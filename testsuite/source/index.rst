.. BreatheExample documentation master file, created by sphinx-quickstart on Tue Feb  3 18:20:48 2009.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Breathe's documentation
=======================

Breathe provides a bridge between the Sphinx and Doxygen documentation systems.

The aim is provide an easy way to include Doxygen output in a set of documention
generated by Sphinx. The system relies on the Doxygen's xml output.

Directives
----------

These directives are a work in progress and may change in syntax as the project
develops.

In each case the ``project`` and ``path`` options have the following meaning.

Where:

``project``
   Specifies which project, as defined in the breathe_projects config value,
   should be used for this directive. This overrides the default project if one
   has been specified.

``path``
   Directly specifies the patht to the folder with the doxygen output. This
   overrides the project and default project if they have bee specified.


doxygenindex Directive
~~~~~~~~~~~~~~~~~~~~~~

This directive processes and produces output for everything described by the
Doxygen xml output. It reads the ``index.xml`` file and process everything
referenced by it.

::

   .. doxygenindex::
      :project: ...
      :path: ...

doxygenfunction Directive
~~~~~~~~~~~~~~~~~~~~~~~~~

This directive generates the appropriate output for a single function. The
function name is required to be unique in the project.

::

   .. doxygenfunction:: <function name>
      :project: ...
      :path: ...

doxygenstruct Directive
~~~~~~~~~~~~~~~~~~~~~~~

This directive generates the appropriate output for a single struct. The struct
name is required to be unique in the project.

::

   .. doxygenstruct:: <struct name>
      :project: ...
      :path: ...

doxygenclass Directive
~~~~~~~~~~~~~~~~~~~~~~

This directive generates the appropriate output for a single class. It behaves
the same as the doxygenstruct directive.

::

   .. doxygenclass:: <class name>
      :project: ...
      :path: ...



Config Values
-------------

**breathe_projects**
   This should be a dictionary in which the keys are project names and the values are
   paths to the folder containing the doxygen output for that project.

**breathe_default_project**
   This should match one of the keys in the **breathe_projects** dictionary and
   indicates which project should be used when the project is not specified on
   the directive.


Example pages
-------------

.. toctree::
   :maxdepth: 1

   function
   struct
   class

Test Pages
----------

.. toctree::
   :maxdepth: 1

   doxygen
   tinyxml


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
