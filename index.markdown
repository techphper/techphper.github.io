---
layout: default
---

<div>
  <ul class="listing">
  {% for post in site.posts limit: 1 %}
  <article class="content">
    <section class="title">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    </section>
    <section class="meta">
    <span class="time">
      <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    </span>
    {% if post.tags %}
    <span class="tags">
      {% for tag in post.tags %}
      <a href="/tags.html#{{ tag }}" title="{{ tag }}">#{{ tag }}</a>
      {% endfor %}
    </span>
    {% endif %}
    <!-- BEGIN this would not work on any other domain -->
    <span
      class           = 'like-wrapper'
      like-shortname  = '{{ site.disqus }}'
      like-identifier = '{{ post.guid }}'
      like-name       = '{{ post.title }}'
      like-link       = '{{ site.atom-baseurl }}{{ page.url }}'
      like-btn        = '&#xf087;'
    ></span>
    <script type="text/javascript">
      var l = document.createElement('script'); l.type = 'text/javascript'; l.async = true;
      l.src = 'http://www.like-btn.com/javascript/widget.js';
      (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(l);
    </script>
    <!-- END this would not work on any other domain -->
    </section>
    <section class="post">
    {{ post.content }}
    </section>
    </article>
  {% endfor %}
  </ul>
  <div class="divider"></div>
</div>
