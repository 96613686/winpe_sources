# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectDistinctClientSyncs

- ea: `0x6b40`
- end: `0x6b5c`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectDistinctClientSyncs`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4cb0`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x6b40  ldstr    aSelectCountDis_1// "SELECT count(DISTINCT  SubscriptionId) "...
0x6b45  stloc.0
0x6b46  ldc.i4.1
0x6b47  stloc.1
0x6b48  ldarg.1
0x6b49  ldc.i4   0x1D6
0x6b4e  ldarg.0
0x6b4f  ldloc.0
0x6b50  ldloc.1
0x6b51  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6b56  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x6b5b  ret
```
