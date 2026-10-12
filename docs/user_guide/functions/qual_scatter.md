---
jupytext:
  text_representation:
    format_name: myst
---

qual_scatter
============

Function `qual_scatter` can help you compares the performance of the best configuration with that of selected configurations across a set of instances. 
You must provide data in `CraceResults` format, options in `CplotOptions` format, the source of data (training or testing) you select for plotting, and selected configurations.

When you provide more than two configurations, it will randomly select two from the provided.


To check more details for its available arguments, call:
```{code-cell} python
import craceplot as cplot

help(cplot.qual_scatter)
```


Take ACOTSP for example:
```{code-cell} python
import os
from pathlib import Path

cplot_home = cplot.where()

p = Path(os.path.join(cplot_home, 'inst', 'examples', 'acotsp'))
path_to_acotsp = os.path.relpath(p, Path.cwd())

results, options = cplot.run('-l', path_to_acotsp)
```


You can plot with the `qual_scatter` method:
```{code-cell} python
cplot.qual_scatter(data=results, options=options, source='training', num='elites')
```




---
<div style="display: flex; justify-content: space-between; align-items: center;">
    <button onclick="history.back()" style="padding: 6px 14px; border: 1px solid #ccc; border-radius: 5px; background-color: #f5f5f5; cursor: pointer;">
        ← Back
    </button>
    <button onclick="history.forward()" style="padding: 6px 14px; border: 1px solid #ccc; border-radius: 5px; background-color: #f5f5f5; cursor: pointer;">
        Next →
    </button>
</div>