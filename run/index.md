---
name: RunEveryStreet
layout: default
group: run
---

<h2>Run Every Street Project: COMING SOON</h2>


#Running Every Street in San Francisco

</br>

The best way to get to know a city is on your feet. Whenever I travel to a new city, I prefer to walk the streets over going into museums or shops. I love looking at all of the architecture, street art, and urban culture. 

San Francisco is where I fell in love with running. And running these streets made me fall in love with this city. 

In the Spring of 2020, like the rest of the world, I was locked in/around my apartment. I realized I only knew the streets in pockets of San Francisco. SF has some of the best residential architecture in the world. The houses are unique and varied throughout every neighborhood. And the neighborhoods also all have their own vibe. 

</br>

So, I decided to take on the challenge of running every street in SF. I am far from the first person to tackle this project. [Tom Graham](https://www.sfgate.com/entertainment/article/Tom-Graham-walks-every-street-in-San-Francisco-3182272.php#photo-2319225), [Toby Silver] (https://pathprojects.com/blogs/news/running-san-francisco-block-by-block#:~:text=Many%20people%20run%20in%20San,hills%20and%20nearly%20endless%20vistas.), [Ricky Gates](https://www.youtube.com/watch?v=wzMiAkk2ywQ https://www.youtube.com/watch?v=jy_W5qsjB5U), among other have also tackled this project.

Over the next ??? years, my goal is to run the full length of every street in San Francisco. I want to get to know the city better and find new favorite vistas, parks, houses, and streets. There are 2,612 streets, covering 1260 miles, in more than 36 neighborhoods in SF. 

</br>

So, let’s get started.

</br>
</br>

<!-- This loops through the paginated posts -->

{% for post in paginator.runposts %}
  <hr>
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p class="author">
    <span class="author"><a href="{{post.author}}">{{post.author}}</a></span><br>
    <span class="date"><em>{{ post.date | date_to_long_string }}</em></span>
  </p>
  <div class="content">
    {{ post.content }}
  </div>
{% endfor %}
<hr>

<!-- This makes links to other paginator pages -->
{% if paginator.total_pages > 1 %}
<ul class="pagination">
  {% if paginator.previous_page %}
    <li><a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&laquo; Prev</a></li>
  {% else %}
    <li><span>&laquo; Prev</span></li>
  {% endif %}

  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <li class="active"><span>{{ page }}</span></li>
    {% elsif page == 1 %}
      <li><a href="{{ '/run' | prepend: site.baseurl | replace: '//', '/' }}">{{ page }}</a></li>
    {% else %}
      <li><a href="{{ '/run/page:num' | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a></li>
    {% endif %}
  {% endfor %}

  {% if paginator.next_page %}
    <li><a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a></li>
  {% else %}
    <li><span>Next &raquo;</span></li>
  {% endif %}
</ul>
{% endif %}
