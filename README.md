# 🏭 Intelligent Conveyor Line with Dynamic Routing & Fault Detection (PLC)

## 📌 Project Overview

This project demonstrates an **advanced PLC-based industrial automation system** for conveyor-based material handling. The system intelligently detects, classifies, and routes items while continuously monitoring for faults to ensure safe and reliable operation.

It simulates a **real-world factory conveyor system** with dynamic routing, safety interlocking, and fault analytics using **Ladder Logic in OpenPLC**.

<img width="1920" height="1020" alt="Screenshot 2026-04-29 153951" src="https://github.com/user-attachments/assets/3a6e0019-8cae-4f7b-9bda-7b8265622a39" />

-----

<img width="1920" height="1020" alt="Screenshot 2026-04-29 154010" src="https://github.com/user-attachments/assets/d1b9a34f-6d30-46dc-b561-9fcd0caeaa53" />

-----

<img width="1920" height="1020" alt="Screenshot 2026-04-29 154022" src="https://github.com/user-attachments/assets/a744dd24-0228-41fd-9d72-09c3d13d9f94" />

-----

<img width="1920" height="1020" alt="Screenshot 2026-04-29 154037" src="https://github.com/user-attachments/assets/7c72f278-15a9-45f3-aeac-d5afbdcaddae" />

-----
<img width="1920" height="1020" alt="Screenshot 2026-04-29 154108" src="https://github.com/user-attachments/assets/039747e9-1e25-4a21-b556-2672050fa98f" />

-----

## 🎯 Objectives

* Automate conveyor-based material handling
* Implement intelligent routing of items
* Ensure safe operation using interlocking and fault detection
* Simulate real-time industrial automation workflow


## ⚙️ System Architecture

### 🔹 Inputs

| Input        | Address | Description                 |
| ------------ | ------- | --------------------------- |
| Start Button | %IX0.0  | Starts conveyor system      |
| Stop Button  | %IX0.1  | Stops system                |
| Entry Sensor | %IX0.2  | Detects incoming item       |
| Metal Sensor | %IX0.3  | Identifies metal objects    |
| Fault Sensor | %IX0.4  | Detects abnormal conditions |


### 🔹 Outputs

| Output         | Address | Description            |
| -------------- | ------- | ---------------------- |
| Conveyor Motor | %QX0.0  | Drives conveyor belt   |
| Diverter A     | %QX0.1  | Routes metal items     |
| Diverter B     | %QX0.2  | Routes non-metal items |
| Reject Gate    | %QX0.3  | Diverts faulty items   |
| Alarm          | %QX0.4  | Alerts fault condition |


### 🔹 Internal Variables

| Variable   | Description                |
| ---------- | -------------------------- |
| item_flag  | Indicates item presence    |
| metal_flag | Indicates metal detection  |
| t1_done    | Metal timer completion     |
| t2_done    | Non-metal timer completion |


### 🔹 Timer Configuration

| Variable | Type | Value |
| -------- | ---- | ----- |
| pt1      | TIME | T#2s  |


## 🔄 Working Principle

### ▶️ Step 1: System Start

* Pressing the start button activates the conveyor motor using latching logic
* System runs continuously until stopped


### ▶️ Step 2: Item Detection

* Entry sensor detects incoming item
* `item_flag` is set to indicate item presence


### ▶️ Step 3: Classification

* Metal sensor identifies item type:

  * Metal → `metal_flag = TRUE`
  * Non-metal → `metal_flag = FALSE`


### ▶️ Step 4: Dynamic Routing

* Based on classification:

  * Metal items → Diverter A
  * Non-metal items → Diverter B
* Interlocking ensures only one diverter operates at a time


### ▶️ Step 5: Fault Detection

* Fault sensor monitors abnormal conditions
* On detection:

  * Conveyor stops
  * Reject gate activates
  * Alarm is triggered


### ▶️ Step 6: Timer-Controlled Operation

* Diverters operate for a fixed duration (2 seconds) using TON timers
* Automatically turn OFF after the time delay


### ▶️ Step 7: Continuous Processing

* System resets and prepares for the next item
* Process repeats continuously


## 🪜 Ladder Logic Highlights

* Latching (Seal-in Circuit) for motor control
* Sensor-based decision-making
* Interlocking logic for safety
* Timer (TON) for controlled actuation
* Fault detection and alarm handling


## 🧠 Key Features

* ✅ Intelligent routing system
* ✅ Multi-condition decision logic
* ✅ Fault detection with alarm system
* ✅ Timer-based actuator control
* ✅ Industrial-style automation workflow


## 🏭 Industrial Applications

* Warehouse automation systems
* Manufacturing production lines
* Material handling systems
* Logistics and sorting centers


## 🚀 Advantages

* Improves operational efficiency
* Reduces manual intervention
* Enhances system safety
* Scalable for real industrial deployment


## 🔮 Future Enhancements

* Add production counters and analytics
* Integrate HMI for real-time monitoring
* Connect with SCADA systems
* Implement predictive maintenance logic


## 📌 Conclusion

This project replicates a **real industrial conveyor automation system** using PLC ladder logic. It combines intelligent decision-making, safety mechanisms, and real-time control, making it a strong demonstration of industrial automation skills.


## 👨‍💻 Author

**Vijayalakshmi S**
Electrical Automation Engineer


## ⭐ Note

This project is developed for learning and demonstrating industrial PLC automation concepts using OpenPLC simulation.
