Constraint
**********

Supported linear constraints in ReHLine are listed in the table below.

Usage
-----

.. code:: python
   
   # list of 
   # name (str): name of the custom loss function
   # loss_kwargs: more keys and values for loss parameters
   constraint = [{'name': <loss_name>, <**loss_kwargs>}, ...]

.. list-table::
 :align: left
 :widths: 5 20 15
 :header-rows: 1

 * - constraint
   - | args
   - | Example 

 * - **nonnegative**
   - | ``name``: 'nonnegative' or '>=0'
   - | ``loss={'name': '>=0'}``

 * - **fair**
   - | ``name``: 'fair' or 'fairness'
     | ``X_sen``: 2d array [n x p] for sensitive attributes
     | ``tol_sen``: 1d array [p] of tolerance for fairness
   - | ``loss={'name': 'fair', 'X_sen': X_sen, 'tol_sen': tol_sen}``

 * - **custom**
   - | ``name``: 'custom'
     | ``A``: 2d array [K x d] for linear constraint coefficients
     | ``b``: 1d array [K] of constraint intercepts
   - | ``loss={'name': 'custom', 'A': A, 'b': b}``

Related Examples
----------------

.. nblinkgallery::
   :caption: Constraints
   :name: rst-link-gallery

   ../examples/FairSVM.ipynb
