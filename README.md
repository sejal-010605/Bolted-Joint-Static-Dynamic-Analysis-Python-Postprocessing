# Finite Element Modeling of Bolted Joints – Python Post-Processing

Finite Element Analysis of threaded bolted joints under static and dynamic loading using ABAQUS, with automated Python-based post-processing to investigate fatigue resistance and anti-loosening performance.

## Institutional Information Request

Technical information from this project was requested by the **Indian Space
Research Organisation (ISRO)** in relation to the finite element modelling,
stress analysis, fatigue behaviour, and anti-loosening performance of the
threaded bolted joint.

The project was independently developed using **ABAQUS** and **Python**.

##  Project Overview

Threaded fasteners are widely used in critical engineering structures where fatigue failure and loosening under vibration are major concerns.

This project investigates a stress-guided geometric design approach for improving both fatigue resistance and anti-loosening performance of threaded fasteners. Instead of modifying the material or applying additional surface treatments, the study focuses on controlling the thread geometry through:

- **Thread pitch difference (α)**
- **Interference fit / interference volume (δ)**

Nonlinear finite element simulations were performed in **ABAQUS** to study stress and contact-stress distributions across the engaged threads. Python scripts were used for automated extraction, processing, and analysis of the simulation results.

##  Objectives

- Develop a nonlinear finite element model of a threaded bolted joint.
- Investigate stress concentration across engaged bolt threads.
- Study fatigue behavior under cyclic axial loading.
- Analyze anti-loosening behavior under transverse vibration.
- Investigate the effect of thread pitch difference (α) on stress distribution.
- Quantify the effect of thread geometry on fatigue life and frictional resistance.
- Automate ABAQUS result extraction and post-processing using Python.
- Identify a geometric configuration that provides a balance between fatigue resistance and anti-loosening performance.

##  Tools & Technologies

- **ABAQUS** – Nonlinear finite element modeling and simulation
- **Python** – Automated post-processing and data analysis
- **Numerical analysis** – Stress distribution, fatigue-life and contact-stress evaluation
- **Curve fitting** – Development of empirical relationships from FEA results

##  Methodology

The analysis was carried out through the following stages:

1. **Bolted Joint Modeling**
   - Developed the threaded fastener geometry.
   - Defined the relevant material and contact properties.
   - Incorporated nonlinear thread contact behavior.

2. **Static Loading Analysis**
   - Applied the required tightening/preload condition.
   - Evaluated axial stress and thread contact stress.
   - Investigated stress concentration among the engaged threads.

3. **Dynamic / Vibration Analysis**
   - Simulated the response of the threaded joint under vibration.
   - Evaluated the distribution of compressive contact stress between mating threads.
   - Related contact stress distribution to frictional resistance against loosening.

4. **Fatigue Analysis**
   - Investigated high-cycle fatigue behavior under cyclic axial loading.
   - Evaluated stress amplitude and corresponding fatigue life.
   - Used S–N relationships to compare different thread geometries.

5. **Parametric Study**
   - Varied the thread pitch difference, α.
   - Compared stress distributions, fatigue life and anti-loosening behavior.
   - Identified the pitch difference providing the best overall performance.

6. **Python-Based Post-Processing**
   - Automated extraction of relevant ABAQUS simulation results.
   - Processed stress and contact-stress data across thread turns.
   - Generated data for comparison of different geometric configurations.
   - Performed curve fitting and numerical analysis of the extracted results.

##  Key Parameters

| Parameter | Description |
|-----------|-------------|
| α | Thread pitch difference between bolt and nut |
| δ | Interference volume / interference fit parameter |
| σᵀ | Fatigue resistance / axial stress at thread root |
| σₙ | Normal compressive contact stress |
| N | Bolt thread number |
| Nf | Fatigue life |
| μ | Static friction coefficient |
| μeq | Equivalent friction coefficient |

##  Key Findings

### Stress Concentration

Finite element results showed that both fatigue-related axial stress and anti-loosening contact stress are strongly influenced by stress concentration at the first engaged thread.

The first engaged thread experiences the highest stress concentration, making it a critical location for fatigue crack initiation.

### Effect of Thread Pitch Difference

The pitch difference α significantly changes the distribution of stress among the engaged threads.

- At **α = 0 μm**, stress is highly concentrated at the first engaged thread.
- Increasing α redistributes the stress across multiple threads.
- Around **α = 8 μm**, the axial stress distribution becomes more uniform.
- Increasing α beyond 8 μm causes stress concentration to shift toward other engaged threads.

### Fatigue Performance

The fatigue-life analysis showed that fatigue life increases as α increases toward approximately **8 μm**.

The highest fatigue life was obtained at approximately:

**α ≈ 8 μm**

Beyond this value, fatigue performance decreases as new stress concentrations develop at other thread locations.

### Anti-Loosening Performance

Increasing α increases the distribution of compressive contact stress across the engaged threads.

A larger contact-stress region provides greater thread contact and therefore greater frictional resistance against loosening.

The anti-loosening performance continued to improve for pitch differences greater than 8 μm, unlike fatigue performance.

### Overall Design Insight

The study demonstrates a trade-off between fatigue resistance and anti-loosening performance.

A controlled thread pitch difference can redistribute both axial and contact stresses, allowing simultaneous improvement in fatigue resistance and resistance to loosening.

The study identified approximately **α = 8 μm** as the optimum pitch difference for maximum fatigue performance while providing significantly improved anti-loosening behavior.

##  Analytical Formulation

The project also investigated relationships describing:

- Thread stress distribution
- Contact stress distribution
- Equivalent friction coefficient
- Fatigue life
- S–N behavior
- Residual force after vibration

Polynomial curve fitting was used to represent the variation of stress across thread turns based on FEA results.

The equivalent friction coefficient was used to quantify the effective frictional contribution of the modified thread geometry.

##  Python Post-Processing

Python was used to automate the processing of ABAQUS simulation results and reduce manual extraction of data from multiple analyses.

The post-processing workflow includes:

```text
ABAQUS Simulation
       ↓
ODB / FEA Results
       ↓
Python Data Extraction
       ↓
Stress & Contact Stress Processing
       ↓
Thread-wise Data Analysis
       ↓
Curve Fitting / Fatigue Analysis
       ↓
Plots & Results
