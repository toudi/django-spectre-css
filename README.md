# django-spectre-css

This Module uses spectre.css (https://picturepan2.github.io/spectre/) to style a Django application.


## Installation

Insatall:

    pip install django-token-bucket


To use include `static/css/lib/\*.css` in your base templates css files or in your CSS pipeline


add it to your installed apps:

    INSTALLED_APPS = [
        '...',
        'django-spectre-css',
    ]

## Examples:
This module defines the following tags to make displaying Forms easier.

- render a field user of the form 'form':


    {% extends base.html %}
    {% load spectre_css %}

    [...]
    {% render_form_field form.user %}

- render the whole form:


    {% extends base.html %}
    {% load spectre_css %}

    <form method="POST">
    {% render_form form %}
    <input type="submit" value="Save" class="btn btn-primary">
    </form>
    

`render_form_field` takes the following keyword arguments:

- `switch=True|False` for checkboxes, if `True` renders the checkbox as switch
- `add_choices=[(value,text),...]` to add the choices of an select to the select
- `replace_choices=[(value,text),...]` to set the choices of an select manually
- `empty_option=value` to generate an emty option if None is selected with the text `value` 
- `value=value` overwrites the initial value of the field (not Checkbox and Select) with `value` 
