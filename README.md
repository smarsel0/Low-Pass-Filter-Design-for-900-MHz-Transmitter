# Low-Pass Filter Design for 900 MHz Transmitter (AWR Design Environment)

Design, optimization, and layout of a **7th-order Elliptic Low-Pass Filter (LPF)** specifically engineered for FPV (First-Person View) drone video transmitters. The project focuses on the suppression of spurious signals in the **GPS (1.5 GHz)** and **Wi-Fi/Remote Control (2.4 GHz)** bands while ensuring minimal insertion loss at the 900 MHz operating frequency.

## Design Specifications
The filter was developed to meet the following RF performance requirements:
*   **Passband**: DC to 1 GHz.
*   **Insertion Loss**: < 0.75 dB (Minimized for efficiency).
*   **Return Loss**: > 15 dB (Maximized for impedance matching).
*   **GPS Rejection**: > 10 dB @ 1500 MHz.
*   **Wi-Fi/RC Rejection**: > 20 dB @ 2400 MHz.
*   **Form Factor**: Compact rectangular size (< 125 x 125 mm²).

## Methodology & Workflow
The design utilizes a transition from ideal mathematical models to physical microstrip implementation:

1.  **Ideal Synthesis**: Initial topology selection of a 7th-order Elliptic filter to leverage transmission zeros for precise frequency rejection.
2.  **iFilter Implementation**: Synthesis of the L-C lumped element prototype using the AWR iFilter tool.
3.  **Optimization**: Definition of *Optimizer Goals* to align transmission zeros exactly at 1.5 GHz and 2.4 GHz while optimizing Return Loss.
4.  **Distributed Elements Conversion**: Transformation of lumped components into real microstrip lines using the **TXLine** calculator.
5.  **Physical Integration**: Implementation on **FR-4 sustrate** ($\epsilon_r = 4.2$, $H = 1.6$ mm, $t = 35$ µm).

## Tools Used
*   **AWR Design Environment**: Microwave Office for schematic design and electromagnetic simulation.
*   **iFilter Synthesis**: For rapid filter prototyping.
*   **AWR Optimizer & Tuner**: For iterative performance refinement.
*   **TXLine**: For accurate physical dimension calculations of transmission lines.

## Final Performance (FOM)
| Specification | Achieved Value | Status |
| :--- | :--- | :--- |
| **Return Loss (S11)** | 29.69 dB | Pass  |
| **Insertion Loss (S21)** | 0.6433 dB | Pass  |
| **GPS Rejection (@ 1.5 GHz)** | 64.41 dB | Pass  |
| **Wi-Fi Rejection (@ 2.4 GHz)** | 61.36 dB | Pass  |
| **Physical Dimensions** | 53.05 x 17.26 mm² | Pass  |
