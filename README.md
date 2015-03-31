# Adafruit_SSD1306MOD library for Arduino
A mod for SSD1306 based on Adafruit_SSD1306 by Lady Ada.

Why a mod?????
The reason for modyfying the excellent Adafruit_SSD1306 library is Ram, or rather the lack of it. The original code requires at least 512 (for 128x32 display) / 1024 (for 128x64 display) bytes of memory in order to buffer the display. Of course, this way you also get the possibility to draw graphics using the Adafruit graphics library. However this mod forgoes the ability for graphics drawing as it adopts a character generator approach. That is instead of buffering the display, we have a buffer of 128 bytes that can hold 16x8 = 128 characters (the character size is 8x8 pixels). The library with the current font provided supports an ascii - like font. The character code is 8 bit, and the most signifigant bit is an inverse video attribute. 
To illustrate this, if you set charbuffer[0] to 65 you should get an A on the top left of the oled screen.
if you set charbuffer[0] = 65 | 128 then you should get an inverse video A. The built- in font has also various symbols in ascii codes 0-31 which are normally reserved for special characters. Some of the symbols are block graphics and combining them with the reverse video support you can create block graphics or big character displays. The library currently works only for 128x64 oled displays and SPI interface because I don't have an I2C or 128x32 oled display.

