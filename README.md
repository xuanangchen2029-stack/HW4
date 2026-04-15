# HW4 - SSD1306 OLED with Pico 2 / 2W

Put these files in your HW4 folder:
- HW4_main.c
- ssd1306.c
- ssd1306.h
- font.h
- CMakeLists.txt

## Wiring
- Pico 3V3(OUT) -> OLED VDD/VCC
- Pico GND -> OLED GND
- Pico GP0 / I2C0 SDA -> OLED SDA
- Pico GP1 / I2C0 SCL -> OLED SCL
- Add a 10k pull-up resistor from SDA to 3.3V
- Add a 10k pull-up resistor from SCL to 3.3V
- Pico GP15 -> heartbeat LED -> 330 ohm -> GND
- Pico GP26 is ADC0 input

## What the code does
- Initializes I2C and the SSD1306 display
- Blinks a Pico heartbeat LED at 1 Hz
- Blinks one OLED pixel at 1 Hz
- Implements drawChar(x, y, c)
- Implements drawMessage(x, y, message)
- Reads ADC0 on GP26 and prints the voltage
- Prints the display fps at the bottom of the screen

## Notes
- Keep the heartbeat LED in the code so you can tell if the Pico freezes because of I2C desynchronization.
- The SSD1306 sample code stores the screen contents in a 513-byte buffer and only updates the display when ssd1306_update() is called.
