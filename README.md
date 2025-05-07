# Variational Autoencoder on Fashion-MNIST

## Project Overview

This repository contains an implementation of a Variational Autoencoder (VAE) trained on the Fashion-MNIST dataset. The encoder learns a 12-dimensional latent distribution, enabling generation of novel clothing-like images by sampling from the learned latent space.

## Repository Contents

* `Variational Autoencoder.ipynb`: Jupyter notebook with code for data loading, VAE model definition, training, sample generation, and latent variable exploration.
* `README.md`: Project documentation (this file).

## Notebook Structure

The `Variational Autoencoder.ipynb` notebook is organized into:

1. **Data Loading & Preprocessing**: Downloading and normalizing Fashion-MNIST; creating train/test splits.
2. **VAE Model Definition**:

   * **Encoder**: Convolutional layers outputting mean and log-variance vectors for a 12-dimensional latent space.
   * **Reparameterization**: Sampling latent codes using the reparameterization trick.
   * **Decoder**: Transposed convolutional layers reconstructing images from latent codes.
3. **Training Loop**:

   * Optimizing ELBO (reconstruction loss + KL divergence) using Adam.
   * Tracking training and validation losses over epochs.
4. **Sample Generation**:

   * Sampling 50 latent vectors from the standard normal distribution.
   * Decoding to generate new Fashion-MNIST–like images displayed in a grid.
   * Qualitative assessment of sample diversity and quality.
5. **Latent Variable Exploration** (Bonus):

   * Manipulating individual latent dimensions to observe effects on generated outputs.
   * Visualizing changes such as thickness, style, or texture variation across samples.

## Hyperparameter Configuration

Key settings used in the notebook:

* **Latent Dimension**: 12
* **Encoder Architecture**: Convolutional layers with ReLU activations
* **Decoder Architecture**: Transposed convolutions mirroring the encoder
* **Optimizer**: Adam with learning rate 0.001
* **Batch Size**: 128
* **Epochs**: 30
* **Loss Function**: Binary Cross-Entropy for reconstruction + KL divergence

## Requirements

* Python 3.7+
* PyTorch
* torchvision
* matplotlib
* numpy
* tqdm

## Results Summary

* **Generated Samples**: 50 new images displayed in a grid, most recognizable as clothing items (shirts, bags, shoes).
* **Diversity**: Samples show variation in style and shape, though some blur occurs in complex textures.
* **Latent Traversals**: Shifting individual dimensions produces smooth changes such as elongation of sleeves or variation in item thickness.

## License

This project is licensed under the MIT License. Feel free to use and modify!
