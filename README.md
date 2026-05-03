# AmidalaBoard (AmidalaShield)

A custom KiCad PCB shield designed specifically for the [Amidala Firmware](https://github.com/thePunderWoman/AmidalaFirmware) — a control system for astromech and similar droid builds. This board provides all the I/O the firmware needs in a single, purpose-built package.

**Designed by [thePunderWoman](https://github.com/thePunderWoman)**

---

## Overview

The AmidalaShield is a carrier/breakout board for the **ESP32-S3 N16R8 DevKit**. It breaks out and conditions the ESP32-S3's peripherals for the specific needs of the Amidala Firmware: wireless XBee communication, multi-channel servo control, RC receiver input, SD card storage, and expansion headers for additional peripherals.

---

## Requirements

- **Microcontroller:** ESP32-S3 N16R8 DevKit (16 MB flash, 8 MB PSRAM)
- **Wireless modules:** XBee3 modules (x2 recommended — one for drive controller, one for dome controller)

---

## Hardware Features

### Wireless Communication
- **2× XBee3 module sockets** for dual-controller operation (drive + dome)

### Servo Control
- **8× PWM servo outputs** — 3-pin headers (signal, power, ground)

### Serial Ports
- **2× hardware serial ports** — UART0 (shared with USB/programming) and UART1
- **1× software serial port** — for additional peripherals

### I/O
- **6× digital I/O pins**
- **2× analog input pins**
- **1× Aux I2C header** — for external I2C devices

### RC Control
- **PPM input (ppmin)** — for analog RC receiver
- **RC select (rcsel)** — RC source selection
- **sel2** — secondary selection/mode pin

### Storage
- **Built-in microSD card reader** — used for `config.txt` at startup (matches Amidala Firmware config system)

### Expansion
- **Dedicated SPI header** — for external SPI peripherals

---

## Repository Contents

| File/Folder | Description |
|---|---|
| `AmidalaShield.kicad_sch` | Top-level schematic |
| `comms.kicad_sch` | XBee communications sub-sheet |
| `io.kicad_sch` | Digital/analog I/O sub-sheet |
| `power.kicad_sch` | Power distribution sub-sheet |
| `rc_control.kicad_sch` | RC input sub-sheet |
| `servos.kicad_sch` | Servo output sub-sheet |
| `spi.kicad_sch` | SPI header sub-sheet |
| `gerbers/` | Production-ready Gerber files |
| `libraries/` | Project-specific KiCad symbol/footprint libraries |
| `images/` | Board renders and screenshots |

---

## Getting Started

1. Clone this repo and open `AmidalaShield.kicad_pro` in KiCad 8+.
2. Review the schematics for pin assignments before assembling.
3. Use the Gerber files in `gerbers/` to order PCBs from your preferred fab.
4. Flash your ESP32-S3 with the [Amidala Firmware](https://github.com/thePunderWoman/AmidalaFirmware).
5. Place a `config.txt` on the microSD card — see the firmware repo for a full annotated example.

---

## License

This hardware design is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](LICENSE.md) (CC BY-NC-SA 4.0).

You are free to share and adapt this design for non-commercial purposes, as long as you give appropriate credit and distribute any adaptations under the same license.
