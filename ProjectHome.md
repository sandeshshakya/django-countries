# Django Countries #

Nice little application for Django projects providing fixtures and models for a "complete" list of world countries ~~and US states~~. Also throwing in a small template filter for getting country flags by _ISO 3166-1 alpha-2_ country code.


## Installation ##

Just check out the latest source and copy `countries` into your django site directory:
```
svn checkout http://django-countries.googlecode.com/svn/trunk/ django-countries
```
add `countries` to the list of installed apps and run `syncdb` and you're good to go.
(Note: the models are fixed to the `country` and `usstate` tables, se models.py for details)

And for the flags hed over to [famfamfam](http://www.famfamfam.com/lab/icons/flags/) and download the _ISO 3166-1 alpha-2 country code flag package_. And add a flags director to your media root and copy the .gif flags there.
An alternative flag resource is [ip2location](http://www.ip2location.com/flagsoftheworld.aspx)

Optionally add:
```
COUNTRIES_FLAG_PATH = '<path relative to media root>flags/%s.png'
```
to django settings if you want to have the flags in an alternative location or use .png instead of the default .gif ( .gif is just a tiny bit smaller ;)


## Source of information ##


### Country list ###

The list of world countries is based on the list of ISO 3166 codes for countries in existence at the time of last update. The tricky part is getting the list complete with iso-2 code, iso-3 code, number and official printable name se models.py for more details.
Therefore this country list is a merge from these two resources:

  * http://www.iso.ch/iso/en/prods-services/iso3166ma/02iso-3166-code-lists/index.html
  * http://unstats.un.org/unsd/methods/m49/m49alpha.htm

The official list is constantly receiving updates, so the list might not be 100% accurate.

Country list last updated: **2007-08-20** - 244 countries.


### ~~US States list~~ ###

  * **DEPRECATED** [django.contrib.localflavor](http://www.djangoproject.com/documentation/localflavor/) provides listings of states. This is still not implemented in the app and needs some modifications to work.

US states list is a plain list of name and abbreviation. Making the list more complete are the additional six military "states" all according to the usps list at the time of last update:

  * http://www.usps.com/ncsc/lookups/usps_abbreviations.html

US States list last updated: **2007-08-20** - 59+6=65 states


### Disclaimer ###

As a disclaimer I'll cite the Unite Nations list of county names at http://unstats.un.org/unsd/methods/m49/m49alpha.htm

> "The designations employed and the presentation of country or area
> names in this list do not imply the expression of any opinion whatsoever on
> the part of the ~~Secretariat of the United Nations~~ _author_ concerning
> the legal status of any country, territory, city or area or of its
> authorities, or concerning the delimitation of its frontiers or boundaries."