# 11_Security_Access_Control

# Security Access Control System

## Overview

This project implements a security access control system using an Arduino and a keypad. Users can enter a passcode using the keypad, and the system will compare it with a predefined passcode. If the entered passcode matches the predefined one, the system grants access. Otherwise, an alarm is triggered, indicating an incorrect passcode entry.

## Components

- Arduino board (e.g., Uno, Mega)
- 4x4 Keypad
- Buzzer
- Jumper wires

## Circuit Diagram

1. **Keypad**
   - Connect the row pins of the keypad to digital pins 2, 3, 4, and 5 on the Arduino.
   - Connect the column pins of the keypad to digital pins 6, 7, 8, and 9 on the Arduino.

2. **Buzzer**
   - Connect the positive (+) pin of the buzzer to digital pin 12 on the Arduino.
   - Connect the negative (-) pin of the buzzer to GND on the Arduino.

## Code Explanation

### Variables and Objects

- `keys[][]`: Array to define the layout of the keypad.
- `rowPins[]` and `colPins[]`: Arrays to define the pins connected to the rows and columns of the keypad.
- `kpd`: Keypad object for reading key presses.
- `keyCode`: Predefined passcode for access control.
- `keyCodeBuffer`: String variable to store the passcode entered by the user.
- `buzzerPin`: Pin connected to the buzzer for sounding the alarm.

### Setup

- Serial communication is initialized at 9600 baud.
- A message is printed to the Serial Monitor instructing the user to enter the passcode using the keypad.

### Loop

- The code continuously checks for key presses on the keypad.
- If a numeric key (0-9) is pressed, it is appended to the `keyCodeBuffer`.
- If the '#' key is pressed, the entered passcode is compared with the predefined passcode (`keyCode`).
  - If the passcodes match, a message indicating successful access is printed to the Serial Monitor.
  - If the passcodes do not match, an alarm is triggered by activating the buzzer, and a message indicating an incorrect passcode is printed to the Serial Monitor.
- If an invalid key is pressed, a message indicating an invalid key is printed to the Serial Monitor.

## Usage Instructions

1. Assemble the circuit as per the circuit diagram.
2. Upload the provided code to the Arduino board.
3. Open the Serial Monitor from the Arduino IDE (Tools -> Serial Monitor) to view status messages.
4. Enter the predefined passcode using the keypad.
5. Press '#' to submit the passcode.
6. Observe the behavior of the system:
   - If the passcode is correct, a message indicating successful access is displayed.
   - If the passcode is incorrect, an alarm is triggered, and a message indicating an incorrect passcode is displayed.

## Example Output

- Entering the correct passcode followed by '#' will display:
  ```
  Passcode is correct
  ```
- Entering an incorrect passcode followed by '#' will trigger the buzzer and display:
  ```
  Passcode is incorrect
  ```

This project provides a simple yet effective security access control system using an Arduino and a keypad, suitable for various applications requiring access control.

---

