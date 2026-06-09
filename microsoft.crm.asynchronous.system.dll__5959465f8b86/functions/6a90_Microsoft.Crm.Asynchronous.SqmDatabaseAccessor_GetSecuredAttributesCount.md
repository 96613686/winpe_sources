# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSecuredAttributesCount

- ea: `0x6a90`
- end: `0x6aa1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSecuredAttributesCount`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x6a90  ldstr    aSelectCountFro_1// "SELECT COUNT(*) FROM AttributeView WHER"...
0x6a95  stloc.0
0x6a96  ldc.i4.1
0x6a97  stloc.1
0x6a98  ldarg.0
0x6a99  ldloc.0
0x6a9a  ldloc.1
0x6a9b  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6aa0  ret
```
