
## Using `ros1_bridge` to Bridge Topics from ROS 1 to ROS 2

This repository provides instructions on how to use `ros1_bridge` to bridge topics from ROS 1 to ROS 2 environments. `ros1_bridge` facilitates communication between ROS 1 and ROS 2 by converting messages between their respective message types.

### Prerequisites

- **ROS 1** (Kinetic, Melodic, or Noetic) installed and configured.
- **ROS 2** (Foxy, Galactic, or later) installed and configured.
- `ros1_bridge` package installed in your ROS 2 environment.

### Steps to Bridge Topics

1. **Setup Environment**

   Ensure that both ROS 1 and ROS 2 environments are properly set up. Source the setup files for both distributions in separate terminals:

   ```bash
   # Source ROS 1 environment (replace <distro> with your ROS 1 distribution)
   source /opt/ros/<distro>/setup.bash

   # Source ROS 2 environment (replace <distro> with your ROS 2 distribution)
   source /opt/ros/<distro>/setup.bash
   ```

2. **Start `roscore` and `ros1_bridge`**

   In a terminal, start `roscore` for ROS 1:

   ```bash
   roscore
   ```

   In another terminal, launch `ros1_bridge` to initiate communication between ROS 1 and ROS 2:

   ```bash
   ros2 run ros1_bridge dynamic_bridge
   ```

3. **Bridge Specific Topics**

   Identify the ROS 1 topics you want to bridge to ROS 2. For example, to bridge `/rosout`:

   ```bash
   # Echo ROS 1 topic (to verify messages)
   rostopic echo /rosout

   # Echo ROS 2 bridged topic (to receive messages from ROS 1)
   ros2 topic echo /ros1/rosout
   ```

4. **Verify Communication**

   Messages published on the ROS 1 topic `/rosout` should now be visible on `/ros1/rosout` in ROS 2. Use the `rostopic` and `ros2 topic` commands to verify the correctness of bridged messages between ROS 1 and ROS 2.

### Additional Notes

- Ensure that both ROS 1 and ROS 2 environments are running and configured correctly throughout the process.
- Adjust topic names and message types as per your specific use case and setup.

---
