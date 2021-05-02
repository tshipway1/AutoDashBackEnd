# Raspberry Pi (4) Dash Server
This is the compnent that gets installed on the raspberry Pi. It will run a Node server that will
1. host the AutoDashFrontEnd's dist files from `public/dist`.
2. listen and parse CAN messages from the PiCAN3 hat
3. Communicate with the dash via a websocket

## Tech Stack
* PiCAN 3 drivers
* node 14 (at the time of this and what was available for rpi4)
* Based off of older (build)[https://gist.github.com/Mathews2115/ed3dbd8623ee815a7bed363dbc7c73a6]
  
# How to run
## How to run development on your Linux/Mac

### Install needed libraries
1. install can utils
2. `sudo chmod u+rw RPI_system/start_vcan.sh`

### Simulate CAN in dev
3. Start the virtual CAN interface: `./start_vcan.sh`
4. Start playing CAN messages from a captured can log: `canplayer vcan0=can0  -I ./can_dumps/candump-2021-05-01_223610.log -li`
5. Run the server: `npm run test_server`

## How to run live on a car connected via CAN.
