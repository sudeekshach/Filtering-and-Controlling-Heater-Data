<center><h1> FILTERING AND CONTROLLING OF HEATER DATA </h1></center>

<h3>Introduction</h3>

The project aims at designing a system that gives a controlled and filtered output. There are two different approaches used. The first approach is to filter the output obtained from a PID controller. The second approach is to give a filtered input to the PID controller, which gives the desired output.

<h3>Working</h3>

Fig 1 represents the Simulink model of the first approach. The input from the Arduino is collected using the analog input block. The data is then altered using gain and is then compared to a desired constant value. The obtained error signal is then given as an input to the PID controller.

![image](https://github.com/sudeekshach/Filtering-and-Controlling-Heater-Data/assets/130401019/d87cf42b-436b-44f8-8937-1535c81fa5c2)

Fig 1: Simulink model of the first approach

A proportional-integral-derivative controller is a feedback-based control loop mechanism employed in a wide range of applications that require modulated control. In this model, a PID controller is designed and tuned to obtain a faster response and to hold the heating system at the required temperature. The PID system is designed using three different blocks; a gain block, a discrete-Time integrator block and a discrete derivative block, that provide the Proportional, Integral and Derivative values to the system respectively.  Fig 2 represents the PID controller of the heating system.

![image](https://github.com/sudeekshach/Filtering-and-Controlling-Heater-Data/assets/130401019/62d59822-456d-4b73-81cd-692b7ccef56c)

Fig 2: PID controller

Filtering is generally used to remove the noises from a signal and to smoothen the data. In this model, the output signal of the PID controlled heating system is filtered using a Low-pass Butterworth filter, which smoothens the output signal. The filter is designed using a digital filter designer, which is used to design filters according to the requirements. Fig 3 represents the filter that is used to refine the output temperature signals.

![image](https://github.com/sudeekshach/Filtering-and-Controlling-Heater-Data/assets/130401019/8de7e2e2-183b-4e87-acca-22332704a461)

Fig 3: Digital filter block

<h3>Second Approach</h3>
The model can be designed using a different approach. The filter can be used to filter the input data from the Arduino. The filtered input obtained can be given as an input to the PID controller.

![image](https://github.com/sudeekshach/Filtering-and-Controlling-Heater-Data/assets/130401019/b87a0484-4f75-47ce-a52a-dac2fa35f92e)

Fig 4: Alternative Simulink model for filtering and controlling Heater data

<h3>Simulation</h3> 
The designed Simulink model is deployed onto Arduino Leonardo, which has a temperature control system connected to it. The data is sent and received by the Arduino using serial communication. The output obtained after the simulation of the model is a PID controlled and filtered temperature signal. The output temperature data is shown in Fig 5.

![image](https://github.com/sudeekshach/Filtering-and-Controlling-Heater-Data/assets/130401019/47354e94-89d0-4043-8369-6457ffa48dea)

Fig 5: Output temperature data graph representing unfiltered and filtered data

The output obtained by simulating the Simulink model in Fig 4 will give a filtered and controlled output as shown in Fig 6.

![image](https://github.com/sudeekshach/Filtering-and-Controlling-Heater-Data/assets/130401019/2332833c-dbb9-4957-80e5-c64ae5aea24e)

Fig 6: Control signal and Output data graph for second approach


