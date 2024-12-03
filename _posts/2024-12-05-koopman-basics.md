---
title: "Koopman Basics"
date: 2024-12-05
permalink: /posts/2024/12/koopman-basics/
tags:
  - koopman
  - dynamics
math: true
---

## A Brief Theory of the Koopman Operator

To understand the Koopman operator, let’s start with the basics. Imagine we have a system of nonlinear differential equations:

\\[
\dot{x} = f(x),
\\]

where:
- \\( x \\) represents the state of the system (e.g., positions, velocities, or other quantities),
- \\( \dot{x} \\) is the rate of change of \\( x \\),
- \\( f(x) \\) is a potentially nonlinear function that describes how the state evolves over time.

This equation models many systems in nature and engineering, from planetary motion to controlling robots. However, nonlinear systems often exhibit complex, unpredictable behaviors, making them challenging to analyze.

---

### **The Koopman Operator: Transforming Nonlinear into Linear**

The Koopman operator, denoted as \\( \mathcal{K} \\), provides a powerful way to study nonlinear systems by shifting our focus from the state \\( x \\) to **observable functions**. These observables, \\( g(x) \\), are functions that describe features of the system state \\( x \\)—for example:
- The energy of a pendulum,
- The distance of a robot from an obstacle,
- Or other meaningful properties.

The Koopman operator is defined as:

\\[
\mathcal{K} g(x) = g(f(x)),
\\]

where:
- \\( g(x) \\) is an observable function,
- \\( f(x) \\) is the nonlinear evolution of the state, as given by \\( \dot{x} = f(x) \\).

**In simple terms:**
- Instead of analyzing how the state \\( x \\) evolves directly, the Koopman operator tracks how **features of \\( x \\)** (the observables \\( g(x) \\)) change over time.
- Remarkably, the Koopman operator is **linear** in the space of observables, even though the original system dynamics are nonlinear.

This linearity allows us to apply the powerful tools of linear algebra to study complex, nonlinear systems.

---

### **Eigenfunctions of the Koopman Operator**

An important concept in Koopman theory is the **eigenfunction**. An eigenfunction \\( \phi(x) \\) satisfies the following relationship under the Koopman operator:

\\[
\mathcal{K} \phi(x) = \lambda \phi(x),
\\]

where:
- \\( \phi(x) \\) is the eigenfunction, representing a special observable whose behavior under the Koopman operator is simple—it just scales by a factor \\( \lambda \\),
- \\( \lambda \\) is the eigenvalue, which describes how \\( \phi(x) \\) evolves over time.

**In simpler terms:**
- Eigenfunctions are like “building blocks” of the system’s dynamics. They evolve predictably, making them incredibly useful for analyzing and understanding the system.
- The eigenvalues \\( \lambda \\) provide insights into the dynamics:
  - If \\( \\|\lambda\\| < 1 \\), the system decays over time.
  - If \\( \\|\lambda\\| > 1 \\), the system grows.
  - If \\( \lambda \\) is complex, it corresponds to oscillatory behavior.

---

### **Why This Matters**

The Koopman operator transforms the complex, nonlinear dynamics of the system \\( \dot{x} = f(x) \\) into a simpler, linear framework by focusing on observables and their evolution. By identifying eigenfunctions and eigenvalues, we can:
1. **Decompose the dynamics** into simpler, predictable components,
2. **Simplify the analysis and prediction** of the system’s long-term behavior,
3. **Design better control strategies** for engineering systems, like robots.

---

### **What’s Next?**
Remember the duffing system from the previous blog post? 
<!-- markdownlint-disable -->
<iframe src="/files/phase_portrait_duffing.html" width="50%" height="700px" frameborder="0"></iframe>
<!-- markdownlint-enable -->

Indeed we can characterize the differet regions of the duffing oscillator.

![Duffing system with Koopman](/files/duffing_manifold.png)


