# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForSentEmails

- ea: `0x8320`
- end: `0x8388`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForSentEmails`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8240`

## callees

- `0x8320`
- `0xf090`

## pseudocode

```c

```

## disassembly

```asm
0x8320  newobj   instance void <>c__DisplayClass48_0::.ctor()
0x8325  stloc.0
0x8326  ldloc.0
0x8327  ldc.i4.0
0x8328  stfld    int32 <>c__DisplayClass48_0::NumOfBulkEmailsSentPerDay
0x832d  ldloc.0
0x832e  ldc.i4.0
0x832f  stfld    int32 <>c__DisplayClass48_0::NumOfEmailsSentPerDay
0x8334  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8339  stloc.1
0x833a  ldloc.1
0x833b  ldstr    aSelectDelivery_0// "SELECT DeliveryPriorityCode, COUNT(1) F"...
0x8340  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8345  ldarg.0
0x8346  ldloc.1
0x8347  ldloc.0
0x8348  ldftn    instance void <>c__DisplayClass48_0::<CollectPointsForSentEmails>b__0(object[] values)
0x834e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8353  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x8358  pop
0x8359  leave.s  loc_8365
0x835b  ldloc.1
0x835c  brfalse.s loc_8364
0x835e  ldloc.1
0x835f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8364  endfinally
0x8365  ldarg.1
0x8366  ldc.i4   0x23C
0x836b  ldloc.0
0x836c  ldfld    int32 <>c__DisplayClass48_0::NumOfBulkEmailsSentPerDay
0x8371  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8376  ldarg.1
0x8377  ldc.i4   0x239
0x837c  ldloc.0
0x837d  ldfld    int32 <>c__DisplayClass48_0::NumOfEmailsSentPerDay
0x8382  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8387  ret
```
