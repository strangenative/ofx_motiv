MOTIV Alpha
========

Version 0.1.10 - Sat 25 Feb 2012

by Russ Maschmeyer  
<http://musicwithmotiv.com/>


Introduction
------------

MOTIV is an open source project that uses Kinect to give digital musicians direct control of emotional expression by interpreting their physical gestures in real-time. It consists of three key parts:

  1 An openFrameworks based Kinect program that uses your movement to output
    values for tempo, velocity (loudness), and intensity (instrumental
    layering).

  2 A Max/MSP patch which receives the tempo, velocity, and intensity values 
    from openFrameworks and adjusts a pre-composed MIDI file (your song) in
    real-time to emotionally match your movement, then outputs the adjusted 
    MIDI.

  3 An Ableton Live demo set which takes the real-time MIDI and runs it 
    through virtual instruments to create the final sound that reaches your 
    audience.

More information about this project can be found at www.musicwithmotiv.com


Requirements 
------------

I created and ran MOTIV on a MBPro 2.66 Ghz Intel Core 2 Duo with 8GB of RAM running Mac OS X Version 10.6.8 (Snow Leopard). I'm sure you could run this on less, but a Mac is probably essential.

Max/MSP requires that all MIDI songs must be broken up into individual MIDI tracks for each instrument. Max/MSP currently doesn't have a MIDI parser that can handle multi-instrument MIDI files. The demo song included is broken up into three MIDI files: a piano track, a drum track, and a strings track.


Installation and Setup
----------------------

OpenFrameworks Installation

For now, you'll need XCode (https://developer.apple.com/xcode/). Plug in your Kinect and run the xcodeproj app located in: 'ofx_motiv/openFrameworks/apps/myApps/MOTIV_0.1.10/opennisample.xcodproj'

It will probably throw a few errors, and this is where MOTIV needs help from real developers… 

MOTIV was developed with openFrameworks after installing a number of Kinect driver libraries which failed. Sooner or later, 'it just worked.' Others shouldn't have to follow the same frustrating path. Developers: try giving installation a shot and put together instructions as you go, including any additional required libraries and where to find them. The error trail should indicate what's required. You'll be doing everyone a GREAT favor!

When you get the openFrameworks application to compile, you should see your silhouette as you step in front of the Kinect camera. This means You're ready to start streaming real-time values to Max/MSP!


Max/MSP Installation

  I.   Download the MOTIV Starter Package at: 
       http://www.musicwithmotiv.com/downloads/motiv_starter_package.zip.

  II.  Download and install Max/MSP. You can get a free trial version at 
       http://cycling74.com/. 

  III. Open 'motiv_starter_package/Max Patch + MIDI files/MOTIV-
       DEMO.maxpat' in Max MSP. There are a couple things you'll want to 
       set in the main window that opens up:

       a. Set the 'CTRL out' to 'MaxMSP 2' and the 'MIDI out' to 
          'MaxMSP 1'. These are the outputs for your MIDI and instrument 
          control signals.

       b. Set the 'Original Tempo' of your song (the included demo is 
          61 bpm)

       d. Turn on a channel for each instrument in the song and select 
          your MIDI files. For the demo song, there are two main MIDI
          files: 'demo-piano' and 'demo-drums'. Add these to instruments 
          1 and 2, and set the channels to 1 and 2 respectively.

       c. Turn on the parameters you want to control (Tempo, Velocity,
          Intensity). When you turn on 'Intensity' you'll be prompted to
          add a MIDI file three times: one for each level of intensity. 
          For the demo, just add the 'demo-piano' MIDI files three times. 

Ableton LIVE Installation

OpenFrameworks and Max/MSP are required at this point for MOTIV, but you're welcome to use any virtual instrument software you like. It just needs to be able to do is take in MIDI and output a sound. I tried both Logic and Ableton. Both worked, but Ableton was far less buggy than Logic.

  I.   Download and install Ableton Live

  II.  Open the 'motiv_starter_package/Ableton Virtual Instrument/MOTIV-
       DEMO.als' Ableton Live Set. Ableton requires no further setup!

Putting It All Together

  I.   Make sure you've got Max/MSP set up and the Ableton Live Set open

  II.  Turn your computer's volume 'up to 11'

  III. 'Build and Run' the openFrameworks application

  IV.  Stand about 6-8 away from the Kinect and register your body with 
       the indicated pose.

  V.   Touch the green 'Start' button with your hand and you're off!

To reset the application, touch the 'Stop' button at any time and then touch 'Start' again


Bugs
----

To file bug reports or feature requests please send email to:
<russ@musicwithmotiv.com>.


Version History
---------------

Alpha Version 0.1.10 - Sat 25 Feb 2012


GNU General Public License
--------------------------

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.