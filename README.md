# 👕 Fine Grained Image Similarity for Apparel

This repository contains the full implementation for the project titled **"Fine Grained Image Similarity for Apparel"**. The objective is to develop a deep learning-based model to distinguish between visually similar apparel items—addressing challenges such as subtle texture changes, minimal pattern variation, and appearance similarities in different stock inventories.

---

## 🔬 Abstract

In retail and e-commerce, it is often difficult to differentiate between apparel items that appear nearly identical due to manufacturing batches, restocks, or returned goods. Traditional computer vision techniques fail to capture the fine-grained features necessary for this task. 

This project introduces a deep learning pipeline that integrates a **ResNet50-based feature extractor**, **attention mechanisms**, and **attention erasure techniques**, along with **Gaussian blur preprocessing**, to improve feature robustness. The system aims to identify minute differences between similar apparel pieces—supporting stock classification, duplicate detection, and visual verification.

---

## 🧠 Model Architecture
![Model Architecture](https://github.com/user-attachments/assets/2c3ced9a-8b90-42ee-9c97-316428bc60cf)

The architecture includes:

- 🎯 **ResNet50 Backbone**: Pretrained on ImageNet; lower layers frozen to extract stable hierarchical features.
- 🧠 **Attention Modules**: Spatial and channel attention to enhance focus on relevant apparel regions.
- 🧹 **Attention Erasure**: During training, salient regions in attention maps are masked to force learning from secondary features.
- 🧱 **Custom Embedding Head**: Dense layers with dropout and batch normalization for robust representation.
- 📐 **Embedding Comparison**: Cosine similarity and Triplet loss with semi-hard mining to generate discriminative embeddings.

---

## 🧪 Results and Discussion

- 🎯 **High accuracy** in identifying subtle apparel differences
- 🧠 **Attention-driven learning** improves discriminative focus on key visual regions
- 🔄 **Attention erasure** improves generalization by preventing over-reliance on single features
- 🌐 **Robust** against background clutter and lighting variation
- ⚙️ **Lightweight** architecture suitable for deployment in inventory or catalog systems

---

## ⚙️ Methodology

### 🧼 Data Preprocessing
- **Color Conversion** (BGR ➝ RGB)
- **Gaussian Blur** for noise suppression
- Normalization and resizing to 224×224

### 🧠 Feature Extraction and Attention
- ResNet50 + Channel & Spatial Attention
- Top-k salient regions masked during training (attention erasure)

### 🔗 Embedding & Similarity
- Dense layers for embedding generation
- Cosine Similarity or KNN for scoring
- Triplet Loss with Semi-Hard Mining for better margin learning

---

## 🗃️ Dataset

- **Source**: In-house or scraped retail apparel datasets
- **Image Type**: RGB clothing images from various categories
- **Labels**: Binary similarity labels
- **Resolution**: 224×224
- **Pairs**: Similar (same item type) and dissimilar (different items with overlap)

---

## 🛠️ Technologies Used

| Category              | Libraries & Tools                             |
|-----------------------|-----------------------------------------------|
| Deep Learning         | TensorFlow, Keras                             |
| Attention Mechanism   | Custom Attention & Erasure modules            |
| Image Processing      | OpenCV                                        |
| Visualization         | Matplotlib, Seaborn                           |
| Feature Backbone      | ResNet50                                      |
| Preprocessing         | Gaussian Blur, Masking                        |
| Similarity Comparison | Triplet Loss, Cosine Similarity, KNN          |

---

## 🚀 How to Run

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/finegrained-apparel-similarity.git
cd finegrained-apparel-similarity
````

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

3. **Update dataset paths in notebook**

```python
image_folder = "path/to/your/images"
```

4. **Run the notebook**

```bash
jupyter notebook "FineGrained_Apparel_Similarity.ipynb"
```

---

## 📌 Use Cases

* 🧾 Apparel Catalog Deduplication
* 🛍️ Similar Product Matching in E-Commerce
* 📦 Inventory Check for Returned vs New Stock
* 🔁 Style Evolution Analysis

---

## 🙏 Acknowledgments

Special thanks to mentors who helped me guide through the project.

---

## 🧾 License

This project is intended for academic, portfolio, and research use only. For commercial use, please contact the author(s).

