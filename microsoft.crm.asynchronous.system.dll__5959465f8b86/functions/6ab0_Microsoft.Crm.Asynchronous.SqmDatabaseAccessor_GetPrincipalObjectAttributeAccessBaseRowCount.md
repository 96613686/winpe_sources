# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetPrincipalObjectAttributeAccessBaseRowCount

- ea: `0x6ab0`
- end: `0x6ac1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetPrincipalObjectAttributeAccessBaseRowCount`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## callees

- `0x67f0`

## string_xrefs

- `0x6ab0`: `SELECT COUNT(*) FROM PrincipalObjectAttributeAccessBase`

## pseudocode

```c

```

## disassembly

```asm
0x6ab0  ldstr    aSelectCountFro_2// "SELECT COUNT(*) FROM PrincipalObjectAtt"...
0x6ab5  stloc.0
0x6ab6  ldc.i4.1
0x6ab7  stloc.1
0x6ab8  ldarg.0
0x6ab9  ldloc.0
0x6aba  ldloc.1
0x6abb  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6ac0  ret
```
