# 🧠 Image Classification - CIFAR-10 End-to-End System

An end-to-end CIFAR-10 image classification system with **model training**, **REST API inference**, and a **Next.js frontend UI**.  
This project demonstrates the full pipeline from training a deep learning model to serving real-time predictions through a web interface.

---

## 🚀 Project Overview

This repository integrates three main components as submodules:

| Component | Description | Technology |
|-----------|-------------|------------|
| [`cifar10`](./cifar10) | Trains a CNN model on the CIFAR-10 dataset and exports `.pth` weights | PyTorch |
| [`imageclassification-back`](https://github.com/yh2mai/imageclassification-back) | Flask backend serving inference requests using the trained model | Flask, PyTorch |
| [`imageclassification-front`](https://github.com/yh2mai/imageclassification-front) | Next.js + TypeScript frontend for users to upload images and view predictions | Next.js, React |

---

## 🧩 System Architecture

```
User → Frontend (Next.js) → Backend (Flask API) → Model (PyTorch .pth) → Prediction → Frontend UI
```

---

## 🗂️ Project Structure

```
imageclassification/
├── cifar10/                     # Model training submodule (PyTorch)
│   └── cifar_net.pth                # Trained weights file (example)
├── imageclassification-back/    # Flask backend API (submodule)
├── imageclassification-front/   # Next.js TypeScript frontend (submodule)
└── README.md                    # This file
```

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the repository with submodules

```bash
git clone --recurse-submodules https://github.com/yh2mai/imageclassification.git
cd imageclassification
```

If you already cloned it without `--recurse-submodules`, run:
```bash
git submodule update --init --recursive
```

---

### 2️⃣ Backend Setup (Flask)

```bash
cd imageclassification-back
python -m venv venv
source venv/bin/activate   # On Windows: venv/Scripts/activate
pip install -r requirements.txt
flask run
```

The Flask API will start on `http://127.0.0.1:5000` by default.

---

### 3️⃣ Frontend Setup (Next.js + TypeScript)

```bash
cd ../imageclassification-front
npm install
npm run dev
```

Visit [http://localhost:3000](http://localhost:3000) in your browser.

Ensure your Flask backend is running before testing uploads.

---

### 4️⃣ Model Training (Optional)

If you wish to retrain the model:

```bash
cd ../cifar10
python main.py
```

The trained weights (`cifar_net.pth`) will be saved/updated in the `cifar10` folder.

---

## 🧠 CIFAR-10 Dataset

The CIFAR-10 dataset contains **60,000 color images** across **10 classes**:  
`airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck`.

---

## 🔮 Future Improvements

- Incorporate **more diverse data** to improve model generalization.  
- Implement **confidence visualization** (bar chart or probability heatmap).  
- Deploy the entire system to **cloud (AWS/GCP)** or **Vercel** for online access.  

---

## 🧑‍💻 Author

Developed by [Yong-Hao Mai](https://github.com/yh2mai)

---

## 🪪 License

This project is open source under the **MIT License**.
