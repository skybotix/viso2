cmake_minimum_required(VERSION 2.8.3)
project(libviso2)

find_package(catkin REQUIRED )

catkin_package(
  INCLUDE_DIRS libviso2/src
  LIBRARIES viso2
)

add_definitions(-Wall -march=native -O3)

include_directories(libviso2/src
  ${catkin_INCLUDE_DIRS}
)

add_library(viso2
  libviso2/src/filter.cpp
  libviso2/src/matcher.cpp
  libviso2/src/matrix.cpp
  libviso2/src/reconstruction.cpp
  libviso2/src/triangle.cpp
  libviso2/src/viso.cpp
  libviso2/src/viso_mono.cpp
  libviso2/src/viso_stereo.cpp)

set_target_properties(viso2 PROPERTIES OUTPUT_NAME viso2)


