# StructMotif-HyperNet

StructMotif-HyperNet is a multimodal deep learning framework for predicting multifunctional peptides (MFPs) by integrating structure-aware graph modeling, cross-sequence motif hypergraph construction, and multi-scale sequence feature extraction.

## Background
Multifunctional peptides (MFPs) are promising therapeutic agents due to their ability to interact with multiple molecular targets via conserved functional motifs. However, existing computational methods often neglect spatial structural information, cannot effectively model shared motifs across sequences, and have limited generalization due to single-sequence modeling.

## Key Features
- **Structure-aware modeling:** Constructs residue distance graphs from predicted 3D structures and applies Graph Isomorphism Networks (GINs) to capture spatial residue interactions.
- **Motif hypergraph learning:** Builds a hypergraph using k-mer motifs shared across sequences to model high-order functional associations.
- **Multi-scale sequence feature extraction:** Employs parallel 1D CNNs to extract hierarchical local sequence features.
- **Multimodal fusion:** Fuses structural, motif, and sequence representations for robust multi-label functional prediction.
- **State-of-the-art performance:** Achieves superior results on the MFTP benchmark dataset, outperforming existing methods.

## Framework Overview
1. **Input:** Peptide sequences and their predicted 3D structures (e.g., PDB files).
2. **Graph Construction:** Build residue distance graphs and motif hypergraphs.
3. **Feature Extraction:** Use GINs for structure, hypergraph attention for motifs, and multi-scale CNNs for sequence features.
4. **Fusion & Prediction:** Concatenate multimodal features and predict peptide functions via a multilayer perceptron.

![Framework Schematic](docs/architecture.png) <!-- Add your architecture image if available -->

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/StructMotif-HyperNet.git
   cd StructMotif-HyperNet
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
Prepare your peptide sequence and structure files. Example step:
1. Use the getdata function to combine the sequence and structure, obtaining the processed data input. 
2. Obtain cross-sequence motif features through the Hypergraph model and use the processed data features as the source of model prediction.
3. input into the overall model for prediction.

## Input & Output
- **Input:**
  - Peptide sequence file (FASTA format)
  - 3D structure file (PDB format)
- **Output:**
  - Multi-label functional prediction results

## Dataset
- The MFTP benchmark dataset is used for training and evaluation. See `dataset/` for details.

## Results and Evaluation
StructMotif-HyperNet achieves:
- Precision: 0.860
- Coverage: 0.852
- Absolute true value: 0.773

Ablation studies confirm the importance of each module. For more details, refer to the paper and `StructMotif-HyperNet/` directory.

## Main Dependencies
- Python 3.7+
- PyTorch
- numpy
- scipy
- biopython
- networkx
- scikit-learn
- matplotlib



## Citation
If you use this project in your research, please cite:
> Tuo ,S.H., Lin, J.K. et al. A Multimodal Prediction Framework for Multifunctional Peptides via Structure-Aware Modeling and Cross-Sequence Motif Hypergraph. 2025.

## Contact
For questions or collaboration, please contact:
- tuo_sh@126.com
- tuo_sh@xupt.edu.cn

## License
This project is licensed under the MIT License.

---
**Notice:** This project and its code are provided for academic learning and research purposes only. The associated paper is currently under peer review. You are not permitted to publish this work or its results as your own. Any academic misconduct is strictly prohibited.

