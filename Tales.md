# Tales

In Labyrinth, an _interactive tale_ is based on a collection of interconnected scenes that are connected together by choices, which are conditional links between scenes. The structure of the tale is held in an [XML](https://en.m.wikipedia.org/wiki/XML) document called `talebones.xml` and it names the scenes, describes the choices and how the scenes and choices join up. It doesn't include any story text or pictures, which are always held in separate files.


## Hello, World!

Let's start with the simplest possible tale. It just has has one scene and no choices. It might look something like the following:

```xml
<talebones layout='/Layouts/Simple'>
    <scene name='Scene001' full-text='Scene001/full-text.md'>
    </scene>
</talebones>
```

When you run [this tale](link-to-be-provided), all it does is display the full-text of the scene that is held in the file `full-text.md`. The tale-telling engine sees that there are no continuations from this scene and realises that this is the end of the tale too, so displays the fancy "THE END" message too. 

Perhaps surprisingly, even this ridiculously simple tale has quite a lot going on:

  * Every scene has a name, which is a unique identifier that can be used elsewhere to reference this particular scene. Trying to load a talebones file that has the same name for two or more scenes isn't allowed. Names are mandatory, so even though there is only one scene in this file it has to have a name.

  * The full-text isn't stored in the talebones file but in another file. In our example it is stored in a file `full-text.md` in a folder `Scene001`. All paths are relative to the folder containing the talebones file.

  * The full-text itself is written in (Markdown)[https://daringfireball.net/], which is a popular format for writing rich-text content using only plain-text. Markdown is popular because it is simple to write, easy to embed in web applications, doesn't require special tools and easy to maintain in version control systems like git. This file that you are reading now is written in Markdown, for instance. 

  * The overall look of the window is determined by a premade template called `Simple`, which is a folder containing a template file `template.mustache` written in the [Mustache](https://mustache.github.io/mustache.5.html) notation. That folder also contains any other images and CSS files used by the layout. Writing templates is an advanced topic because it requires not just knowing Mustache but also HTML, CSS, image editing and how Labyrinth passes data into the template. So, to start with, you can just use the [premade layouts](link-to-be-provided). Pre-made assets are addressed with an absolute path.

