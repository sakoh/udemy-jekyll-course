---
layout: post
title: Benefits of static site generators
date: 2016-03-08 12:00
author: Sako Hartounian
image: http://placehold.it/900x300
lead: "We pay a huge price for the underlying complexity of dynamic code
running on the server for every request - a price could avoid entirely when this kind of complexity is not
needed."
subtitle: "Create an ultra fast secure blog that is easy to maintain and easy to scale"
---

# Dynamic Problems Link
When I built my first dynamic website more than 15 years ago, I was following the original LAMP-stack tutorials from the MySQL documentation. When I realized that all of this stuff was going on every time someone visited a website that was built like this, it blew my mind!
A web server would load my code into a PHP interpreter, on the fly, and then open connections to a database, sending queries back and forth, using the data in templates and stitching together strings of text into an HTML document, tailor-made for the visitor at that moment. Amazing!
It was, admittedly, a bit less amazing when I visited the website a few years later and found the whole web page replaced with a message from a hacker who pointed out the security flaws in the configuration and was at least generous enough just to deface the website, rather than use it as a vehicle to spread malware.
This dynamic website architecture moved the web forward, but it also opened a can of worms. By a conservative estimate, more than 70% of today’s WordPress installations are vulnerable to known exploits (and WordPress powers more than 23% of the web). Just a few months ago, 1.2 million Drupal installations got infected with malware in the span of a few days 12 million Drupal sites needed emergency patching, and any not patched within 7 hours of the exploits’ announcement should be considered infected with malware.. Not a week goes by when I don’t follow a link from social media to a website that shows a “Database connection error.” Scaling a dynamic website can be very expensive, and agencies that launch a campaign website or the like often have to overprovision drastically in order to guard against the website blowing up if it manages to go viral — or else they have to desperately scale it while trying to get it back online (something that never seems to happen during office hours).

We pay a huge price for the underlying complexity of dynamic code running on a server for every request — a price we could avoid paying entirely when this kind of complexity is not needed.

# Dynamic Websites And Caching Link

To some degree, we tend to work around this by caching. No high-profile WordPress website would be capable of running without a plugin such as WP Super Cache. Large websites no doubt rely on proxy caches such as Varnish, Nginx and Apache Traffic Server in front of their websites.
Caching is notoriously difficult to get right, however, and even the most optimized dynamic website will normally be many times slower than a static solution.
This website, Smashing Magazine, is obviously run by one of the most performance-focused teams out there and is, in general, very heavily optimized for performance. So, I ran a small experiment for this article. Using HTTrack, I grabbed a copy of this website one level deep and then deployed the static version to Netlify, a static-hosting platform based on a content delivery network (CDN). I didn’t do anything to improve performance of the static version apart from simply deploying to a host with deep CDN integration.
