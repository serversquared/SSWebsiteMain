# (server)² Website - Main
This repository contains the webpages and all resources that are used for the
official (server)² main webserver.
  
## Apache2 Configuration
In order to get the webserver to properly load every page, you must, at the
very least, perform these edits to Apache's configuration files:
 * As root, run `a2enmod include`.
 * In `/etc/apache2/mods-enabled/dir.conf`, add `index.shtml` to the end of
   the `DirectoryIndex` line.
 * In `/etc/apache2/sites-enabled/000-default` (or whichever yours is), under
   `<Directory /var/www/>` of your VirtualHost, add `Includes` to the end of
   the `Options` line.
 * For each custom error page:
   * In `/etc/apache2/sites-enabled/000-default` (or whichever yours is), under
     your VirtualHost, add a new line: ErrorDocument _code_ _/path/to/page_
   * Example: `ErrorDocument 404 /error_pages/404`
