# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlProductEdition

- ea: `0x6870`
- end: `0x6881`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlProductEdition`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x43c0`

## callees

- `0x6890`

## pseudocode

```c

```

## disassembly

```asm
0x6870  ldstr    aSelectServerpr_2// "SELECT SERVERPROPERTY('Edition')"
0x6875  stloc.0
0x6876  ldc.i4.1
0x6877  stloc.1
0x6878  ldarg.0
0x6879  ldloc.0
0x687a  ldloc.1
0x687b  call     instance string Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneString(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6880  ret
```
