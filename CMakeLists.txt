cmake_minimum_required(VERSION 2.8.3)
project(dataprocess)

## Add support for C++11, supported in ROS Kinetic and newer
# add_definitions(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  #libpcl-all-dev
  pcl_conversions
  pcl_msgs
  pcl_ros
  roscpp
  std_msgs
)
find_package(OpenCV REQUIRED)

add_executable(get_Image scripts/get_Image.cpp)
add_executable(get_PCD scripts/get_PCD.cpp)
add_executable(get_Depth scripts/get_Depth.cpp)
target_link_libraries(get_Depth ${catkin_LIBRARIES})
target_link_libraries(get_PCD ${catkin_LIBRARIES})
target_link_libraries(get_Image ${catkin_LIBRARIES})


###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES dataprocess
#  CATKIN_DEPENDS cv_bridge libpcl-all-dev pcd_tutorial pcl_conversions pcl_msgs pcl_ros roscpp std_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
# include_directories(include)
include_directories(
  ${catkin_INCLUDE_DIRS}
)

## Declare a C++ executable
## With catkin_make all packages are built within a single CMake context
## The recommended prefix ensures that target names across packages don't collide
# add_executable(${PROJECT_NAME}_node src/dataprocess_node.cpp)


