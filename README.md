# Requirements
- JRuby 1.7.9
- Oracle Database 11g Enterprise Edition Release 11.2.0.2.0 - Production

# Installation
```sh
$ git clone oracle_repro
$ cd oracle_repro
$ bundle install
```

# Error
```sh
$ bin/rake db:migrate
```

Stacktrace:

```
==  CreateBugs: migrating =====================================================
-- create_table(:bugs)
   -> 0.2060s
   -> 0 rows
==  CreateBugs: migrated (0.2080s) ============================================

rake aborted!
An error has occurred, all later migrations canceled:

ActiveRecord::JDBCError: java.sql.SQLSyntaxErrorException: ORA-00911: invalid character
: INSERT INTO "SCHEMA_MIGRATIONS" ("VERSION") VALUES ('20140107141958')arjdbc/jdbc/RubyJdbcConnection.java:597:in `execute_insert'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-jdbc-adapter-1.3.4/lib/arjdbc/jdbc/adapter.rb:448:in `exec_insert'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/connection_adapters/abstract_adapter.rb:435:in `log'
/home/tobias/.gem/jruby/1.9.3/gems/activesupport-4.0.2/lib/active_support/notifications/instrumenter.rb:20:in `instrument'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/connection_adapters/abstract_adapter.rb:430:in `log'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-jdbc-adapter-1.3.4/lib/arjdbc/jdbc/adapter.rb:448:in `exec_insert'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-jdbc-adapter-1.3.4/lib/arjdbc/oracle/adapter.rb:565:in `exec_insert'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-jdbc-adapter-1.3.4/lib/arjdbc/oracle/adapter.rb:555:in `insert'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/relation.rb:76:in `insert'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/persistence.rb:509:in `create_record'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/attribute_methods/dirty.rb:78:in `create_record'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/callbacks.rb:306:in `create_record'
/home/tobias/.gem/jruby/1.9.3/gems/activesupport-4.0.2/lib/active_support/callbacks.rb:376:in `_run__1458203378__create__callbacks'
/home/tobias/.gem/jruby/1.9.3/gems/activesupport-4.0.2/lib/active_support/callbacks.rb:80:in `run_callbacks'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/callbacks.rb:306:in `create_record'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/timestamp.rb:57:in `create_record'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/persistence.rb:477:in `create_or_update'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/callbacks.rb:302:in `create_or_update'
/home/tobias/.gem/jruby/1.9.3/gems/activesupport-4.0.2/lib/active_support/callbacks.rb:376:in `_run__1458203378__save__callbacks'
/home/tobias/.gem/jruby/1.9.3/gems/activesupport-4.0.2/lib/active_support/callbacks.rb:80:in `run_callbacks'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/callbacks.rb:302:in `create_or_update'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/persistence.rb:128:in `save!'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/validations.rb:57:in `save!'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/attribute_methods/dirty.rb:41:in `save!'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/transactions.rb:275:in `save!'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/transactions.rb:326:in `with_transaction_returning_status'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/connection_adapters/abstract/database_statements.rb:202:in `transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/connection_adapters/abstract/database_statements.rb:210:in `within_new_transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/connection_adapters/abstract/database_statements.rb:202:in `transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/transactions.rb:209:in `transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/transactions.rb:323:in `with_transaction_returning_status'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/transactions.rb:275:in `save!'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/validations.rb:41:in `create!'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:990:in `record_version_state_after_migrating'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:960:in `execute_migration_in_transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:1007:in `ddl_transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:958:in `execute_migration_in_transaction'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:920:in `migrate'
org/jruby/RubyArray.java:1613:in `each'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:916:in `migrate'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:764:in `up'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/migration.rb:742:in `migrate'
/home/tobias/.gem/jruby/1.9.3/gems/activerecord-4.0.2/lib/active_record/railties/databases.rake:42:in `(root)'
org/jruby/RubyProc.java:271:in `call'
org/jruby/RubyArray.java:1613:in `each'
org/jruby/RubyArray.java:1613:in `each'
Tasks: TOP => db:migrate
(See full trace by running task with --trace)
```
