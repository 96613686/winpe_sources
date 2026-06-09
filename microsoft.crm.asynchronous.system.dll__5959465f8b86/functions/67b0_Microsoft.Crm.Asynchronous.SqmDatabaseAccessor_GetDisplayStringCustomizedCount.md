# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetDisplayStringCustomizedCount

- ea: `0x67b0`
- end: `0x67c1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetDisplayStringCustomizedCount`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b60`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x67b0  ldstr    aSelectCountFro_0// "SELECT COUNT(*) FROM DisplayString WHER"...
0x67b5  stloc.0
0x67b6  ldc.i4.1
0x67b7  stloc.1
0x67b8  ldarg.0
0x67b9  ldloc.0
0x67ba  ldloc.1
0x67bb  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x67c0  ret
```
