notebook = scopatz_mc13
nbcdir = ~/ipython/IPython/nbconvert

all:
	ipython nbconvert reveal $(notebook).ipynb $<
	sed -i 's:<link rel="stylesheet" href="//cdn.jsdelivr.net/reveal.js/2.4.0/css/theme/simple.css" id="theme">:<link rel="stylesheet" href="classy.css" id="theme">:' $(notebook).reveal.html $<
# May not be needed anymore
#	sed -i 's:class="fragment" class="text_cell_render:class="fragment text_cell_render:' $(notebook).reveal.html $<

clean:
	rm -f *.pdf *.html *.zip

%.ps :%.eps
	convert $< $@

%.png :%.eps
	convert $< $@

zip:
	zip paper.zip *.html *.bib

.PHONY: all clean
