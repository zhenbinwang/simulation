# Install dependent packages
sudo apt-get install ros-noetic-ros-control
sudo apt-get install ros-noetic-ros-controllers
sudo apt-get install ros-noetic-gazebo-ros-control 
sudo apt-get install ros-noetic-effort-controllers
sudo apt-get install ros-noetic-position-controllers
sudo apt-get install ros-noetic-velocity-controllers

# Operating Steps
roslaunch mingnuo_description gazebo_mingnuo.launch 

# Control robot communication
# Speed control of the left and right wheels of the car, which sends speed topics through speed control
rostopic pub -1 /mingnuo_carlike/wheel_rb_velocity_controller/command std_msgs/Float64 "data: 0.5" 
rostopic pub -1 /mingnuo_carlike/wheel_lb_velocity_controller/command std_msgs/Float64 "data: 0.5" 

# The front wheel of the car is the steering wheel, which sends the position topic through position control
rostopic pub /mingnuo_carlike/wheel_steering_position_controller/command std_msgs/Float64 "data: 0.5
