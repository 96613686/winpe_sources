# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlLanguage

- ea: `0x6720`
- end: `0x6731`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlLanguage`
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
0x6720  ldstr    aSelectLcidFrom// "SELECT lcid FROM master.dbo.syslanguage"...
0x6725  stloc.0
0x6726  ldc.i4.1
0x6727  stloc.1
0x6728  ldarg.0
0x6729  ldloc.0
0x672a  ldloc.1
0x672b  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6730  ret
```
