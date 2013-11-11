FastLED
=======

This is a library for easily & efficiently controlling a wide variety of LED chipsets, like the ones
sold by adafruit (Neopixel, LPD8806), Sparkfun (WS2801), and aliexpress.  In addition to writing to the
leds, this library also includes a number of functions for high-performing 8bit math for manipulating
your RGB values, as well as low level classes for abstracting out access to pins and SPI hardware, while
still keeping things as fast as possible.

We have multiple goals with this library:

* Quick start for new developers - hook up your leds and go, no need to think about specifics of the led chipsets being used
* Zero pain switching LED chipsets - you get some new leds that the library supports, just change the definition of LEDs you're using, et. voila!  Your code is running with the new leds.
* High performance - with features like zero cost global brightness scaling, high performance 8-bit math for RGB manipulation, and some of the fastest bit-bang'd SPI support around, FastLED wants to keep as many CPU cycles available for your led patterns as possible

## Simple example

How quickly can you get up and running with the library?  Here's a simple blink program:

	#include "FastLED.h"
	#define NUM_LEDS 60
	CRGB leds[NUM_LEDS];
	void setup() { FastLED.addLeds<NEOPIXEL, 6>(leds, NUM_LEDS); }
	void loop() { 
		leds[0] = CRGB::White; FastLED.show(); delay(30); 
		leds[0] = CRGB::Black; FastLED.show(); delay30);
	}

## Supported LED chipsets

Here's a list of all the LED chipsets are supported.  More details on the led chipsets are included *TODO: Link to wiki page*

* Adafruit's Neopixel - aka the WS2812B (also WS2811/WS2812, also suppored in lo-speed mode) - a 3 wire addressable led chipset
* TM1809/4 - 3 wire chipset, cheaply available on aliexpress.com
* TM1803 - 3 wire chipset, sold by radio shack
* UCS1903 - another 3 wire led chipset, cheap
* LPD8806 - SPI based chpiset, very high speed
* WS2801 - SPI based chipset, cheap and widely available
* SM16716 - SPI based chipset
* DMX - send rgb data out over DMX using arduino DMX libraries

## Supported platforms

Right now the library is supported on a variety of arduino compatable platforms.  If it's ARM or AVR and uses the arduino software (or a modified version of it to build) then it is likely supported.  Note that we have a long list of upcoming platforms to support, so if you don't see what you're looking for here, ask, it may be on the roadmap (or may already be supported).  N.B. at the moment we are only supporting the stock compilers that ship with the arduino software.  Support for upgraded compilers, as well as using AVR studio and skipping the arduino entirely, should be coming in a near future release.

* Arduino & compatibles - straight up arduino devices, uno, duo, leonardo, mega, nano, etc...
* Teensy 2, Teensy++ 2, Teensy 3 - arduino compataible from pjrc.com with some extra goodies (note the teensy 3 is ARM, not AVR!)

What types of platforms are we thinking about supporting in the future?  Here's a short list:  MSP430, ChipKit32, Maple, Beagleboard

## What about that name?

Wait, what happend to FastSPI_LED and FastSPI_LED2?  The library was initially named FastSPI_LED because it was focused on very fast
and efficient SPI access.  However, since then, the library has expanded to support a number of LED chipsets that don't use SPI, as 
well as a number of math and utility functions for LED processing across the board.  We decided that the name FastLED more accurately
represents the totality of what the library provides, everything fast, for LEDs.

## For more information

Check out the official site http://fastled.io for links to documentation, issues, and news


*TODO* - get candy

