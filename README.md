# TaleSpin

This is a port of the [Tale-Hugo theme](https://github.com/EmielH/tale-hugo), which itself is a port of [Tale theme for Jekyll](https://github.com/chesterhow/tale) to Hugo. I did not design this theme, merely tweaked it enough from the source theme so that it fits my needs.


![Talespin screenshot](https://raw.githubusercontent.com/umairsd/talespin/master/images/screenshot.png)

## Installation

### 1. Install the theme

If your site is also under version control using git, the easiest way to install this theme is to add it as a submodule. If you have not created a git repo for your project yet, you need to run `git init` beforehand. Inside the folder of your Hugo site, run the following command.

```shell
git submodule add https://github.com/umairsd/talespin.git themes/talespin
```

Alternatively, you can clone the theme into your project.

```shell
git clone https://github.com/umairsd/talespin.git themes/talespin
```

### 2. Configure Hugo

Add the following line to `config.toml` to tell Hugo to use the theme.

```toml
theme = "talespin"
```

Alternatively, you can tell Hugo to use the theme with the `server` command.

```shell
hugo server -t talespin
```

### Additional information

For more information, read the official [setup guide](https//gohugo.io/overview/installing/) of Hugo.

### Update the theme

If you have installed the theme as a git submodule, you can update the theme by issuing the following command inside your project folder.

```shell
git submodule update --remote --rebase
```

If you have cloned the theme, you can run `git pull` inside the theme folder.

## Configuration

Talespin allows for writing the summary of your posts manually by setting the `summary` variable in the page frontmatter. If this variable is not set, the summary that Hugo automatically generates will be used.

### Taxonomies

Talespin has basic support for taxonomies. Taxonomy and terms pages will be generated when you have defined taxonomies. However, the top menu will only generate links to those pages if they are defined in the `menu` property in the `config.yaml`.

### Placeholder partials

The theme contains placeholder partials to make the theme more flexible and easier to adapt to your site without having to change the theme itself. These are:

- `single/header.html`
- `single/footer.html`

These are included in the template for a single post, at the top of the post (below the title) and at the bottom of the post, respectively. These can be used, for example, to include additional information about the post author or for related posts. Create a file `/layouts/partials/single/header.html` or `footer.html` on your own site to have it included.

- `index/introduction.html`

This partial is included at the top of the list of posts on the index page, allowing you to add an introduction to your site.

### Linklogs

Talespin can visually identify whether a post is a [linklog](https://en.wikipedia.org/wiki/Linklog). This is done by checking whether the post has an `external-url` parameter. If so, then the title of the post is appended by the &rarr; character.

### Truncated Summary

If the summary of the post in the main index is truncated, Talespin adds a "Read more..." link to the full post.

### Copyright message

The copyright message in the footer uses the name of the author of the site, as defined in `config.toml`. For example:

```toml
[Author]
    name = "Umair"
```

### Additional CSS files

The theme can load additional CSS files for you, e.g. to override some of the styles, or the CSS that goes with a component that you're using. To add additional CSS files, put these files in the `static` folder of your site and add the `css` parameter to `config.toml`, like so:

```toml
[Params]
css = ["custom.css"]
```

To load multiple CSS files, use the parameter like this:

```toml
[Params]
css = ["custom.css", "custom2.css"]
```

## Acknowledgments

Thanks

- to [Emiel Hollander](https://github.com/EmielH/tale-hugo/") for migrating the original  [Tale theme for Jekyll](https://chesterhow.github.io/tale/).

## License

See [LICENSE](https://github.com/umairsd/talespin/blob/master/LICENSE).
