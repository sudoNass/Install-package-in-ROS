### Install-package-in-ROS
we are going to try to run a robotic arm by cloning an existing project from GitHub, from this account [Smart Methods](https://github.com/smart-methods)

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
```
sudo apt install curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
```
sudo apt install python3-rosdep

sudo rosdep init

rosdep update
```
```
mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/

catkin_make

cd ~/catkin_ws/src
```
here i'm cloning the repository project that i wanted.
```
git clone https://github.com/smart-methods/arduino_robot_arm.git 
```
```
cd ~/catkin_ws

rosdep install --from-paths src --ignore-src -r -y
```
install needed requirements. 
```
sudo apt-get install ros-noetic-moveit

sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui

sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
```
to run the project using RVIZ.
```
catkin_make

roslaunch robot_arm_pkg check_motors.launch
```

<img width="604" alt="image" src="https://user-images.githubusercontent.com/107954336/181574350-99eca267-52c8-4519-984d-7f945239e35c.png">
