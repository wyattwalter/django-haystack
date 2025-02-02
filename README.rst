========
About this branch
========

:date: 2012/01/09

Added LocationField to Haystack and location data type to Solr backend code based upon Yun Fu's blog: http://fuyun.org/2011/11/add-solr-spatial-search-for-djang-haystack/

Add field to Index like this:
>>> location = LocationField(model_lat_attr='lat', model_lng_attr='lng')


:date: 2011/11/04

Added spatial filtering as 
discussed in http://groups.google.com/group/django-haystack/browse_thread/thread/d0e23d45c0baa300/cb5d29132735afaf
but using haystack 1.2.* (so all changes are in the 1.2.X branch at the moment) and geofiltering from Solr 3.4+

Spatial filtering example

>>> from haystack.query import SearchQuerySet
>>> s = SearchQuerySet()
>>> s.spatial(lat=9.671519, long=46.686754000000001, sfield='location',distance=10)

See more here - https://github.com/frutik/django-haystack/blob/1.2.X/README.rst

========
Haystack
========

:author: Daniel Lindsley
:date: 2011/09/18

Haystack provides modular search for Django. It features a unified, familiar
API that allows you to plug in different search backends (such as Solr_,
Whoosh_, Xapian_, etc.) without having to modify your code.

.. _Solr: http://lucene.apache.org/solr/
.. _Whoosh: http://whoosh.ca/
.. _Xapian: http://xapian.org/

Haystack is BSD licensed, plays nicely with third-party app without needing to
modify the source and supports advanced features like faceting, More Like This,
highlighting and spelling suggestions.

You can find more information at http://haystacksearch.org/.


Getting Help
============

There is a mailing list (http://groups.google.com/group/django-haystack/)
available for general discussion and an IRC channel (#haystack on
irc.freenode.net).


Documentation
=============

* Development version: http://docs.haystacksearch.org/dev/
* v1.1: http://docs.haystacksearch.org/1.1/
* v1.0: http://docs.haystacksearch.org/1.0/


Requirements
============

Haystack has a relatively easily-met set of requirements.

* Python 2.5+
* Django 1.2+

Additionally, each backend has its own requirements. You should refer to
http://docs.haystacksearch.org/dev/installing_search_engines.html for more
details.
