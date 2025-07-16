# Hexa Keypad Encoder – Verilog Implementation

This repository contains a Verilog-based design and testbench for interfacing and encoding signals from a hexadecimal (4x4) matrix keypad. The project includes the main encoder logic, row scanning, and synchronization modules, along with a behavioral testbench and waveform configuration for simulation.

## 📁 Files Overview

| File Name                    | Description |
|-----------------------------|-------------|
| `Hex_Keypad_Encoder.v`      | Top-level module that detects and encodes keypad presses. |
| `Row_Signal.v`              | Generates row scanning signals for the keypad. |
| `Synchronizer.v`           | Eliminates metastability from asynchronous keypresses. |
| `test_Hex_Keypad.v`         | Testbench to verify functional behavior of the keypad encoder. |


---

## 📌 Functionality

This project models a **hex keypad encoder** which:
- Scans a 4x4 keypad matrix.
- Detects the pressed key by checking column signals.
- Outputs a 4-bit hex code corresponding to the pressed key.
- Debounces keypresses and synchronizes inputs to the system clock.

### ✳️ Modules

#### `Hex_Keypad_Encoder`
- Inputs: `clk`, `reset`, `col` (4-bit).
- Outputs: `row` (4-bit), `key_pressed` (flag), `hex_out` (4-bit).
- Logic: Scans rows and detects column activations. Encodes key index to hex output.

#### `Row_Signal`
- Cycles through row signals one at a time to perform keypad scanning.

#### `Synchronizer`
- Converts asynchronous input signals into clock-domain signals to avoid metastability.

#### `test_Hex_Keypad`
- Simulates keypress patterns.
- Validates encoding logic, edge cases, and response time.

---

## ✅ How to Run Simulation

1. **Simulation Tool**: Use ModelSim / Vivado / XSIM or any Verilog simulator.
2. **Compile**:
   ```bash
   vlog Hex_Keypad_Encoder.v Row_Signal.v Synchronizer.v test_Hex_Keypad.v
