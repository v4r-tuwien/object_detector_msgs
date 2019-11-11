cmake_minimum_required(VERSION 2.4.6)
project(object_detector_msgs)

# Get the information about this package's buildtime dependencies
find_package(catkin REQUIRED
  COMPONENTS 
  message_generation 
  std_msgs 
  actionlib_msgs 
  sensor_msgs
)

# Declare the message files to be built
add_message_files(
  FILES
  BoundingBox.msg
  Detection.msg
  Detections.msg
)

# Declare the service files to be built
add_service_files(FILES
  start.srv
  stop.srv
)

add_action_files(FILES
  CheckForDetections.action
)

generate_messages(
  DEPENDENCIES
  actionlib_msgs
  sensor_msgs
  std_msgs
)

# Declare that this catkin package's runtime dependencies
catkin_package(
  CATKIN_DEPENDS 
  std_msgs 
  sensor_msgs
)

