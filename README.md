
# Follow the following instruction for IMU node

sudo apt-get install ros-kinetic-imu-tools

cd ~/catkin_ws/src/
git clone https://github.com/jeskesen/i2c_imu
cd ..
catkin_make

sudo apt-get install python-dev
cd ~/catkin_ws/src/
git clone https://github.com/RTIMULib/RTIMULib2
cd Linux
cd python
sudo python setup.py build
sudo python setup.py install
nano ~/catkin_ws/src/RTIMULib2/RTIMULib/IMUDrivers/RTIMUDefs.h
>> Change the MPU9250 ID to 73
cd ~/catkin_ws/src/RTIMULib2/RTIMULib/
mkdir build
cd build
cmake ..
make -j4
sudo make install
sudo ldconfig

roslaunch i2c_imu i2c_imu_auto.launch


https://github.com/RTIMULib/RTIMULib2/blob/master/Linux/README.md
