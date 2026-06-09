# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSecuredEntitiesCount

- ea: `0x6a70`
- end: `0x6a81`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSecuredEntitiesCount`
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
0x6a70  ldstr    aSelectCountDis_0// "SELECT count(DISTINCT EntityId) FROM At"...
0x6a75  stloc.0
0x6a76  ldc.i4.1
0x6a77  stloc.1
0x6a78  ldarg.0
0x6a79  ldloc.0
0x6a7a  ldloc.1
0x6a7b  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6a80  ret
```
