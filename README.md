# The Synaptics Chimera processor

Chimera is a microcontroller core for use in small embedded chips.
Chimera is optimized for use in power- and cost-sensitive systems
that combine fast, nimble control with a significant amount of computation.

Chimera was designed at [Synaptics, Inc.](https://www.synaptics.com), where it has appeared
in a variety of touch and touchscreen controller chips since 2003, following upon other
CPUs developed at Synaptics going back to the mid-1990s. Chimera is sometimes used alone,
but it is often paired with Synaptics' vector arithmetic coprocessor, Hydra.

---

Until recently, Chimera and Hydra were proprietary technologies that were never described in public, even
though they have shipped billions of units and there is a good chance that you have Chimera and Hydra processors
right now inside your phone, car, or laptop. (Or soon, possibly in the fingertips of your own personal robot.)
As the market for Synaptics touch chips has broadened, and more and more
people are interested in programming Synaptics touch chips, we have decided to open up these architectures to the
general public.

Initially, the specifications and related documentation for Chimera and Hydra will appear in this GitHub repository
and in Hydra's companion repository:

* https://github.com/synaptics-public/synaptics-chimera
* https://github.com/synaptics-public/synaptics-hydra

We hope over time to expand these repositories to include further materials, perhaps eventually including
the Chimera and Hydra cores themselves either under license or as open-source &mdash; but that will
have to wait for a future phase.

Chimera and Hydra are named after ancient Greek mythological creatures. The [Chimera](https://en.wikipedia.org/wiki/Chimera_%28mythology%29)
was a beast assembled from the parts of several animals; the Chimera CPU similarly draws from and combines the
computer architecture traditions of RISC, CISC, DSP, and MCUs. The [Hydra](https://en.wikipedia.org/wiki/Lernaean_Hydra)
was a serpent with many identical snakelike heads; the Hydra coprocessor likewise chews on many vector elements together.

<img src='doc/synaptics-chimera-image.png' alt='Chimera drawing' width='300'> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src='doc/synaptics-hydra-image.png' alt='Hydra drawing' width='300'>

<!-- Artwork is courtesy of ChatGPT Images. -->

---

Chimera's custom architecture aims for good performance at a low clock rate and small size by
using a mixture of RISC, CISC, and DSP concepts to achieve a great deal of work per clock cycle.

Chimera's main emphasis is efficient embedded control, with features such as hardware-managed
firmware threads with zero-cycle context switching, fast atomic read-modify-writes,
fully deterministic cycle timing, simple superscalar operation, zero-overhead loops,
and near-zero interrupt overhead.

These features allow a Chimera processor to perform roughly as well as a traditional microcontroller
such as ARM Cortex-M33 running at twice Chimera's clock frequency, at roughly half the size
and cost, and drawing significantly less power. Chimera's hardware multithreading makes its
interrupt latency over 10x faster than that of a traditional microcontroller.

Although Chimera began as a simple 16-bit processor, modern Chimera 4.2 also supports 32-bit data
and 32-bit addressing efficiently, as well as half- and single-precision floating-point
arithmetic.

> _Note:_ Chimera and Hydra are used in Synaptics' touch and fingerprint product lines. Other [Synaptics products](https://www.synaptics.com), including the Astra&trade; SR- series MCUs and SL-series MPUs, aim at dramatically different cost/performance points with very different choices of CPUs augmented by powerful NPUs.

---

This repository is still in preparation, but it will shortly contain at least these primary Chimera documents:

* The _Chimera 4.2 Programmers's Guide_, an MS Word (or PDF) document of ~1200 pages.
* The _Chimera 4.2 Hardware Guide_, an MS Word (or PDF) document of ~150 pages.
* The presentation _What Chimera Is All About_, an MS PowerPoint (or PDF) deck of ~100 slides.

And possibly, eventually:

* The presentation _An Introduction to the Chimera 4.2 Architecture_, an MS PowerPoint (or PDF) deck of ~1700 slides.
* Chimera's compiler and simulator, header files, and sample firmware.

Questions, inquiries, and comments are always welcome!

Thank you,

Dave Gillespie  
Synaptics Fellow  
daveg@synaptics.com
