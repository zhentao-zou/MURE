# MURE
Beyond Textual CoT: Interleaved Text-image chains with Deep Confidence Reasoning for Image Editing
# Overview
![alt text](https://github.com/zhentao-zou/MURE/blob/main/Fig/teaser.png)
Figure 1: Visualization of our interleaved text-visual reasoning process and a comparative result. 
Given the prompt “swap the tv for a lizard”, the MURE model **correctly performs multi-step
reasoning to remove the lizard and its reflection in the mirror, generating a final edited image
that maintains physical consistency**. In contrast, baseline approaches fail to handle this complex
editing tasks, leading to erroneous results.
# Framework
![alt text](https://github.com/zhentao-zou/MURE/blob/main/Fig/Introduction.png)
Figure 2: **Overview of the MURE framework.** **Left:** Our framework leverages an interleaved
text-image CoT to achieve high-fidelity image editing. **Right:** The Multimodal Deep Confidence
(MMDC) reasoning explores a tree of visual reasoning paths at each step. It prunes low-quality
branches based on a deep confidence score from a reward model, ensuring a superior trajectory toward the final edited image.

# Introduction
Image editing with natural language has gained signiffcant popularity, yet existing
methods struggle with intricate object intersections and ffne-grained spatial
relationships due to the lack of an explicit reasoning process. While Chain-of-Thought
(CoT) has been explored to enhance reasoning, purely textual CoT or
CoT augmented with coordinate information is fundamentally limited in its ability
to represent intricate visual layouts and lacks the necessary visual cues to guide
the generation of ffne-grained, pixel-level details. To address these challenges,
we propose **Mu**ltimodal **R**easoning **E**dit (**MURE**), a novel framework that **shifts
the visual editing process from purely text-based reasoning to a series of inter-leaved
textual and visual rationales.** Our framework performs image editing us-ing
a natively multimodal, interleaved text-image CoT. This approach generates
a step-by-step chain of reasoning where a textual description is followed by a
corresponding visual cue, such as a positional mask that deffned intended edited
regions or a representation of new content. Furthermore, to mitigate the hallu-cination
phenomenon of large language models, we introduce **M**ulti**m**odal Deep
Conffdence (MMDC) reasoning paradigm. This paradigm explores a tree of vi-sual
reasoning paths at each step. By pruning low-quality branches using a deep
conffdence score from a reward model, it ensures the model consistently follows
a high-quality trajectory towards the ffnal edited result. The proposed method de-composes
complex editing tasks into interdependent sub-tasks, achieving greater
precision at each stage and yielding high-ffdelity edited results. We deffne the
formulation for interleaved text-image chains and release the first CoT-Edit-14K
dataset, comprising 14K high-quality editing examples. Extensive experiments
show that our method yields signiffcant improvements across three image editing
benchmarks, establishing a more effective reasoning framework for visual editing.
# CoT-Edit-14K Dataset Construction

![alt text](https://github.com/zhentao-zou/MURE/blob/main/Fig/Dataset.png)
Figure 3: **MURE Dataset Construction Process.** **Top:** The visual annotation pipeline constructs
explicit visual cues, including positional masks that define intended edited regions and valid representations of new content. **Bottom:** The textual annotation pipeline generates detailed textual
descriptions based on the annotated CoT images from the top pipeline.

# Qualitative Results for Image Editing

![alt text](https://github.com/zhentao-zou/MURE/blob/main/Fig/Table1.png)
![alt text](https://github.com/zhentao-zou/MURE/blob/main/Fig/Table2.png)
# Vision Comparison Results
![alt text](https://github.com/zhentao-zou/MURE/blob/main/Fig/Vis.png)
# To Do List 
1. Release the training and inference code of MURE
2. Release the CoT-Edit-14K Dataset
3. The code and dataset are currently **undergoing internal confidentiality review. As this process may take some time, we appreciate your patience**and will release them as soon as final approval is granted.
