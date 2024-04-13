# Parking Spot Availability Detection
This script utilizes YOLO object detection to identify open parking spots in a video feed. It leverages a custom YOLOv8 weight trained on our model car, the ROSMASTER R2, developed by Yahboom Technologies. This specialized weight enables YOLO to effectively detect the model car used in this application, enabling real-time identification of occupied parking spots. The script then determines the availability of parking spaces, which are subsequently published to a ROS2 topic. These data are utilized by the `avp.py` node, available [here](https://github.com/zubxxr/Automated-Valet-Parking-Autoware), enabling autonomous parking in open spots.

## Quick Setup

1. **Install Packages**: Create a virtual environment, activate it and install the packages from the requirements file.

    ```bash
    python3 -m venv <your_venv>
    source <your_venv>/bin/activate
    pip install -r requirements.txt
    ```
    
2. **Start the Parking Spot Detection**: Run the following script to detect open parking spots. 
    ```bash
    python parking_spot_detection.py
    ```

## Customized Setup
To use the script in your own environment, you'll need to follow these steps:

1. **Mapping Parking Spaces**: Use the `parking_spot_coordinate_mapper.py` script on your live feed or recorded video to identify parking spaces. 
2. **Define Coordinates**: Manually mark the coordinates of each parking spot by dragging the mouse over each corner and recording the coordinates in this order: `Top Left, Top Right, Bottom Right, Bottom Left`.
3. **Update Parking Space Variables**: Update the area variables at the start of `parking_spot_detection.py` with each coordinate.
