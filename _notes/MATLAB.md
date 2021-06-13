---
title: MATLAB
tags: code
season: summer
---


## `startup.m`

> [`startup`](https://www.mathworks.com/help/matlab/ref/startup.html) executes user-specified commands when starting MATLAB®.

Use this file to add folders to the MATLAB paths, restore the vanished figure toolbar buttons (zoom, pan, ...) and set custom-defined parameters.

{% highlight matlab %}
%% startup.m

% add folder to MATLAB path
addpath(genpath('<path>'))

% Since Matlab 2018b figure toolbar disappeared, this reverts the change
set(groot,'defaultFigureCreateFcn','addToolbarExplorationButtons(gcf)');

% Change default Colormap from parula to hot
set(0, 'defaultFigureColormap', hot)

% define some physics
hc = 1239.84193;        % in eV*nm
c = 299792458;          % in m/s
e = 1.6021766209e-19;   % in C
a0 = 0.52917721067e-10; % in m
me = 9.10938356e-31;    % in kg
{% endhighlight %}

Here, we have also defined some physical parameters often used. Make sure you reserve those variable names and do not use them for something else in the code.

## Live scripts

[Live Scripts](https://www.mathworks.com/help/matlab/live-scripts-and-functions.html) are somewhat the MATLAB-equivalent of Jupyter Notebooks. They are really useful to display the code, text, annotations and output on a single page. 

Note that a MATLAB kernel seems to be available in Jupyter Notebooks (see for example [here](https://nbviewer.jupyter.org/github/Calysto/matlab_kernel/blob/master/matlab_kernel.ipynb) for a working example.
{: .notice--info}
