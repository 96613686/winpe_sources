# Microsoft.Crm.Asynchronous.OrganizationDatabaseIOCollector::RetrieveTotalIO

- ea: `0xb980`
- end: `0xb98e`
- name: `Microsoft.Crm.Asynchronous.OrganizationDatabaseIOCollector::RetrieveTotalIO`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb750`

## callees

- `0xb990`

## string_xrefs

- `0xb980`: `select cast( sum(numberreads + numberwrites) as int) from fn_virtualfilestats(db_id(), null)`

## pseudocode

```c

```

## disassembly

```asm
0xb980  ldstr    aSelectCastSumN// "select cast( sum(numberreads + numberwr"...
0xb985  stloc.0
0xb986  ldarg.0
0xb987  ldloc.0
0xb988  call     instance int32 Microsoft.Crm.Asynchronous.OrganizationDatabaseIOCollector::ExecuteScalar(string query)
0xb98d  ret
```
