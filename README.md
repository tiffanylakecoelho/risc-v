# RISC-V Single-Cycle Processor (Logisim)

This project is a fully functional single-cycle RISC-V processor built in Logisim, supporting a core subset of the RISC-V instruction set. It includes a custom test suite and two byte reversal programs written in RISC-V assembly to verify processor correctness and performance.

## 🧠 Overview

The processor executes one instruction per cycle and follows the classic five-stage architecture: fetch, decode, execute, memory access, and write-back. Designed with modularity and clarity in mind, the build focuses on clean subcircuit organization, efficient control signal routing, and accurate instruction decoding.

## ✅ Supported Instructions

**R-type:** `ADD`, `SUB`, `AND`, `OR`, `XOR`, `SLT`, `SLL`, `SRA`
**I-type:** `ADDI`, `ANDI`, `LW`, `LB`
**S-type:** `SW`, `SB`
**U-type:** `LUI`

## 🧪 Programs & Testing

Included in this repo:

* **Bitmask Byte Reversal** – Uses bitwise operations and shifts to reverse the order of bytes in a 32-bit word.
* **Load/Store Byte Reversal** – Reverses bytes using `LB` and `SB` instructions and reloads the final word.
* **Instruction Test Suite** – Validates all supported opcodes, with edge cases and register state expectations.

### Example Output

```assembly
# Reversing 0x12345678 with bitmasks → 0x78563412
# Reversing 0x13f4464c with LB/SB → 0x4c46f413
# XOR result stored in t2 → 0x3490b721
```

## 🛠️ Built With

* **Logisim Evolution** – Digital circuit simulation
* **RISC-V Assembly** – For validation and testing
* **Java CLI** – For automated register state verification

## 📁 Files in This Repository

* `RISCV.circ` – Complete Logisim processor circuit
* `byte_reversal.txt` – Byte reversal program
* `test_suite.txt` – Instruction and edge case tests
* `README.md` – This file

## 🚀 How to Run

1. Clone this repository
2. Open `RISCV.circ` in [Logisim Evolution](https://github.com/logisim-evolution/logisim-evolution)
3. Load `test_suite.txt` into the Program ROM
4. Step through cycles or use the CLI tester:

```bash
java -jar logisim.jar --test-risc test_suite.txt RISCV.circ
```

## 🧾 Highlights

* Designed a full instruction decoder from scratch
* Built immediate generator and ALU control logic
* Verified edge cases and instruction correctness with cycle-limited tests
* Demonstrated complete 32-bit byte manipulation in RISC-V assembly

