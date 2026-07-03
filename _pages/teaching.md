---
layout: page
permalink: /teaching/
title: Teaching
description: List of Courses taught by Dr. Sneha Jain
nav: true
nav_order: 6
display_categories: ["University of Calgary", "Stanford University", "CEPT", "EPFL", "IIIT Hyderabad"]
---

<div class="projects">
{% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_courses = site.courses | where: "category", category %}
  {% assign sorted_courses = categorized_courses | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for course in sorted_courses %}
      {% include courses.liquid %}
    {% endfor %}
  </div>
{% endfor %}
</div>
