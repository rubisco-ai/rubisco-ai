---
layout: post
title: Proof of concept
description: null
image: assets/images/demo.png
nav-menu: true
permalink: /demo/
---

<!-- Main -->
<div id="main" class="alt">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>Our proof of concept</h1>
		</header>

<p>
In 2023, we partnered with the <a href="https://lefo.ca/?lang=en">Plant Functional Ecology Laboratory</a> (LEFO) and <a href="https://carboneboreal.uqac.ca/en/home/">Carbone Boréal</a> to develop a proof of concept.
</p>


<div style="text-align: center;">
<iframe width="1000" height="800" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"
src="https://lefo.maps.arcgis.com/apps/instant/basic/index.html?appid=9fa843c7be0a4b19862bb042698f8097"></iframe>
</div>


<h2> Dataset </h2>

<h3> Imagery </h3>

<p>
<p align="justify">
LEFO acquired high-resolution drone imagery in June 2023 over one of Carbone Boréal’s plantation sites. That site was planted with white spruce (<i>Picea glauca</i>) trees in 2013.  <br>

The images were acquired using the DJI Zenmuse P1 camera mounted on a DJI M300 drone flying at 40 m above the canopy, yielding 5 mm / pixel spatial resolution.  <br>

While the camera and drone we used here are professional-grade equipment, cheaper and more accessible consumer drones and cameras can also be successfully used.  <br>
</p>

<h3> Labels </h3>
<p align="justify">
Individual planted white spruce trees were labelled manually using GIS software by segmenting their crowns (white outlines). These labels were <b>not</b> used to train our models, but are only shown to evaluate the results. White spruce labels from another independent area were used to train our models.
</p>



<h2> Data processing </h2>

<h3> Photogrammetry </h3>

<p align="justify">
The imagery was processed using structure-from-motion photogrammetry to generate a colour orthomosaic and a 3D point cloud. The 3D point cloud was projected to a 2D digital surface model (DSM).
</p>

<h3> Tree detection and segmentation </h3>

<p align="justify">
Our AI model automatically predicted all white spruce trees from the plantation site and delineated their crown outlines from the colour imagery alone. All white spruce trees were detected and there were no false positives. The automatic segmentations proved to be accurate.
</p>

<h3> Crown diameter, tree height and carbon </h3>

<p align="justify">
We estimated the mean crown diameter per tree from the predicted tree segmentations, and extracted the tree height from the DSM and a LiDAR-derived digital terrain (DTM) model we had of the area. <br>

Allometric equations specific to white spruce were used to estimate the stem diameter of every predicted tree <a href="https://onlinelibrary.wiley.com/doi/full/10.1111/gcb.16302">from its crown diameter and height</a>. Then, we estimated the total aboveground biomass and carbon of each tree, again using <a href="https://cdnsciencepub.com/doi/10.1139/x05-112">allometric equations</a> for white spruce based on stem diameter and tree height.
</p>
