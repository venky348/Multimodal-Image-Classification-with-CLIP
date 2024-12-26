# Image Classification and Multimodal Embedding with CLIP: Analyzing Categories and Conditions

This project explores the capabilities of the CLIP model (Contrastive Language–Image Pretraining) for image classification and visualization across multiple categories and conditions. The analysis compares the model's performance with human benchmarks, emphasizing the effectiveness of its multimodal embedding space.

## Key Features
- **Multimodal Embedding**: Utilizes the CLIP model to map images and text descriptions into a shared embedding space.
- **Category Analysis**: Evaluates the model's ability to classify images across eight categories (`airplane`, `car`, `chair`, `cup`, `dog`, `donkey`, `duck`, `hat`).
- **Condition Analysis**: Analyzes performance under various visual conditions, such as `realistic`, `geons`, `silhouettes`, `blurred`, and `features`.
- **Performance Benchmarking**: Compares model accuracy with human performance.
- **Dimensionality Reduction**: Visualizes high-dimensional data using t-SNE to observe category separation.

## Model Architecture
### Vision Encoder
- **Backbone**: Vision Transformer (ViT) with 12 Transformer layers.
- **Process**: Images are split into patches (32x32), embedded into 512-dimensional vectors, and passed through a Transformer encoder.
- **Output**: A fixed-size feature vector representing the image.

### Text Encoder
- **Backbone**: Transformer-based architecture with 12 layers.
- **Process**: Text is tokenized, embedded, and passed through self-attention layers.
- **Output**: A fixed-size feature vector for the text.

### Shared Embedding Space
- Both vision and text embeddings are projected into a shared 512-dimensional space.
- Similarity between images and text is computed using a dot product.

## Dataset
- **Categories**: `airplane`, `car`, `chair`, `cup`, `dog`, `donkey`, `duck`, `hat`.
- **Conditions**: 
  - `realistic`: High-resolution images.
  - `geons`: Simplified geometric shapes.
  - `silhouettes`: Black-and-white outlines.
  - `blurred`: Low-clarity images.
  - `features`: Simplified key details.
- **Preprocessing**:
  - Images resized to 100x100 pixels.
  - Pixel values normalized to [0, 1].

## Evaluation
### Accuracy Across Conditions
- **Realistic**: 100.00%
- **Geons**: 49.15%
- **Silhouettes**: 87.50%
- **Blurred**: 64.29%
- **Features**: 80.49%

### Human Comparison
- The model outperforms humans in most conditions, such as `realistic` and `features`, but underperforms in `geons`.

## Visualization
### t-SNE Plot
- Reduces the high-dimensional embeddings into 2D for visualization.
- Categories are color-coded for clarity, and images are overlaid on the scatter plot to aid interpretability.

## Observations
- **Strengths**: 
  - Exceptional performance in `realistic` and `silhouette` conditions.
  - High accuracy in recognizing detailed patterns (`features`).
- **Weaknesses**: Struggles with abstract patterns like `geons`.
- **Multimodal Embedding**: The shared space effectively aligns images and text, enabling robust classification.

## Conclusion
This project demonstrates the CLIP model's ability to classify images with high accuracy under realistic and structured conditions. It highlights the model's strengths in leveraging multimodal embeddings and its potential applications in visual recognition tasks.

