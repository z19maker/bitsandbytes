

## Model Summary

- 30B Total, 3B Active
- Speculative Decoding 	DSpark for low-concurrency Data Centre and DGX Spark Workflows — Read more below, also provided are MTP (Multi-Token Prediction) and DFlash
- 

## Model Overview

December 2025 to May 2026

### What is Nemotron?

NVIDIA Nemotron™ is a family of open models with open weights, training data, and recipes, delivering leading efficiency and accuracy for building specialized AI agents.

## Description

The model employs a hybrid Mixture-of-Experts architecture, utilizing interleaved Mamba-2 and MoE layers, along with select Attention layers. The Lightning 3.5 model is released alongside a number of speculative decoding methods for faster text generation. The model has 3B active parameters and 30B parameters in total.

## Quick Start
## License/Terms of Use
## Benchmarks

general knowledge
- mmlu pro
- aa omniscience

reasoning
- gpqa diamond
- hle
- sci code

coding and agentic
- swe bench verified
- swe bench multilingual
- terminal bench
- pinch bench
- browsecomp
- τ³-bench (Banking)
- GDPval-AA-V2

instruction following
- IFBench (loose)

long context
- AA LCR

### Reasoning Benchmark Evaluations
#### Agentic Coding Benchmarks
### Deployment Geography: Global
### Use Case

NVIDIA-Nemotron-3.5-Lightning-30B-A3B-NVFP4 is a general purpose reasoning and chat model intended to be used in English and coding languages. Other non-English languages (Spanish, French, German, Italian, Japanese) are also supported. Intended for developers designing AI Agent systems, chatbots, RAG systems, and other AI-powered applications. Also suitable for typical instruction-following tasks.

### Release Date
## Model Architecture

Architecture Type: Mixture-of-Experts Hybrid (Mamba + Transformer)
Network Architecture: Nemotron-3-Lightning + Multi-Token Prediction (MTP)
Number of model parameters: 30B Total / 3B Active

- NVFP4 precision across all hardware platforms listed. 
- NVFP4 is NVIDIA's proprietary 4-bit floating-point format.
- https://developer.nvidia.com/blog/introducing-nvfp4-for-efficient-and-accurate-low-precision-inference/

The stored precision is consistently NVFP4 across all hardware, but the compute path varies depending on whether the hardware has native FP4 tensor cores. Older architectures (Ampere, Hopper) convert the 4-bit weights to 16-bit activations during computation, while Blackwell's GB200 can compute natively in FP4.

## Model Design

The model was pre-trained with over 20T tokens and supports up to 1M context length. The pre-training phase used an NVFP4 recipe. The model includes Multi-Token Prediction (MTP) layers, which predict multiple future tokens to provide richer training signals.

## Training Methodology

Stage 1: Pre-Training
- Software used for pre-training: Megatron-LM

Stage 2: Continued Pre-Training for Multi-Token Prediction (MTP)

Stage 3: Supervised Fine-Tuning

Stage 4: Reinforcement Learning
- GRPO
- Software used for reinforcement learning: NeMo RL, NeMo Gym

Stage 5: Post-training Quantization (PTQ)

## Input

- Input Type(s): Text
- Input Format(s): String
- Input Parameters: One-Dimensional (1D): Sequences
- Other Properties Related to Input: Maximum context length up to 1M tokens. - Supported languages include English, Spanish, French, German, Italian, and Japanese.

## Output

- Output Type(s): Text
- Output Format: String
- Output Parameters: One-Dimensional (1D): Sequences
- Other Properties Related to Output: Maximum context length up to 1M tokens

Our AI models are designed and/or optimized to run on NVIDIA GPU-accelerated systems. By leveraging NVIDIA's hardware (e.g. GPU cores) and software frameworks (e.g., CUDA libraries), the model achieves faster training and inference times compared to CPU-only solutions.


## Software Integration

- Runtime Engine(s): PyTorch
- Supported Hardware Microarchitecture Compatibility: NVIDIA Blackwell; NVIDIA Hopper (NVFP4 / W4A16); NVIDIA Ampere (W4A16)
- Preferred/Supported Operating System(s): Linux

## Model Version(s)
## **Quick Start Guide**
## Choose your deployment
### **Speculative Decoding Strategies**
### **vLLM** 
#### **1x DGX Spark (GB10)**
#### **1x H100 (max throughput)**
#### **1x H100 (interactive)**
#### **8x H100 (vLLM)**
#### **1x GB200 (vLLM)**
#### **W4A16 (vLLM)**
### **TensorRT-LLM**
#### **1x H100 (TensorRT-LLM)**
### **SGLang**
#### **1x B200**
#### **1x H100**
#### **1x DGX Spark (GB10)**
#### **Speculative decoding**
## Local AI (RTX 5090, DGX Spark, and RTX 6000 Pro)
### Ollama
### llama.cpp
### LM Studio
### **API Client**
#### **Tool Calling**
## Training, Testing, and Evaluation Datasets
#### **Base Pre-Training Corpus (Nemotron 3 Foundation)**
### Public Datasets
### **Crawled and Scraped from Online Sources by NVIDIA**
## Private Non-publicly Accessible Datasets of Third Parties
## Private Non-publicly Accessible Datasets by NVIDIA
## NVIDIA-Sourced Synthetic Datasets (Pre-Training)
## NVIDIA-Sourced Synthetic Datasets (Post-Training)
## Language Distribution in Post-Training
## Testing Datasets:
## Evaluation Datasets:
## Inference
## Ethical Considerations
