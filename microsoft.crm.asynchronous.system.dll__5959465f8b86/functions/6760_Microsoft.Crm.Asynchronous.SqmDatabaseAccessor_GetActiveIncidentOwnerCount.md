# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetActiveIncidentOwnerCount

- ea: `0x6760`
- end: `0x6771`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetActiveIncidentOwnerCount`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x46b0`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x6760  ldstr    aSelectCountDis// "SELECT COUNT(DISTINCT CONVERT(varchar(6"...
0x6765  stloc.0
0x6766  ldc.i4.1
0x6767  stloc.1
0x6768  ldarg.0
0x6769  ldloc.0
0x676a  ldloc.1
0x676b  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6770  ret
```
