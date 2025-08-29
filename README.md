# Model_Rocket_telemetry_LORA_E32_
This repository contains two custom PCBs for a rocket telemetry system. Sonic is the transmitter board that collects data from the flight computers via I²C and sends it using the LoRa E32-900T30D module. Echo is the receiver board that receives this data and passes it to the ground station for monitoring.

SONIC (Rocket Communication Computer)
Collects data from the three microcontrollers (FC1, FC2, and IGRIS) via I2C communication continuously.

Converts this data from CSV format into a compact binary format to reduce packet size for efficient transmission.

Saves the collected data onto an SD card for local storage.

Transmits the binary data wirelessly to the ground station using an E32-900T30D radio module.

ECHO (Ground Computer)
Receives binary data wirelessly from the SONIC module using its E32-900T30D radio transceiver.

Also listens to a secondary source, the CANSAT, via another radio transceiver.

Forwards the received binary data directly to the ground station PC via USB serial communication.

Functions as a transparent relay, enabling the PC to parse the binary data and display it on the user interface.
