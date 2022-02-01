# RF Low Noise Amplifier Design and Analysis

This project outlines the design and implementation of the RF low noise amplifier (LNA) and the amplifier itself is intended for use as a frontend amplifier. As the front end of a receiver the amplifier input will be a relatively small current that must be amplified into a useable voltage signal while increasing SNR as much as possible.

#### LNA Schematic
![lna](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/12f24fcd7f765fb7e83095fde01a236c59638f23/Full%20sc.PNG)

## Mactching network design

To begin the matching network design, the input matching network was prioritized as this stage is the most important when it comes to noise figure. To determine what input impedance was necessary for the transistor, noise figure circles were plotted for the device at 10GHz, and the input impedance was then matched close to the center of the NF circles.

#### Input Stage Noise Figure Circles
![Input Stage Noise Figure Circles](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/aa6125749a10645aeedc8e35a16a8555db4dae51/Capture.PNG)

#### LNA Output Return Loss
![Output Return Losst](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/677c6341c9abdfe123e23d62d163b5e3d96a8ecd/123444.PNG)

## Circuit Stability
In order to guarantee the amplifiers operation over the desired frequency range, we want to guarantee each stage is unconditionally stable over the frequency range (0.1-20GHz). This was done by analyzing the stability circles (input and output) of each stage. Initially without any feedback methods in place neither stage was unconditionally stable over the frequency range, so an RC feedback network was added. The capacitor value was chosen to be 20pF, large enough to not change the input and output impedances too much, but still block dc from passing. For both stages a 600 ohm resistance seemed to be the best compromise to get unconditional stability while maintaining proper noise figure and gain performance. The addition of the feedback network did not change the necessary input impedance by a meaningful amount, however the output impedance did need to be changed slightly. The change was fairly small so the MWO circuit tuner was used to change the output networks to get a proper match once again after the addition of the feedback network.

#### Input Matching Network Input Stability Circles
![Input Matching Network Input Stability Circles](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/677c6341c9abdfe123e23d62d163b5e3d96a8ecd/imnisc.PNG)

#### Input Matching Network Output Stability Circles
![Input Matching Network Output Stability Circles](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/677c6341c9abdfe123e23d62d163b5e3d96a8ecd/imnosc.PNG)

#### Output Matching Network Input Stability Circles
![Output Matching Network Input Stability Circles](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/677c6341c9abdfe123e23d62d163b5e3d96a8ecd/omnisc.PNG)

#### Output Matching Network Output Stability Circles
![Output Matching Network Output Stability Circles](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/677c6341c9abdfe123e23d62d163b5e3d96a8ecd/omnosc.PNG)


## Circuit Performance
After finalizing the design and stability of the circuit, the performance was characterized using MWO simulations for each of the specifications The first simulation in figure 14 run shows the amplifier s-parameters as well as noise figure over the amplification frequency range. 

#### Relevant Amplifier S-parameters and NF
![Relevant Amplifier S-parameters and NF](https://github.com/yichienchiang/RF-Low-Noise-Amplifier/blob/677c6341c9abdfe123e23d62d163b5e3d96a8ecd/Full%20LNA%20graph.PNG)























