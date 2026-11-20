# Keypad Based Product Counting and Automatic Batch Packing System with Station Sensing using LPC2129

## Abstract
This project proposes a keypad-based product counting and automatic batch packing system using the LPC2129 microcontroller. The system counts products passing through a sensing station, lets an operator set a target batch quantity using a keypad, and indicates when the preset quantity is reached. The station sensor detects product passage and sends signals to the controller. When the required count is reached, the controller can trigger a batch-completion alert and interface with a packing or conveyor mechanism through suitable driver circuitry. The system helps reduce manual counting and improve consistency in batch packing.

## Project Overview
In small-scale production and packaging, products are often counted and grouped manually. Manual counting can be time-consuming and may cause errors. This embedded system automates product counting using a station sensor and compares the count with a batch quantity entered by the operator.

## Objectives
- Automatically count products passing the sensing station.
- Allow the operator to set the required batch size using a keypad.
- Compare the running count with the target quantity.
- Display the count and batch status.
- Alert the operator when the batch is complete.
- Provide an interface for a conveyor or packing mechanism using suitable driver circuitry.

## Block Diagram

```text
        +----------------+       +-------------------+
        |     Keypad    |       |  Station Sensor  |
        | Batch Setting |       | Product Detection|
        +-------+--------+       +---------+---------+
                |                          |
                +------------+--------------+
                             |
                    +--------v---------+
                    |    LPC2129      |
                    | Count & Control |
                    +---+----------+---+
                        |          |
             +----------v--+   +---v------------+
             | LCD Display |   | Driver Circuit |
             | Count/Status|   | Motor/Actuator |
             +------+------+   +-------+--------+
                    |                  |
             +------v------+    +------v---------+
             | LED/Buzzer  |    | Conveyor/Packing|
             | Completion  |    | Mechanism     |
             +-------------+    +----------------+
```

*Note: This is a conceptual block diagram. Exact sensor, motor driver, and packing actuator selection depends on the prototype implementation.*

## Hardware Components Required
- LPC2129 microcontroller board
- Matrix keypad (for example, 4×4)
- Station sensor (IR, photoelectric, or suitable proximity sensor)
- LCD display (16×2 or compatible)
- Buzzer
- LED indicators
- Conveyor motor / packing actuator (if used)
- Motor driver or relay interface
- Regulated power supply
- Breadboard or PCB, connecting wires, and mounting hardware

## Software Requirements
- Embedded C
- LPC2129-compatible ARM development toolchain
- Programming/debugging tools available in the lab
- Firmware for keypad scanning, sensor input, counting logic, display updates, and output control

## Working Principle
1. Power up the controller, sensor, display, and interface circuits.
2. Enter the desired batch size using the keypad.
3. The station sensor detects each product passing the sensing point.
4. The LPC2129 increments the count for each valid detection.
5. The count is displayed and compared with the target batch size.
6. When the target is reached, the controller activates a batch-complete indication and signals the packing/conveyor interface.
7. Reset or re-arm the system to begin the next batch.

## Applications
- Small-scale production and packaging lines
- Batch counting before packing
- Product grouping stations
- Embedded systems and industrial automation demonstrations

## Advantages
- Reduces manual counting effort
- Helps maintain consistent batch quantity
- Provides real-time count and status feedback
- Batch size can be changed through keypad input
- Can be expanded for conveyor and packing automation

## Conclusion
The keypad-based product counting and automatic batch packing system using LPC2129 combines product sensing, embedded counting, batch comparison, and output control. It offers a practical approach to reducing manual counting errors and provides a base for developing a more complete automated packing station.
