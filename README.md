# VR-Robotic-Car-Simulator
Garduation project 
#
We aim to construct a realistic general-purpose motion simulator using Stewart platform mechanism which could be used to simulate any motion environment (Airplane, Vehicle, …etc.) just by changing the upper frame holding the driver within it.
To get the best performance out of any motion simulator, The Instant Driver-System dynamic interaction should be the focal point.

For our vehicle driving simulator system, the driver interacts with the simulation environment through steering wheel, gas and brake pedals, where the simulation environment is generated using an application called “BeamNG”. To extract the vehicle motion parameters (Roll, Pitch and Yaw) from the simulation environment another application called “SimTools” is used, Then Simtools sends these pieces of information to a chosen communication port.

A virtual communication port is established and connected to the SimTools Port to send the parameters to the embedded controller (Raspberry pi) via LAN (Server and Client) communication, the embedded controller then substitutes the parameters into an inverse kinematics equation which outputs the position needed for all hydraulic actuators end point to establish the required platform position.

To make the closed loop control system we measure the actual length of the actuators using a wired potentiometer sensor, which outputs an analog reading corresponds to the actual position of the hydraulic actuator end point, then the reading is digitalized using analog to digital converter and captured by the embedded controller which calculates the error (kinematic Equation actuator end point position – actual actuator end point position) and performs the PID control.
