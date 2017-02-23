---
title: archieve
layout: page
description: keep hungry keep foolish
header-img: "img/tag-bg.jpg"
---


<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <h1 class="listing-seperator">{{ y }}年</h1>
  {% endif %}
  {% capture mon %}{{post.date | date:"%m"}}{% endcapture %}
  {% if month != mon %}
    {% assign month = mon %}
    <h3 class="listing-seperator">{{ mon }}月</h3>
  {% endif %}
  <li class="listing-item">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
