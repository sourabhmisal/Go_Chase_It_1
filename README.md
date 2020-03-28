# Go_Chase_It_1
Making a robot to chase a white-coloured-ball - All in a virtual world!

## Project Aim:

  1) To create two ROS packages inside ```/src```: the ```drive_bot``` and the ```ball_chaser```.
  
  2) In ROS package ```drive_bot```:

    - To create a ```my_robot``` ROS package to hold the robot, white ball, and the world.
    - To design a differential drive robot with the Unified Robot Description Format and adding two sensors to the robot: a lidar and a camera. 
    - To add Gazebo plugins for the robot’s differential drive, lidar, and camera. 
    - Housing the robot inside a gazebo world. 
    - Adding a white-colored ball to gazebo world. The ```world.launch``` file should launch the world with white-colored ball and robot.
  
  3) In ROS package ```ball_chaser```:
  
    - To create a ball_chaser ROS package to hold C++ nodes.
    - Writing a ```drive_bot``` C++ node that will provide a ```ball_chaser/command_robot``` service to drive the robot by controlling its linear x and angular z velocities. The service should publish to the wheel joints and return back the requested velocities.
    - Writing a ```process_image``` C++ node that reads the robot’s camera image, analyzes it to determine the presence and position of a white ball. If a white ball exists in the image, the node should request a service via a client to drive the robot towards it.
    - The ```ball_chaser.launch``` should run both the drive_bot and the process_image nodes.
    
  
## Instructions to download and run the project:
  
  1) Create a new folder, say Go_Chase_It_1 and clone this repository with ```git clone https://github.com/sourabhmisal/Go_Chase_It_1.git``` 
  
  2) Create a build directory and compile the code in the following steps:
    
     - For launching the robot using ROS and Gazebo
     
     ```$ cd ~/Go_Chase_It_1/```
     
     ```$ catkin_make```
     
     ```$ source devel/setup.bash```
     
     ```$ roslaunch my_robot world.launch```
     
     - For launching ball chaser node and making the robot chase the white ball
       
       Open this in new terminal with the same above directory 
     
     ```$ source devel/setup.bash```
     
     ```$ roslaunch ball_chaser ball_chaser.launch```
     
        Move the white ball in front of the robot and see the robot chasing it !

