# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlProductVersion

- ea: `0x6830`
- end: `0x6841`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlProductVersion`
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
0x6830  ldstr    aSelectServerpr_0// "SELECT SERVERPROPERTY('ProductVersion')"
0x6835  stloc.0
0x6836  ldc.i4.1
0x6837  stloc.1
0x6838  ldarg.0
0x6839  ldloc.0
0x683a  ldloc.1
0x683b  call     instance string Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneString(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6840  ret
```
