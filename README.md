# CIFAR-10 Residual CNN with Advanced Augmentation

Deep Residual CNN for CIFAR-10 image classification achieving **93.23% test accuracy** with TensorFlow/Keras.

## Results
- **Test Accuracy: 93.23%** (Validation)
- **Architecture:** Custom ResNet-style CNN with residual connections
- **Parameters:** ~2.7M (much more efficient than previous 108M model!)

## Model Architecture
- **Residual Blocks:** 64 → 128 → 256 filters with skip connections
- **Regularization:** Batch Norm, Dropout (0.5), L2 Weight Decay (1e-4)
- **Data Augmentation:** Cutout, CutMix, Random Flip, Brightness
- **Global Average Pooling** instead of dense layers for efficiency

## Training Details
- **Optimizer:** AdamW with Warmup + Cosine Annealing LR schedule
- **Epochs:** 400 (early stopped with patience 50)
- **Batch Size:** 128
- **Advanced Features:**
  - WarmupCosine learning rate scheduling
  - CutMix augmentation (alpha=1.0)
  - Cutout regularization (size=8)

## Files
- `code/rescnn-cifar10.ipynb` - Complete training pipeline
- `submission/submission.csv` - Kaggle submission results

## How to Run
1. Open `code/rescnn-cifar10.ipynb` in Jupyter/Colab/Kaggle
2. Run all cells sequentially
3. Generates `submission.csv` for Kaggle competition

## Dependencies
See `requirements.txt` for package versions.