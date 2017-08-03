cmake_minimum_required(VERSION 2.8.3)
project(autonomous_exploration_msgs)

## Add support for C++11, supported in ROS Kinetic and newer
add_definitions(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  tf
  roscpp
  rospy
  std_msgs
  message_generation
  actionlib_msgs
  actionlib
  geometry_msgs
  nav_msgs
)

find_package(Boost REQUIRED COMPONENTS system)

add_action_files(
  FILES
  Explore.action
)

generate_messages(
  DEPENDENCIES
  std_msgs
  actionlib_msgs
  geometry_msgs
  nav_msgs
)

catkin_package(
  CATKIN_DEPENDS actionlib_msgs 
)

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${Boost_INCLUDE_DIRS}
)
