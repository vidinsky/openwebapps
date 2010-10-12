This is an experiment around installable web applications.  What
you'll find here:

<dl>
<dt>addons/</dt>
<dd>Addons for different browsers that provide better support
    for web applications: including new features (like search and
    notification support) and better integration into browser UI.</dd>

<dt>example/</dt>
<dd>An example that shows how to integrate myapps javascript libraries
    to allow a site author to trigger an installation of their application.</dd>

<dt>harness/</dt>
<dd>Files related to setting up a local develoment environment.  Currently
    a nodejs script that will allow you to run a webserver that serves
    up the various sites contained here.</dd>

<dt>site/</dt>
<dd>The "myapps" website.  To the end user this site is a location
    where they can launch their application dashboard.  To the developer
    this is the domain under which several javascript libraries are
    hosted that allow interaction with the user's applications.
    Site nightlies are hosted at https://myapps.mozillalabs.com</dd>
</dl>

## Building the Add-On

You have to install the Jetpack SDK locally.  Get it from tip.

To use Jetpack with 4.0b5 or nightlies, you need to change:

    python-lib/cuddlefish/app-extension/install.rdf

and change <em:maxVersion> to 4.0b6pre (instead of 4.0b5pre).  If this
is no longer necessary, please delete this node from the README.

Run "source bin/activate" from your jetpack-sdk checkout.  And go to
addons/firefox/jetpack/appetizer and run:

    cfx xpi

There will now be an appetizer.xpi which you can install.

You may have to edit addons/firefox/jetpack/appetizer/package.json
(and remove "id").  This is fine, but don't commit the result.