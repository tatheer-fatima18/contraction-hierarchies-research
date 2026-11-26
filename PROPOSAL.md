# Research Proposal — Track A

## Title
**Performance Evaluation of Contraction Hierarchies for Shortest-Path Routing in Road Networks**

### 1. Benchmark Paper
Geisberger, R., Sanders, P., Schultes, D., & Delling, D. (2008). *Contraction Hierarchies: Faster and Simpler Hierarchical Routing in Road Networks*. In **Experimental Algorithms: 7th International Workshop (WEA 2008)**, Lecture Notes in Computer Science, vol. 5038, pp. 319–333. Springer. https://doi.org/10.1007/978-3-540-68552-4_24

Paper: https://ai.dmi.unibas.ch/research/reading_group/geisberger-et-al-wea2008.pdf  
Publication record: https://publikationen.bibliothek.kit.edu/en/1000015090

The paper presents node contraction, shortcut edges, and bidirectional search on upward/downward edges. The KIT publication record lists 647 Scopus citations at the time checked. The paper is a WEA 2008 conference proceeding; its acceptance under the course's venue/recency rule should be confirmed with the instructor.

### 2. Result to Reproduce
Reproduce the central query-speed comparison in **Table 1** on a manageable road-network instance. In the original experiment, the `EVSQL` contraction-hierarchy configuration reports a mean query time of **159 μs**, compared with **802 μs** for the HNR baseline. The original measurements used a Western European road network with 18,029,721 nodes and 42,199,587 directed edges on a 2.0 GHz AMD Opteron system. Our Python measurements will be reported separately and will not be presented as a direct hardware-equivalent reproduction.

### 3. Research Question
**How do road-network size and graph density affect Contraction Hierarchies preprocessing time and shortest-path query time, compared with Dijkstra's algorithm, in a reproducible Python implementation?**

### 4. Data and Compute
Implement Dijkstra and a simplified, exact Contraction Hierarchies pipeline in Python. Use NetworkX for graph handling, NumPy for data processing, and Matplotlib for plots. Begin with generated weighted graphs and, if feasible, a small OpenStreetMap road-network extract using OSMnx. Experiments will run on a laptop or Google Colab; large-scale replication of the original 18-million-node experiment is outside the project scope.

### 5. Plan and Fallback
**By 4 December:** review the paper; implement and test Dijkstra; implement node contraction, witness searches, shortcut storage, and a basic bidirectional CH query on small graphs; validate that CH and Dijkstra return equal distances.

**By 18 December:** benchmark multiple graph sizes/densities; measure preprocessing time, query time, settled/visited nodes, and path-distance correctness; produce plots and discuss trade-offs.

**Fallback:** if full CH preprocessing or real-road data integration proves too time-consuming, evaluate a correct simplified CH implementation on several small synthetic weighted graphs and compare query time and visited-node counts against Dijkstra. Report limitations honestly.
