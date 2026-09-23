# DISPLAY-GPIO-SWITCH-COUNT-USING-UART
Maintain a switch-press counter inside an ISR and periodically transmit the count through UART from the main loop. Evaluate the data exchange between the ISR and main program. 
---

## Apparatus Required

| S. No. | Apparatus / Software | Specification |
|:---:|---|---|
| 1 | Microcontroller Development Board | **NXP S32K144 Development Board** |
| 2 | IDE | **S32 Design Studio** |
| 3 | Programming Language | **Embedded C** |
| 4 | SDK | **S32K144 SDK** |
| 5 | LED | On-board LED / External LED |
| 6 | Programmer / Debugger | On-board Debugger / OpenSDA |
| 7 | USB Cable | For programming and power supply |

---
## Procedure

1. Connect the **NXP S32K144 Evaluation Board** to the computer using the USB Debug Cable.

2. Open **S32 Design Studio** and create/open the project for the **S32K144 microcontroller**.

3. Configure the **user switch GPIO pin as a Digital Input** with interrupt capability.

4. Configure the **UART peripheral** for serial communication with the required baud rate and communication parameters.

5. Configure the required **MCAL GPIO and UART modules** and generate the initialization code using the **ANCIT GenX Tool**.

6. Declare a global **switch-press counter variable** that can be accessed by both the ISR and the main program.

7. Configure the GPIO interrupt to detect the required switch transition, such as a falling-edge or rising-edge event.

8. Write the **GPIO Interrupt Service Routine (ISR)** to increment the switch-press counter whenever a valid switch press is detected.

9. Keep the ISR short and avoid performing UART transmission inside the ISR.

10. In the **main loop**, periodically read the updated switch-press counter.

11. Transmit the counter value through the **UART API** at regular intervals.

12. Connect the S32K144 UART interface to the computer and open **PuTTY** with the configured serial communication settings.

13. Build the project in **S32 Design Studio** and verify that there are no compilation errors.

14. Program the application into the **S32K144 Evaluation Board** and start execution.

15. Press the switch several times and observe that the ISR increments the counter for each valid switch press.

16. Observe the transmitted counter value on **PuTTY** from the main loop.

17. Compare the number of physical switch presses with the counter value displayed through UART.

18. Verify that the **ISR updates the counter**, while the **main loop reads and transmits the updated value**, demonstrating data exchange between interrupt and main program contexts.

19. Repeat the test with different numbers of switch presses and verify that the UART output corresponds to the accumulated switch-press count.

---

## OUTPUT
<img width="642" height="255" alt="image" src="https://github.com/user-attachments/assets/3a654f66-f3b1-4002-bf17-af4e0fa13cfe" />

<img width="1918" height="1145" alt="image" src="https://github.com/user-attachments/assets/cb759102-1173-460c-8d5f-64327ba23740" />












---



## Result

The **switch-press counter was successfully maintained inside the GPIO ISR**, and the updated count was periodically transmitted through **UART from the main loop**. The counter displayed on **PuTTY** matched the number of valid switch presses, confirming reliable **data exchange between the ISR and the main program** without performing UART communication inside the ISR.
