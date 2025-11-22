# Katashe Solutions: Generative Art Integration (PoC)

![Status](https://img.shields.io/badge/Status-Prototype-success)
![Performance](https://img.shields.io/badge/Performance-60fps-green)
![Tech](https://img.shields.io/badge/Tech-HTML5_Canvas-blue)

### 🔗 [View Live Demo Here](https://codepen.io/oluwamo-tunde/pen/xbVXmow)

## 📋 Overview
This repository serves as a technical Proof of Concept (PoC) for the **Katashe Solutions** website refresh. It demonstrates a lightweight, high-performance generative animation system designed to simulate "blockchain nodes" and "decentralized networks."

The goal was to create a visual metaphor for Web3 infrastructure that is:
1.  **Performant:** Runs at 60fps on standard devices.
2.  **Lightweight:** Zero external heavy dependencies (no Three.js or WebGL overhead).
3.  **Responsive:** Adapts dynamically to container resizing.

## ⚙️ Technical Implementation

### 1. HTML5 Canvas & Euclidean Distance
Instead of using DOM elements (divs) for particles, which causes layout thrashing, this implementation utilizes the **HTML5 Canvas API**.
* **Node Generation:** Particles represent network nodes with randomized velocity vectors.
* **Proximity Logic:** The script calculates the Euclidean distance between every pair of particles in real-time.
* **Dynamic Edges:** When two nodes move within a specific threshold, a line is drawn with an alpha (opacity) value inversely proportional to the distance. This creates the "organic" network effect.

### 2. Performance Optimization Loop
To ensure the site remains buttery smooth (matching the Stripe.dev aesthetic), the animation loop uses `window.requestAnimationFrame()`.
* **Delta Time:** (Planned integration) Ensures animation speed is consistent across high-refresh-rate monitors (144hz) and standard screens (60hz).
* **Garbage Collection:** Variables are scoped effectively to prevent memory leaks during long sessions.

### 3. Squarespace Integration Strategy
This code is architected to be "drop-in" ready for Squarespace:
* **Encapsulation:** The CSS and JS are namespaced to avoid conflicts with Squarespace's native template styles.
* **Z-Indexing:** The canvas is positioned with a low `z-index` to sit seamlessly behind hero typography without blocking text selection.

## 🛠️ Tech Stack
* **Core:** Vanilla JavaScript (ES6+)
* **Rendering:** HTML5 Canvas API
* **Styling:** CSS3 (Flexbox for container layout)

## 🚀 Setup & Usage
To run this locally:
1.  Clone the repo: `git clone https://github.com/shadrach16/generative-art-demo.git`
2.  Open `index.html` in any modern browser.

## 📄 Attribution & License
* Base particle logic adapted from open-source community examples (MIT License).
* Refactored and optimized for the Katashe Solutions usage case.