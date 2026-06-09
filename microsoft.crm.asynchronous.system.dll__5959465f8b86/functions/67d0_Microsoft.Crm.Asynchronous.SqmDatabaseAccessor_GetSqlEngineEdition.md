# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlEngineEdition

- ea: `0x67d0`
- end: `0x67e1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlEngineEdition`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x43c0`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x67d0  ldstr    aSelectServerpr// "SELECT SERVERPROPERTY('EngineEdition')"
0x67d5  stloc.0
0x67d6  ldc.i4.1
0x67d7  stloc.1
0x67d8  ldarg.0
0x67d9  ldloc.0
0x67da  ldloc.1
0x67db  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x67e0  ret
```
