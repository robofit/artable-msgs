cmake_minimum_required(VERSION 2.8.3)
project(art_msgs)

find_package(catkin REQUIRED COMPONENTS
  actionlib
  actionlib_msgs
  std_msgs
  geometry_msgs
  shape_msgs
  message_generation)

add_action_files(
  DIRECTORY action
  FILES PickPlace.action LocalizeAgainstUMF.action LearningRequest.action
  ArmNavigation.action
)

add_message_files(
  FILES
  GuiNotification.msg
  ObjInstance.msg
  ObjectType.msg
  InstancesArray.msg
  ObjectsCentroids.msg
  UserStatus.msg # deprecated
  UserActivity.msg # deprecated
  SystemState.msg
  SceneLabel.msg
  ProgramItem.msg
  ProgramBlock.msg
  Program.msg
  ProgramHeader.msg
  InterfaceState.msg
  KeyValue.msg
  Touch.msg
  User.msg
  UserArray.msg
  HololensState.msg
  CollisionPrimitive.msg
  CollisionObjects.msg
  Color.msg
)

add_service_files(
    FILES
    AddCollisionPrimitive.srv
    GetCollisionPrimitives.srv
    ClearCollisionPrimitives.srv
    getProgram.srv
    getProgramHeaders.srv
    storeProgram.srv
    getObjectType.srv
    getAllObjectTypes.srv
    storeObjectType.srv
    ProgramIdTrigger.srv
    TouchCalibrationPoints.srv
    NotifyUser.srv
    ProgramErrorResolve.srv
    SelectArm.srv
    RecalibrateCell.srv
    ObjectFlagSet.srv
    ObjectFlagClear.srv
    ReinitArms.srv
    StringTrigger.srv
    PoseStampedTrigger.srv
    GetRosparam.srv
)

generate_messages(
  DEPENDENCIES actionlib_msgs shape_msgs
)

catkin_package(
  CATKIN_DEPENDS
    actionlib_msgs
    shape_msgs
    std_msgs
    geometry_msgs
    message_runtime
    )
