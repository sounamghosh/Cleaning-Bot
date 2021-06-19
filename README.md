
# Automation and Controlling of Automatic Floor Cleaner
##### By Pronoy Kumar Karmakar, Rahul kumar, Chandni Kumari and Sounam Ghosh

Traditionally floor is cleaned with the help of dry mop or wet mop using the hand as a potential tool. They have to scrub hard on the surface. The cleaning includes cleaning of various surfaces basically cement floors, highly polished wooden or marble floors. Among these floors the rough surface floor such as cement floor, mostly present in semi urban areas are covered with so much dust.
From early human civilization human is increasingly dependent on the machines. Human is trying to reduce the workload upon himself. By the help of machines also we can get huge efficiency because there is no chance of human error there. Now -a -days from 30 years intelligence and robotics growing with a vast pace. Every human is using 2-3 robot at least per day. If we look at past 30 years we will see robotics from large structure going to small and smaller in Nano range. Very complicated sensors have been designed to help the robot in various works .Complicated pneumatic and actuating systems have been designed. One of the best examples is the mobile phone. If we look at the floor cleaning robot we can see iRobot is dominating the market with its 90 sq. cm robot having indoor navigation as its principal controlling system. Also for many in-house mobile robots indoor navigation is a big issue. Also currently indoor GPS is evolving which uses unsupervised learning and determining its path in its first run. Since now indoor navigation has not been solved completely. Also now-a-days complicated artificial intelligence algorithms like unsupervised and supervised learning, Swarm optimization, ANT algorithm, natural heuristic search are playing a major role in designing control system of the most of the mobile robot [10].
	
## BODY
The body of the robot has many small components. Like all robots it has sensors, microcontrollers and actuators and other components. It has 2 vacuum pumps connected in backside as well as front side of the robot. A 300 rpm DC motor is connected in the middle of the robot with the scrubber. A bearing is attached to the axle of the scrubber. 2 DC motors of 100 rpm are connected to the wheels. One microcontroller with 4 ultrasonic sensors is attached to it. This has 2 bread boards for circuit connection which ultimately can be replaced after welding.
 
For scrubbing we are using the brushes instead of cloths .The scrubber rotates at very high speed which performs very good mopping action.
## NAVIGATION SYSTEM
Navigation system of the robot is basically dependent on the sensors and microcontroller and algorithm fed to it. Basically the data acquisition system (here sensor) first collects the data from the environment and feeds to microcontroller .The microcontroller uses 2 algorithms. The 2 algorithms are:-
	Spiral motion algorithm
	Random Straight path following
## SPIRAL MOTION
Basically after sensing the obstacle distance from outside environment, if the robot has sufficient space on its 4 sides it will move in spiral path at first half of its running. The spiral path can be anti-clockwise and clockwise .The spiral path can be generated by the decreasing ratio of left motor encoder and right motor encoder [1].
## RANDOM STRAIGHT PATH
Basically random straight path searches from one node to another by the help of natural heuristic search. After the spiral motion the robot if detects a collision then it follows the edge of the wall until it gets enough free space for spiral motion again. After some moment if it doesn’t get any specific clear area for spiral motion then it will move in random path for some time and the obstacle detection and avoidance system will be carried out by the help of ultrasonic sensors [2]. After that robots stop rotating if the timer is over. In this process we can divide a particular area in the floor as grids and move accordingly so that it will have very confine control over the robot. So it will have grid based search over the floor for movement [4].
Finally we implemented computer vision by the help of ultrasonic imaging and analyzing the image for the dust particles by the help of supervised learning and clustering the data [5]. We have implemented here A* search algorithm for motion planning [7]. The breadth first search implemented here is very effective and provides efficient result for moving [9].

##  AUTOMATION AND CONTROL OF MOBILE ROBOT
## 	AUTOMATION
We have to automate the robot so that it will roam freely on the floor avoiding all the obstacles. We have to also provide a microcontroller in which we have to feed the code so that it will work as a brain of the robot. Also we have to give a proper power source and proper motor for regulating the sprinkling of the robot and motor driver for controlling the direction and speed of motor connected to wheel.

## 	SENSORS


This is an ultrasonic sensor of 40 kHz frequency specification. It requires power supply of 5 volt with working current specification as 15 mA .It detects around 13ft of distance. It triggers the pulses in the interval of 10 us. It has 4 terminals namely Vcc,trig,echo and GND pin . Vcc = 5v
Trig pin =connected to Arduino board PWM pin Echo pin = connected to Arduino
GND = negative terminal
 
Through trig pin we set the pulses and emit it to the environment and after emitting square waves the signals are received from the echo pin of this sensor module which ultimately fed to the Arduino board.

## 	ALGORITHM
### Random Straight Path Flow chart

![image](https://user-images.githubusercontent.com/66516162/122647699-27762400-d143-11eb-9caa-6b1fe94ea2d1.png)

### Spiral Path following flow chart

![image](https://user-images.githubusercontent.com/66516162/122647727-44aaf280-d143-11eb-931b-2bea73dff41a.png)


## Construction of ultrasonic sensor from transducer pairs

Ultrasonic range finder is a circuit for measuring distance by the help of ultrasonic sound. First the ultrasonic bust is transmitted from the transmitter and then receiver receives the ultrasonic burst. The ultrasonic sound velocity is known in the medium as
c = 331,3 (m/s) * (1+T/273)1/2
Actually the speed of sonic wave varies with respect to temperature of medium. Overall attenuation in air depends upon: geometric spreading, molecular relaxation, boundaries, and refraction by non-homogeneous atmosphere, and diffraction by turbulence, conduction and shear viscosity losses. Attenuation also varies with respect to distance travelled by the sonic wave. In this experiment we are using two transducers of 40 kHz. Transducer is a device which converts one form of energy to electrical energy and electrical energy to another form of energy. It carries a piezoelectric material which does these energy conversion.

TRANSDUCER PAIR:-

Between the two transducer pair one is transmitter and other is receiver.

![image](https://user-images.githubusercontent.com/66516162/122647782-83d94380-d143-11eb-83b8-b355ce48bfce.png)

Di = 0.5 * C * ( Tinitial-Tfinal ) (Where:
Di = Distance to Object
C = Speed of Sound
Tinitial = Time at which sonic wave is transmitted Tfinal = Time at which sonic wave is received)

## 	Transmitter circuit

![image](https://user-images.githubusercontent.com/66516162/122647838-d450a100-d143-11eb-84a5-12cb20b416ad.png)


## 	RECIEVER CIRCUIT

![image](https://user-images.githubusercontent.com/66516162/122647854-e8949e00-d143-11eb-8417-6eb4ad06afe7.png)

IN4148 – Diode UA741CP – opamp model
Gain in first stage of amplifier (approx.) = -20 log (R2/R1) = -20 log (80/1.2) = -36.92db
(Here R2 value taken as 80 kΩ approximately whereas real value of R2 is less as 80KΩ is connected to capacitor of value 33pF.So gain will be less. But it will provide frequency stability.)
So approximate gain from two stage = 36.92 + 36.92 = 72 dB
The 0.1 coulomb capacitor passes the signal having medium and high frequency signals.
Here 2 inverting opamps are used and combined stage has a voltage gain of 67 db. So after 2 succesive inversion the phase of signal doesn’t change. Here band pass filters are used with RC circuit where we pass high frequency signal into the circuit input. Band pass filter is centered on the frequency 40 kHz. The output voltage of the opamp is around 2.5 volt (Vcc/2).
 
For easier processing of the echo, a diode (IN4148), capacitor of 0.05uF and resistor of 10k ohm are used to demodulate the signal. A coupling capacitor (1uF) is used. This helps to get rid of demodulated signal of the DC component.

![image](https://user-images.githubusercontent.com/66516162/122647881-0d891100-d144-11eb-911d-b5a41b7a2bdf.png)
![image](https://user-images.githubusercontent.com/66516162/122647886-17ab0f80-d144-11eb-8999-541f035e0f34.png)
![image](https://user-images.githubusercontent.com/66516162/122647891-209be100-d144-11eb-85a8-72aefddd68a4.png)


## Commercialization possibility

Now in the automatic floor cleaner market iRobot and Scooba are playing major roles. They hold around 80% of the market. Their costs are around 25000 to 35000.Also the algorithms used by them are not most effective. They are using algorithms which approximately provides 70% accuracy. They are not using any image processing algorithms to run their robot. But the robot designed by us is cost efficient which will cost around 15000 .Also we can use camera lens for small dust particle detection, so that it will give more efficient decision in governing the motion of the particle which ultimately save considerable amount of power and reduce the timing with better efficiency and sensitivity. This will act like a pheromone like in ant algorithm.. In ant algorithm when pheromone density of ants in particular direction is denser all other ants follow that direction. Similarly when the robot will find the particular dust size on floor on one side of it and there are less on other 3 sides, it will head towards dusty area if obstacle is not present.
Time redundancy and power saving with low cost provides the best opportunity for marketing this consumer product.

## CONCLUSION

The Product developed is definitely a very important product in robotics and floor cleaning area .The robots developed uses 2 vacuum pump which ultimately provides lots of vibration and power loss in the system. Also the algorithm implemented is not very effective. So there is definitely current scope for improvement and optimization till the most effective product is being developed. After optimizing the algorithm and taking it to the heuristic based search like bee algorithm it will be a great product and can revolutionize this industry. Definitely it has very huge potential. Also we can use 1 vacuum pump instead two so that it will be cost effective and very energy saving product with less vibration and much control over the robot. The robot having 33*30*8 cm in dimension is very compact in nature and can go beneath any furniture and bed. This is also very handy in portability. The scrubber of the robot now consists of small plastic fibers .But it can be further improved so that the surface area of the scrubber will come 90% in contact with the floor.

## Acknowledgements

[1]	Razvan Solea, Adrian Filipescu and Grigore Stamatescu” Sliding-mode real-time mobile platform control in the presence of uncertainties ”,Decision and Control(2009) 32 16-18

[2]	T. Palleja,M. Tresanchez,M. Teixido,J. Palacin" Modeling floor-cleaning coverage performances of some domestic mobile robots in a reduced scenario", Robotics and Autonomous Systems(2010) 58 37- 45.
[3]	M.R.B. Bahara, A.R. Ghiasib, H.B. Bahara, "Grid roadmap based ANN corridor search for collision free, path planning ",Scientia Iranica (2012) 19 1850-1855.


[4]	Ayoub Bahmanikashkoolia , Majid Zareb, Bahman Safarpourc, Mostafa Safarpourd" Application of Particle Swarm Optimization Algorithm for Computing Critical Depth of Horseshoe Cross Section Tunnel "APCBEE Procedia( 2014)9 207–211


[5]	Spyros G. Tzafestas"9 – Mobile Robot Control V: Vision-Based Methods",Introduction to Mobile Robot Control(2014) 319–384

[6]	Spyros G. Tzafestas"11 – Mobile Robot Path, Motion, and Task Planning”, Introduction to Mobile Robot Control (2014) 429–478

[7]	Masoud Nosrati , Ronak Karimi , Hojat Allah Hasanvand “Investigation of the * (Star) Search Algorithms: Characteristics, Methods and Approaches” Applied Programming(2012) 2 251-256

[8]	Dr. R.Anbuselvi “PATH FINDING SOLUTIONS FOR GRID BASED GRAPH” Advanced Computing(2013) 4

[9]	Rina Dechter,Judea Pearl “Generalized best-first search strategies and the optimality of A*",Journal of the association of Computing Machinery(1985) 32 505-536

[10]	Ashraf A. Kassim, , B.V.K. Vijaya Kumar"Path planners based on the wave expansion neural network",Robotics and Autonomous Systems(1999) 26 1–22


  
