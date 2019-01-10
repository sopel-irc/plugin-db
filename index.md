## List of modules

  {% assign cats = site.modules | group_by: 'category' %}
  {% for cat in cats %}
### {{ cat.name | capitalize }}
<dl>
    {% for mod in cat.items %}
      {% assign name = mod.path | split:"/" | last | split:"." | first %}
  <dt><a href="{{ mod.url }}">{{ name }}</a>{% if mod.core %} (included){% endif %}</dt>
    <dd>{{ mod.excerpt }}</dd>
    {% endfor %}
</dl>
  {% endfor %}
