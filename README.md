# 3 DB ATTENUATOR

# INTRODUCTION:
A 3 dB attenuator is a passive RF / microwave circuit used to reduce signal power by 3 decibels, i.e., to one-half of its original power level. It is widely used in communication, measurement, and microwave systems to control signal levels, protect sensitive devices, and improve impedance matching.

A 3 dB attenuator can be implemented using different resistor networks (L-pad, T-type, Π-type) designed for a given characteristic impedance (usually 50 Ω or 75 Ω). Like the Standing Waves & SWR report in your EMT&TL material, this document explains the basic theory, design equations, measurement techniques, applications, and key references




# OVERVIEW:

# 3 dB Attenuator (50 Ω System)

This repository documents the theory, design, and applications of a **3 dB attenuator** for a **50 Ω RF system**.  
A 3 dB attenuator is a passive network that reduces signal power by **half** while maintaining the characteristic impedance at both ports.

---

## 1. Basics of Attenuation

For an RF/microwave system with characteristic impedance \( Z_0 \):

- **Power attenuation (in dB)**  

  \[
  A_\text{dB} = 10 \log_{10}\left(\frac{P_\text{in}}{P_\text{out}}\right)
  \]

- **Voltage attenuation (in dB)**  

  \[
  A_\text{dB} = 20 \log_{10}\left(\frac{V_\text{in}}{V_\text{out}}\right)
  \]

For a **3 dB attenuator**:

- Power ratio  

  \[
  \frac{P_\text{out}}{P_\text{in}} = 10^{-3/10} \approx 0.5
  \]

- Voltage ratio (for matched impedances)  

  \[
  \frac{V_\text{out}}{V_\text{in}} = 10^{-3/20} \approx 0.707
  \]

So a 3 dB pad is commonly referred to as a **half-power attenuator**.

---

## 2. Voltage Ratio and Design Factor

Define the **voltage attenuation factor**

\[
K = \frac{V_\text{in}}{V_\text{out}} = 10^{A_\text{dB}/20}
\]

For \( A_\text{dB} = 3 \):

\[
K = 10^{3/20} \approx 1.4125
\]

All resistor calculations below assume:

- \( A_\text{dB} = 3 \) dB  
- \( Z_0 = 50\ \Omega \)  
- \( K \approx 1.4125 \)

---

## 3. L-Pad 3 dB Attenuator (Asymmetrical)

The **L-pad** uses one series and one shunt resistor. It is typically used when the **source** and **load** impedances are known and may be equal or unequal.  
Here we design for equal 50 Ω source and load.

### 3.1. Topology

```text
Vin ---- Rs ----+---- Vout
                |
                Rp
                |
               GND

