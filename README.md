# IR-Remote-Tester-and-Decoder
----------------

[![g0SWwadlrkk](https://img.youtube.com/vi/g0SWwadlrkk/0.jpg)](https://www.youtube.com/watch?v=g0SWwadlrkk)

What do you generally do when your remote controls starts playing up?
	Do you generally use a multimeter and check the voltage and current produced by the battery?
	Or do you point the remote control to a digital camera and try to visualize the infrared light? 
In this video, I am going to show you guys how to create a simple InfraRed(IR) Receiver Circuit using TSOP4838 and will also show you how to read the code send by the remote controls. You can also use this circuit as an IR remote tester.



Setup Without Arduino 
---------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizyzkYTKO7xy2c91MwYUEZjsLpF7InDchuIhIwzN0KlCxxrMBKBt70j5TE2Z454KfYU50PPYnKmI329lJ6-yqVvcx4ATXuzFSf8B0Um5KvdZqLO8VbCbxNXZJgvC1mZqZrgOZtrJXr0g4YNt1BOyr2AegKvYXJrwNVhGZcvSijqRhRheSF2EeyofeX/w640-h202/5.png)

Lets first have a look at the setup without an Arduino.
The main component of this circuit is the Infrared Remote (IR) Receiver TSOP4838.
The TSOP4838 is tuned to 38kHz, which is typically the frequency range of the TV remote controls. 

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgyxkPYxVjSyKvkm4LnBpKNOrYEOnsDr9iTl0ZLciSiJZQy2N2cjwJrjxVuCIYDl4I71DI4ZSVlTuOQ5QY6x0uDSxs1OOYcsGG5Xe3scZME6Yv6z1hnudUFUucquknjgDk1f5j4IWyih3nl4qBhgzqBuyBsi_KUxIWOS5idurwMl1bXxWTNWOvLnkHZ/w640-h360/6.png)

From left to right Pin-1 is the OUTput pin, Pin-2 is GND and Pin-3 is VCC. Just remember, the pin assignments can be different depending upon the TSOP variant. So, please be very careful while hooking it up to your circuit.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEid2ujx73aqSrrBmo_6dJh3daSOkM_ie0PKGzfFY1i8dYQp8EQVp7gZfNBGqp0ldP8Fz-Ku3KFJak5ZVQsh81BMoJWH2eLcbpcw2GIwNK1SYlhkqW2BtBKRpeupFnOxyekdTqG1R_MhE2yGEiN7ZudF0FqlylfD7Ee6Y_EJvrrptnkWDjiIvHURObSa/w640-h360/7.png)

Now, lets have a look at the setup.
Connect Pin-2 of IR Receiver to the -ve and Pin-3 to the +ve terminal of the battery.
Then connect the -ve pin of the LED to Pin-1 of the IR Receiver and the +ve pin to the +ve terminal of the battery by placing a current limiting resistance in-between.
To reduce the flickering rate of the LED, you can add a capacitor anything between 10mfd to 100mfd between Pin-3 and VCC of the circuit.
That's it, as easy as that.


Demo Without Arduino 
--------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjp4qcEeRPpFu--HUgg4G-NodwZOuqsfni76Z0HMS_QbLYJsNlkYPpx1WLi1V8sE-MoxgpXIwYYWxSdxVyswoYVsBArkUhjDMFHyRPDuE8oj49f-Ch31cexXKxXUqNwL1Fp7xwUwKMN_nPo6BL2IpsyNaa1wLHTFUOBJsEUZnOR_9j_9BFkR2w3zs1t/w640-h360/8.png)

Now, lets do a quick test.
As you can see, when I press any button on the the remote control the LED starts flickering.
TSOP4838 demodulates the signals received from the remote control and gives the output in the form of active low to the LED.
Adding a capacitor will lower the flickering rate of the LED.
The supply voltage has to be strictly between 5V-6V.



Setup Using Arduino
-------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhHJLlcdGbytVvqUcPfhW79NB_m8nOC6dIeP6XZ1r69BSu53_gcWBfFGYg-5IWADjvsmEZ_J6ltSTnj-XeBiLts_K6C070zxBxqNA4oQMyVe4arLNGt6xTXSVTVLFDZrkdhfIRBZpQdyEqAhlbsWFGNrzc-X1e6gAHC6KGxAKImU2HbMnCS1vL0UXnD/w640-h202/9.png)

Now, lets set this up using a MicroController and try to read the demodulated signals.
Connect the +ve pin of the IR Receiver to 5V, -ve to GND and the OUT pin to Pin-2 of the Arduino.
You can also add the optional LED to this setup to get a visual effect when the Receiver decodes the signal. 

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhbJqpe_Pu-w3R9mozaTmhkz30c5GTkQJ9DKn90SGBSzwx4mUuyEn4r_aAwCXHMLgiAihSYjk-KKbrBvzyXpSEfcV16DZALZZWHiebGoGtyJgfvm_yYzXJSEpoaVWHvDzZWnmPHRI4_14SQgQJzVGkejG76g9cnX_FPX8WQ2aJhMsAgsS6NaAuVdl7i/w640-h360/11.png)



The Code
--------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhz97Ab2aMn4dYQYf3qIDXrPwEkwUxVlhpEnuXGRFCSuyGWQI8Hvu8Qlc9rmfTFkRvQVpnhmN5uIZVqlLB2tv5NbSxvhTq-Z5r0pqUsSQemeiTA4GIrJQpscCvFoBgzGV6BgU88QXoixHERI6uJW7BZ1Jc_GVl4aRne2Uoa2ld-jjdBtVPpD7rsGnCD/w640-h360/12.png)

Now, go ahead and launch Arduino IDE and go to "Tools" > "Manage Libraries".
Download and Install the latest release of the "IRremote" library from the library manager.
Then, go to "Examples" and open the "SimpleReceiver" example. Go ahead and load the code without making any modification to the Arduino Board.


Demo Using Arduino
------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgG9osT50Z2OLq6M6YGASjTk-srPeCz9uV5VGc-Y-rm20EnQTAKQwuMVjdKE8vtioGsLY9J3K99VpTiJnZWs60vNwjqpeJF4IdvqbxgS4Ox8nUjgUE4EQmKlboOHmxpjDXlB8bPQ9JeKc_uY7MiW76e4p4HBTsMz24X5UlhEUzvP8-5b8tUnwgPRulJ/w640-h360/13.png)

For this demo, I am using a Panasonic and a Sony remote control. The decoded data will be shown using the Arduino IDE's Serial Monitor.
As you can see when I press a button on the remote control, the LED lights up and the decoded data is displayed on the serial monitor.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhEAkXf7GaonI94QAlFt0d2j3O6TcVtUhMO2sAedyTuXoflHMHfll6hMr74OrdU1oeLkByU9VLPkfdB4Bw1bxcnBEz0ExJ0-oXDfFpp5VyVrd-lTgKDwaf_c4TVyvmXnbu3qY_M7PMV6KyJz0XKEGoR6eUP6nw2aTG9oth7WleANrAtKe8zrzyBkREy/w640-h360/14.png)

The serial monitor displays a lot of information, but the one of my interest is the "Source" and the "Command" send by the remote control.




Uses
----

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhscaa4JHL2_5DfbBguF3qQKIAiQ_pdLPQq2S2uchXcfI_dEwrTH3LWmcR1_ezaY79JSudPVMjycF0cWqFcVMi8ljk_ysSL5pU3Ha5zWwjqTglF3TmGmBpFpWcd8kXB1w5U6B7dz--TMl-RRVeWqsHsixm6WeEFYqN2MXAEeF2OltYCk5UJyi4V2Rl0/w640-h360/15.png)

Some common uses of this project includes:
*	Controlling devices using a remote control
*	Decoding data sent over IR
*	Troubleshooting remote controls 
*	Lighting up LED strips near your TV whenever you press a button on the remote control



Thanks
------

[![g0SWwadlrkk](https://img.youtube.com/vi/g0SWwadlrkk/0.jpg)](https://www.youtube.com/watch?v=g0SWwadlrkk)

Thanks again for checking my post. I hope it helps you.
If you want to support me subscribe to my YouTube Channel: https://www.youtube.com/user/tarantula3

Video: https://youtu.be/g0SWwadlrkk
Full Blog Post: https://diyfactory007.blogspot.com/2022/11/IR-Remote-Tester-Decoder.html
Datasheet: Download 


Support My Work:
BTC:  15cNh9hup8jidCVPwa1DTcxeoh2FPijVrX
LTC:  LbquH9Ku78vHtcm3LZnWXpD1JQWdKzeV4v
DOGE: DEB2QBAihnBRhGsaB8P7kz559TDiucQhX6
ETH:  0x5d8c9ba0e54d8354d4af81871db26daa190d2194
BAT:  0x939aa4e13ecb4b46663c8017986abc0d204cde60
LBC:  bZ8ANEJFsd2MNFfpoxBhtFNPboh7PmD7M2
COS:  bnb136ns6lfw4zs5hg4n85vdthaad7hq5m4gtkgf23 Memo: 572187879
BNB:  0x5d8c9ba0e54d8354d4af81871db26daa190d2194

Thanks, ca again in my next tutorial.



Tags
----
Infrared Remote,TSOP4838,Breadboard,IR Remote Tester,how to make a simple remote control,IR Remote Decoder,Arduino decoder,arduino ir decoder,2 simple remote control testers,remote control testers,how to make a ir remote control tester,howtomake,how to make remotesensor,ir sensor homemade,proximitiy sensor,diy electronics,homemade circuits,simple electronics project,science project,line following robot sensor,remotester,circut projects,science of stupid,scienceproject,schoolproject,


