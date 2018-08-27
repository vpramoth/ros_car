# OBJECT DETECTION USING CAR CAMERAS AND SENSORS (ROS GAZEBO RVIZD)
----------------------------------------------------------------------------------------------------
### What does this project do?
Project contains a car with front and rear cameras and a laser in the front. A simple world has been
to demonstrate the working of all components. The car is controlled using turtlesim teleop. The laser
scan map is displayed in rviz. 

If you are just interested in running the packages skip to run the project section.

mybot_control package contains the configuration required for providing effort to left and right wheel 
hinge.

mybot_description contains the xml files for the bot.

mybot_gazebo contains the core logic of the project. The launch file of this package calls the launch 
files of the other two packages and they need not be launched explicitly. mybot_gazebo/src directory
contains the cpp file for capturing the laser scan points and making a map.

find_object_2d contains logic for the logic for the object detection using deep learning techniques 
----------------------------------------------------------------------------------------------------
### To run the project:

Clone this repo in your workspace/src and do catkin make

Open new terminal --> Enter: roslaunch mybot_gazebo assembler.launch

Open new terminal --> Enter: rosrun turtlesim turtle_teleop_key /turtle1/cmd_vel:=/mybot/cmd_vel 

Open new terminal --> Enter: rosrun find_object_2d find_object_2d image:=/mybot/camera/image_raw 

Then add the image you want to detect
