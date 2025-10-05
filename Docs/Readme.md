# Project AuraLink

## Description

AuraLink is an integrated IoT project that connects a Python-based backend with embedded firmware to collect sensor data, summarise email content, generate contextual quotes, and communicate with hardware over MQTT. It is split into two primary parts:

- **Aura-Backend** : A Python service that implements agents, messaging, and utilities to process data, summarise emails, and provide high-level business logic. Key folders include `Agent/` (email summarization and quote generation agents), `MQTTClient/` (device communication), `EmailService/`, `Models/`, and `Utils/`.
- **Aura-Firmware** : Embedded firmware (PlatformIO) for the device that reads sensors, manages displays, and handles connectivity. Source lives under `Aura-Firmware/src/` with `platformio.ini` for building and flashing the board.

## Features
- Modular agent-based backend for extensible processing (email summarization, quote generation).
- MQTT-based communication between backend and firmware for real-time updates and control.
- Firmware supports sensor reading, display updates, and robust connection handling.

## Getting Started
### Prerequisites
- Python 3.8+
- PlatformIO for firmware development
- MQTT Broker Credentials (broker address)
- Gmail address for email summarization

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/yasanthaniroshan/AuraLink.git
   cd AuraLink
   ```

2. Clone the submodules:
   ```bash
   git submodule update --init --recursive
   ```
> [!TIP]
> Some submodules may be private. You will need to contact the repository owner for access.

3. Backend Setup
    - Navigate to the `Aura-Backend` directory:
      ```bash
      cd Aura-Backend
      ```
    - Follow the instructions in [Docs/Backend-Setup.md](/Aura-Backend/Docs/Readme.md) to set up the Python environment, install dependencies, and configure environment variables.

4. Firmware Setup
    - Navigate to the `Aura-Firmware` directory:
      ```bash
      cd Aura-Firmware
      ```
    - Follow the instructions in [Docs/Firmware-Setup.md](/Aura-Firmware/Docs/Readme.md) to set up the firmware environment, install dependencies, and configure build settings.


## Important 
- Ensure that the MQTT broker is accessible and the credentials are correctly set in the backend configuration.
- `.env` file in the backend should contain the correct API keys and configurations.
- Make sure to replace the WiFi credentials accordingly in the `include/definitions.h` file before uploading the firmware.
- The Gmail account used for email summarization should have the necessary permissions and settings to allow API access.


> [!WARNING]
> Replace only the editable configurations in the respective configuration files. Do not modify other parts of the codebase as it may lead to unexpected behavior.


