`NoInject!` is a Lua script for MySQL proxy.  It aims to prevent SQL injection by marking application SQL "fingerprints" as known, and when unknown fingerprints are encountered, either blocking the SQL or logging the access information and allowing the query to proceed.

In addition to using the Lua MySQL proxy script, you can use pt-query-digest to collect query fingerprints.  This provides out-of-band intrusion detection.   The provided Lua script can provide in-band SQL injection prevention by detecting queries which do not match a known fingerprint and returning an empty set for said queries.  In-band protection comes at the cost of increased query latency.

A web interface is included which can be used to mark fingerprints as white-listed.  You can also do this manually via SQL.

The proxy can be configured to block queries that do not match a known and white-listed query pattern, thereby reducing the risk of SQL injection or in 'permissive' mode, which allows quick collection of SQL patterns during development or deployment.

### Requires ###

  1. perl (DBI, DBD::mysql, Time::HiRes)
  1. Apache / Mod\_PHP
  1. MySQL server (tested with 5.6.10)
  1. MySQL proxy (tested with 0.8.3)
  1. modified pt-fingerprint (included) ([Percona Website](http://www.percona.com))

# Percona Live #
`noinject!` was developed as an example for the talk: "[Using Percona Toolkit To Detect And Even Prevent SQL Inject Attacks](https://www.percona.com/live/mysql-conference-2013/sessions/using-percona-toolkit-detect-and-even-prevent-sql-injection-attacks)"


The author of `noinject!` is a Percona trainer.  If you want to take your developer and DBA skills to the next level, check out Percona Training.  Percona has the highest level expertise in its trainers.  Bring your toughest problems and we'll help you solve them.
[Percona Training website](http://www.percona.com/training)