# Control-of-Anti-lock-Brake-Systems-with-Value-Iteration

## Introduction 

As a common active safety system in ground vehicles, the Anti-lock Brake System (ABS) avoids wheel lockups during panic braking, minimizing the stopping distance (in most scenarios) and improving the vehicle's directional stability/steerability.  

![image](https://github.com/user-attachments/assets/65609055-8803-47fa-911d-e25089a7e7f1)

The figure above shows the schematics of a hydraulic brake system. There are two solenoid valves: a built valve and a dump valve. The allowed configurations are as follows: 
- **Pressure Increase**: When the built valve is open, and the dump valve is closed, the braking pressure increases behind the braking pad.
- **Pressure Decrease**: When the built valve is closed, and the dump valve is open, the braking pressure decreases behind the braking pad.
- **Pressure Hold**: When both valves are closed, the pressure behind the braking pad is constant.


You might wonder why avoiding wheel lockups decreases the stopping distance. The key to answering this question is understanding the slip and its relationship with the friction coefficient. 

Let us start with the slip. Slip is the ratio of the difference between vehicle speed and wheel linear velocity over vehicle speed. 
Mathematically, ![image](https://github.com/user-attachments/assets/a50b8abe-7366-4ad9-961b-ceacdb81e5ec) 
where lambda is the slip, t denotes time, R is the wheel radius, and omega is the angular velocity of the wheel. You can see that lambda changes between 0 and 1. 
Zero slip means the wheel's linear velocity and the vehicle's speed are the same, so no braking is applied (no slip). When the wheel is locked up, the omega of the wheel is zero, so the slip is 1. 

It is known that friction coefficients are max at some specific values of slip in different road conditions. The figure below shows this relationship for different road conditions. 
By preventing wheels from locking up, the ABS will benefit from the maximum friction coefficient, leading to maximum braking force. 
As 

![image](https://github.com/user-attachments/assets/11e905ea-d9b1-4d3e-9499-23911ec24605)


## Modeling
