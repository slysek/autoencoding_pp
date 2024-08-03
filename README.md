# Double Higgs-boson Signal Strength Measurement in the Multi-leptons Production Channel in the ATLAS Experiment

## Overview
This project focuses on measuring the signal strength of double Higgs-boson production in the multi-leptons production channel, specifically within the ATLAS experiment. The primary challenge in this analysis is the separation of signal events from background noise, which is critical due to the small cross-section of signal events and the significant background, primarily from WZ (VV) bosons.

## Motivation
The 2lSC+1τ channel has been identified as having low significance in previous analyses. This is mainly due to two factors:
- **Small Statistic of Signal Events**: The cross-section for these events is quite small, leading to limited data.
- **Irreducible Background**: Most background noise originates from WZ (VV) boson production, which is difficult to separate from the signal.

To address these issues, this project aimed to develop a new method for signal and background separation using advanced machine learning techniques, specifically focusing on outlier detection with autoencoders.

## Methodology
### Outlier Detection with Autoencoders
Autoencoders are a type of neural network used to learn efficient representations of data, typically for the purpose of dimensionality reduction or noise filtering. In this project, we employed an autoencoder to differentiate between signal and background events by learning to minimize reconstruction error. The autoencoder compresses the input data, captures its essential features, and then reconstructs the data, allowing us to identify anomalies and reduce noise.

#### Autoencoder Architecture
- **Input Layer**: 183 variables
- **Encoding and Decoding Layers**: Symmetrical layers using the ELU (Exponential Linear Unit) activation function
- **Bottleneck Layer**: Contains 30 neurons using the ReLU (Rectified Linear Unit) activation function
- **Loss Function**: Mean Squared Error (MSE)

### Analysis Process
1. **Data Normalization**: The data was normalized to ensure consistent scaling across all features.
2. **Training**: The autoencoder was trained on the signal data to learn its underlying structure.
3. **Anomaly Detection**: Post-training, the reconstruction error was calculated for both signal and background data. A threshold (cut value) was set to distinguish between signal and background based on this error.

### Results
By applying the autoencoder-based method, we achieved significant improvement in separating the signal from the background:
- **Before Applying Cut**:
    - Signal Yield: 10.262
    - Background Yield: 676.336
    - Significance: 0.394
- **After Applying Cut**:
    - Signal Yield: 9.780
    - Background Yield: 50.80
    - Significance: 1.372

The results indicate that the autoencoder method drastically reduced the background noise while preserving most of the signal, thus significantly improving the overall significance of the measurement.

## Conclusion
The development and application of the autoencoder-based outlier detection method provided a more effective way of separating signal from background compared to traditional methods such as Boosted Decision Trees (BDT). This new approach not only improved the significance of the double Higgs-boson signal in the multi-leptons channel but also offers a promising tool for future analyses in high-energy physics experiments.
