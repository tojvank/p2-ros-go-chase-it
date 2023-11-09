### Nano degree program: Robotics Software Engineering  

**Project Title**: Go Chase It! 

By Navjot Kaur


**Project Goals**: 
- Design and build a 4 wheeled skid-steering robot equipped with a camera and lidar,
- Use the world environment created in project1,
- Create a white ball detector algorithm,
- Drive the robot toward the ball and stop once nothing appears on the cam.

**Package Directory**
```
project                          # Go Chase It Project
├── my_robot                       # my_robot package                   
│   ├── launch                     # launch folder for launch files   
│   │   ├── robot_description.launch
│   │   ├── world.launch
│   ├── meshes                     # meshes folder for sensors
│   │   ├── hokuyo.dae
│   ├── urdf                       # urdf folder for xarco files
│   │   ├── my_robot.gazebo
│   │   ├── my_robot.xacro
│   ├── worlds                      # world folder for world files
│   │   ├── myoffice.world
│   ├── CMakeLists.txt             # compiler instructions
│   ├── package.xml                # package info
├── ball_chaser                    # ball_chaser package                   
│   ├── launch                     # launch folder for launch files   
│   │   ├── ball_chaser.launch
│   ├── src                        # source folder for C++ scripts
│   │   ├── drive_bot.cpp
│   │   ├── process_image.cpp
│   ├── srv                        # service folder for ROS services
│   │   ├── DriveToTarget.srv
│   ├── CMakeLists.txt             # compiler instructions
│   ├── package.xml                # package info                  
└──   
```

**Project Description**: 
1 - drive_bot:
    - Create a my_robot ROS package to hold your robot, the white ball, and the world.
    
    - Design a differential drive robot with the Unified Robot Description Format. Add two sensors to your robot: a lidar and a camera. Add Gazebo plugins for your robot’s differential drive, lidar, and camera. The robot you design should be significantly different from the one presented in the project lesson. Minimum required changes are adjusting the color, wheel radius, and chassis dimensions. You can also completely redesign the robot model! After all, you want to impress your future employers :-D
    
    - Create a new world, which is different from the world you built in the Build My World project and house your robot inside that world.
    
    - Add a white-colored ball to your Gazebo world and save a new copy of this world.
    
    - The world.launch file should launch your world with the white-colored ball and your robot.

2 - ball_chaser:

    - Create a ball_chaser ROS package to hold your C++ nodes.
    
    - Write a drive_botC++ node that will provide a ball_chaser/command_robot service to drive the robot by controlling its linear x and angular z velocities. The service should publish to the wheel joints and return back the requested velocities.
    
    - Write a process_image C++ node that reads your robot’s camera image, analyzes it to determine the presence and position of a white ball. If a white ball exists in the image, your node should request a service via a client to drive the robot towards it.
    
    - The ball_chaser.launch should run both the drive_bot and the process_image nodes.
