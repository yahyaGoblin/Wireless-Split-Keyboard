# Wireless Split Keyboard

A fully wireless split keyboard PCB, designed for ergonomic typing with no cables between halves or to the host.

![PCB Preview](./images/preview.jpg)

## Features

- Wireless split design — no cable between halves
- Bluetooth LE connectivity to host
- Battery powered on each half
- 1N4148 diodes for full anti-ghosting / n-key rollover
- Low power design for extended battery life

## Bill of Materials

| Ref | Component | Value / Model | Qty |
|-----|-----------|---------------|-----|
| U1–U2 | Wireless MCU | nice!nano (nRF52840) | 2 |
| SW1–SWn | Mechanical Key Switch | Cherry MX compatible | n |
| D1–Dn | Switching Diode | 1N4148 SOD-123 | n |
| BAT1–BAT2 | LiPo Battery | 3.7V 301230 or similar | 2 |
| C1–C2 | Decoupling Capacitor | 100nF 0402 | 2 |
| R1–R2 | Pull-up Resistor | 4.7kΩ 0402 | 2 |
| SW_RESET1–2 | Reset Button | 3x6mm tactile switch | 2 |
| SW_POWER1–2 | Power Switch | MSK-12C02 slide switch | 2 |
| J1–J2 | Battery Connector | JST PH 2.0 2-pin | 2 |

> Update switch quantities (n) based on your layout. Part numbers are suggestions.

## PCB Design

Each half is an independent PCB with its own MCU and battery:
- **Left half** — acts as the central device, connects to the host via Bluetooth
- **Right half** — acts as a peripheral, communicates wirelessly to the left half

## Fabrication

Gerber files for both halves are in the `/gerbers` folder.

Recommended specs:
- Layers: 2
- Thickness: 1.6mm
- Surface finish: HASL or ENIG

## Firmware

Designed for [ZMK Firmware](https://zmk.dev/), which has first-class support for wireless split keyboards and the nice!nano.

## Battery Life

Estimated battery life varies by usage and battery capacity. With a 110mAh battery expect several weeks of typical use.

## Project Files

| File | Description |
|------|-------------|
| `keyboard_left.kicad_sch` | Left half schematic |
| `keyboard_right.kicad_sch` | Right half schematic |
| `keyboard_left.kicad_pcb` | Left half PCB layout |
| `keyboard_right.kicad_pcb` | Right half PCB layout |
| `/gerbers` | Fabrication files for both halves |

## License

Open source hardware — feel free to modify and build your own.