---
layout: page
title: Services
permalink: /services/
---

{% for post in site.posts  %}{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}{% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}

{% if forloop.first %}<h2 class="c-archives__year" id="{{ this_year }}-ref">{{this_year}}</h2>

  
  {{ post.date | date: "%b %-d, %Y" }}: <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </li>{% if forloop.last %}</ul>{% else %}{% if this_year != next_year %}

  <ul class="c-archives__list">{% endif %}
<li class="c-archives__item">
  
</ul>
<h2 class="c-archives__year" id="{{ next_year }}-ref">{{next_year}}</h2>
<ul class="c-archives__list">{% endif %}{% endif %}{% endfor %}
