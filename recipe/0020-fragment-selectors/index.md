---
title: Fragment Selectors
id: 0020
layout: recipe
tags: [tbc]
summary: "tbc"
viewers:
topic: 
 - basic
---

## Use Case

Explain the different forms and uses of media fragment selectors in IIIF.

## Implementation Notes

The IIIF APIs often need to reference media like images, audio, video at a more granular level than the whole media file, which is represented by a URI. You may want to only refer to a spatial region of an image, a temporal section of an audio or video file. 

The IIIF APIs use the [W3C Media Fragment syntax](https://www.w3.org/TR/media-frags/) in most of these cases. In the simplest case you add a fragment, starting with a number sign "#" to the URI:
- `#xywh={xpos},{ypos},{width},{height}` for a rectangular image region,
- `#t={starttime},{endtime}` for a temporal audio or video section.

Example 1: `http://iiif.io/api/presentation/2.1/example/fixtures/resources/page1-full.png#xywh=0,0,600,900` references the upper left quarter of the image "page1-full.png". Please note that the coordinates are using the pixel units of the referenced image by default, you can use `#xywh=percent:0,0,50,50` to reference the upper left quarter in relative units.

Example 2: `https://fixtures.iiif.io/audio/indiana/mahler-symphony-3/CD1/medium/128Kbps.mp4#t=20,30` references ten seconds of the audio file "128Kbps.mp4" between 20 seconds and 30 seconds playing time. Please note that time coordinates are in seconds of normal play time by default and that you can omit the start time (`#t=,30`) to start at the beginning or omit the end time (`#t=20`) to stop at the end of the file.



QUESTIONS
- fragments vs selectors
- only presentation api or other apis?
- spatiotemporal video selection?


## Restrictions

When is this pattern is usable / not usable? Is it deprecated? If it uses multiple specifications, which versions are needed, etc.? 

Delete this section if it is not needed.
If you don't know what the restrictions might be initially, just leave the following line:
**Unknown - Help Needed**

## Example

Describe the solution in prose and provide an example.
The example json document must be an external document, and imported with the following:

{% include manifest_links.html viewers="UV, Mirador, Curation" manifest="manifest.json" %}

{% include jsonviewer.html src="manifest.json" %}

The direct link to the fixture is a useful convenience.

## Related Recipes

Provide a bulleted list of related recipes and why they are relevant.

{% include acronyms.md %}
{% include links.md %}

