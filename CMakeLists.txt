cmake_minimum_required(VERSION 2.8.3)
project(viscap_gazebo)

find_package(catkin REQUIRED COMPONENTS
    roscpp imav_2017 geometry_msgs sensor_msgs nav_msgs tf
)

catkin_package(
    CATKIN_DEPENDS roscpp imav_2017 geometry_msgs sensor_msgs nav_msgs tf
)

include_directories(
    ${catkin_INCLUDE_DIRS}
)

add_executable(joystick_control src/joystick_control.cpp ${CPP_FILES})
add_dependencies(joystick_control ${catkin_EXPORTED_TARGETS})
target_link_libraries(joystick_control ${catkin_LIBRARIES})

add_executable(transform_publisher src/transform_publisher.cpp ${CPP_FILES})
add_dependencies(transform_publisher ${catkin_EXPORTED_TARGETS})
target_link_libraries(transform_publisher ${catkin_LIBRARIES})
