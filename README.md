# SeismoGuard: Earthquake Detection System

## Overview
The **Earthquake Detection System** is a low-cost, efficient, and scalable earthquake early warning system utilizing STM32 microcontrollers and MPU-6050 accelerometer sensors. Designed for deployment in earthquake-prone regions, this system detects seismic activity, processes acceleration data, and triggers alerts based on predefined safety thresholds.

## Features
- **Real-time Seismic Monitoring:** Detects ground vibrations and potential earthquakes using accelerometer sensors.
- **Multi-MCU Architecture:** A master-slave architecture for reliable data collection and processing.
- **Queue-Based Communication:** Ensures efficient data transmission between sensors and the central processing unit.
- **Alert System:** Activates alarms based on Peak Ground Acceleration (PGA) thresholds.
- **Data Logging & Storage:** Utilizes STM32 flash memory to store acceleration data for analysis.
- **Wired Communication:** Reduces latency and increases system reliability compared to wireless alternatives.

## Hardware Components
- **STM32 Nucleo Board (x3)** – Main processing units
- **MPU-6050 Accelerometers (x4)** – Motion detection sensors
- **Buzzer** – Alarm notification system
- **Vibration Motors** – Used for sensor calibration
- **Power Supply & Cables** – Provides necessary power to microcontrollers and sensors

## System Architecture
The system consists of **one master MCU** and multiple **slave MCUs**:
1. **Master MCU:**
   - Collects and processes acceleration data.
   - Determines whether to trigger an alarm based on PGA values.
   - Stores processed data in flash memory.
2. **Slave MCUs:**
   - Each slave MCU is connected to two MPU-6050 accelerometers.
   - Continuously gathers raw acceleration data.
   - Transmits data to the master MCU via UART communication.

## Installation
1. Assemble all hardware components and connect them as per the circuit design.
2. Flash the firmware onto the STM32 microcontrollers.
3. Connect the master MCU to a computer via USB for data monitoring.
4. Deploy the slave MCUs in various locations, ensuring proper wiring to the master MCU.
5. Run the program and verify sensor calibration.

## Usage
- Power on the system, and ensure all microcontrollers communicate properly.
- Monitor the real-time serial output for acceleration data.
- If seismic activity is detected, the buzzer will sound an alarm based on the severity of ground motion.
- Logged data can be extracted from flash memory for post-event analysis.

## Testing Procedures
- **Communication Test:** Ensures data transmission between the master and slave MCUs.
- **Sensor Calibration:** Uses vibration motors to verify accelerometer accuracy.
- **Alarm Activation:** Simulates various PGA thresholds to confirm the buzzer response.
- **Data Storage Verification:** Checks that accelerometer data is correctly written and retrieved from STM32 flash memory.

## Future Improvements
- **Wireless Communication:** Integrate LoRa or Zigbee for remote data transmission.
- **Cloud Data Storage:** Enable real-time earthquake data logging in a cloud database.
- **Machine Learning Analysis:** Implement AI-based seismic event classification.
- **Extended Sensor Network:** Deploy additional sensors to cover larger geographic areas.

## Contributors
- **Yuvraj Singh Birdi**
- **Andrew Deng**
- **Vincent Liu**

## License
This project is open-source and licensed under the MIT License.

## Acknowledgments
Special thanks to the National Society for Earthquake Technology (NSET) for their insights on earthquake monitoring systems.

---

### Repository Structure
```
📂 earthquake-detection-system
├── 📂 firmware          # Source code for STM32 microcontrollers
├── 📂 hardware          # Circuit diagrams and component details
├── 📂 data              # Sample logged acceleration data
├── README.md           # Project documentation
└── LICENSE             # License details
