# The-Dark-Side-of-Generative-AI_-Deepfake-Reputation-Risk-Identify-Theft

# Research Overview: Exploring the Dark Side of Generative AI

## Overview
This research paper explores the darker aspects of Generative AI, highlighting its potential misuse across various domains. By leveraging a hybridization approach, we utilized five different models to tackle five specific problems related to AI-generated content. Each model was evaluated based on its effectiveness in identifying and mitigating risks associated with the respective issues.

## Problem Statements and Model Performance
The following table summarizes the models used, the specific problems they address, their performance scores, and the datasets employed in our analysis:

| No | Problem Statement                                           | Model           | Score  | Dataset        |
|----|-----------------------------------------------------------|------------------|--------|-----------------|
| 1  | AI-Generated Photoshopped Celebrities or DeepFake         | CTCN             | 0.9918 | DFDC            |
| 2  | Fake News Generation via AI                                | TAGN             | 0.9700 | LIAR            |
| 3  | AI-Generated Phishing Emails                               | IceptionTime     | 0.9634 | Enron Email     |
| 4  | AI-Synthesized Voice for Fraudulent Activities             | WaveNet          | 0.9902 | VCTK Corpus     |
| 5  | AI-Controlled Bot Accounts for Misinformation Spread       | ConTasnet        | 0.9721 | Twitter Bot     |

## Methodology

### Data Preprocessing
The dataset is preprocessed using TensorFlow's ImageDataGenerator to load and augment the images. The images are resized to **64x64 pixels**, normalized by rescaling pixel values, and fed into the models in batches.

The data was split into:
- **Training Data:** 70% of the dataset.
- **Validation Data:** 30% of the dataset.

### CNN Architectures
We implemented and trained five different CNN architectures to explore various design strategies for image classification:

1. **TCN (Temporal Convolutional Network):** This model uses multiple convolutional layers followed by global pooling and dense layers. We adapted the TCN architecture to process images instead of time-series data.
  
2. **WaveNet:** A CNN architecture that uses dilated convolutions for extracting features from images, inspired by its original use for audio signal processing.

3. **InceptionTime:** Based on the Inception architecture, this model includes multiple convolutional layers with different filter sizes, helping capture various features at different scales.

4. **Conv-TasNet:** Initially designed for source separation in audio, we adapted Conv-TasNet to handle image data, employing deep convolutional layers followed by pooling and dense layers.

5. **TAGN (Topology Adaptive Graph Networks):** Simplified and adapted to work with image data, this model uses CNN layers and global pooling to capture the topology of the images.

### Model Training and Optimization
Each model was trained with the following settings:
- **Optimizer:** Adam optimizer with an initial learning rate of **0.0005**.
- **Loss Function:** Binary cross-entropy for the two-class classification (real or fake).
- **Regularization:** L2 regularization applied to the convolutional and dense layers to reduce overfitting.
- **Callbacks:** Early stopping, model checkpointing, and learning rate reduction based on validation performance were implemented.

### Training Procedure
Each model is trained for a maximum of **30 epochs**, with early stopping applied if the validation loss does not improve for **6 consecutive epochs**. The model with the best validation accuracy is saved for future predictions.

## Results
The performance of each model is evaluated on the validation dataset, with accuracy and loss reported after training. The top-performing models based on validation accuracy are saved and can be loaded for future predictions.

## Conclusion
This research demonstrates that using optimized CNN models can effectively detect deepfake images. Among the five architectures, we found that **[insert your top-performing model here]** provided the best accuracy, achieving over **X%** validation accuracy.


