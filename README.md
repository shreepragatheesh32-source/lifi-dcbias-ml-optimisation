# LiFi DCO-OFDM DC Bias Optimisation

**Domain:** Optical Wireless Communications | LiFi  
**Tools:** Python, NumPy, pandas, scikit-learn, PyTorch, Matplotlib, OptiSystem  
**Type:** Master's Research — Whitecliffe College, Auckland NZ (2025)

---

## Overview

This project investigates **DC-biased optical OFDM (DCO-OFDM)** for LiFi systems,
focusing on predicting the **optimal DC bias voltage** to minimise distortion and
maximise signal quality. A physics-based simulation generates a realistic 9,000-sample
dataset incorporating:

- 3rd-order LED nonlinearity
- Photodiode shot + thermal noise
- 50 Hz ambient lighting interference
- LOS + first-reflection multipath channel

![LiFi System Diagram](lifi_system_diagram.png)

---

## Research Question

> *Is it possible to predict the optimal DC bias voltage for a LiFi DCO-OFDM system
> from a set of measurable link features?*

---

## Machine Learning Models Compared

| Model | R² | MAE | RMSE |
|---|---|---|---|
| Linear Regression | 1.0000 | ~0 | ~0 |
| Ridge Regression | 1.0000 | ~0 | ~0 |
| Random Forest | 0.9998 | 0.0037 | 0.0049 |
| Gradient Boosting | 0.9998 | 0.0039 | 0.0049 |
| SVR | 0.9763 | 0.0361 | 0.0491 |
| Neural Network (MLP) | 0.9729 | 0.0434 | 0.0525 |

**Key finding:** SNR_dB (83.5%) and Clip_V (16.5%) are the dominant predictors
of optimal bias voltage.

---

## Files

| File | Description |
|---|---|
| `thesis.ipynb` | Full notebook — simulation, dataset generation, ML training & evaluation |
| `lifi_project.osd` | OptiSystem simulation project file (LiFi DCO-OFDM channel model) |
| `research_presentation.pptx` | 13-slide research presentation |
| `lifi_system_diagram.png` | LiFi system architecture infographic |
| `lifi_ofdm_dataset_realistic_9000.csv` | Base simulation dataset (9,000 samples) |
| `lifi_ofdm_dataset_realistic_9000_sweep.csv` | Dataset with bias sweep column |

---

## How to Run

```bash
pip install numpy pandas scikit-learn torch matplotlib
jupyter notebook thesis.ipynb
```

> Note: `.osd` file requires [OptiSystem](https://optiwave.com/optisystem-overview/)
> to open the simulation model.
