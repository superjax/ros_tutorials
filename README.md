# turtlesim_dynamics
Fork of the ROS tutorials turtlesim package, modified to add dynamics and wind for use in the BYU MAGICC lab controls tutorials.

# Topics:
## Subscriptions
* cmd_vel - commanded velocity (bypasses internal dynamics and behaves like a normal turtlsim node)
* cmd_wrench - commanded Forces and Torques (Only x force and z torque do anything)

## Publications
* pose - the 2D pose of the turtle

# Parameters
* mass - mass of the turtle
* inertia - inertia of the turtle
* linear_damping - the damping on linear velocity
* angular_damping - the damping on angular velocity
* wind_x - wind in the x direction (world-fixed)
* wind_y - wind in the y direction (world-fixed)

Dynamics are calculated at 1000 Hz by the following method (see line 98-99 of turtle.cpp)

`linear_acceleration =  (force-linear_damping*lin_vel)/mass`

`angular_acceleartion = (torque - angular_damping*ang_vel)/inertia`

Wind is applied as a constant force in the component direction


