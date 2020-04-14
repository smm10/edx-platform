Record External ID Table Decision
=================================

Status
------

Accepted

Context
-------

Third Party's at times require a unique user ID as part of the data that they can
access about a Learner. We would like to avoid sending them internal database IDs
to protect our internal data models.

Currently, we use the database row ID for each user internally. We also have Hash IDs
that are used for some reporting and other external sources as part of the anonymous ID
table.  We would like to avoid using the anonymous IDs because they have a specific use case.


Decisions
---------

- External IDs will be UUIDs.
- User's will only have exactly 1 external id per ExternalIDType.
- All Types will have a clear description in the ExternalIDType table.
- All External ID Types should be easily referenced in the platform to support getting User information based on External IDs.
- We will add an External ID table to support different types of generated UUIDs.

Consequences
------------

We will have a clear unique ID to share with external sources that can reference
an internal User.

References
----------

Some notes on why add a type table
- https://www.itprotoday.com/sql-server/trouble-type-tables
