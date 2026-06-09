# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCreatedEmails

- ea: `0x82b0`
- end: `0x8318`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCreatedEmails`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8240`

## callees

- `0x82b0`
- `0xf030`

## string_xrefs

- `0x82cb`: `SELECT DeliveryPriorityCode, COUNT(1) FROM Email (NOLOCK) WHERE DirectionCode = 1 AND CreatedOn >= DATEADD(DAY, -1, GETUTCDATE()) GROUP BY DeliveryPriorityCode`

## pseudocode

```c

```

## disassembly

```asm
0x82b0  newobj   instance void <>c__DisplayClass47_0::.ctor()
0x82b5  stloc.0
0x82b6  ldloc.0
0x82b7  ldc.i4.0
0x82b8  stfld    int32 <>c__DisplayClass47_0::NumOfBulkEmailsCreatedPerDay
0x82bd  ldloc.0
0x82be  ldc.i4.0
0x82bf  stfld    int32 <>c__DisplayClass47_0::NumOfEmailsCreatedPerDay
0x82c4  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x82c9  stloc.1
0x82ca  ldloc.1
0x82cb  ldstr    aSelectDelivery// "SELECT DeliveryPriorityCode, COUNT(1) F"...
0x82d0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x82d5  ldarg.0
0x82d6  ldloc.1
0x82d7  ldloc.0
0x82d8  ldftn    instance void <>c__DisplayClass47_0::<CollectPointsForCreatedEmails>b__0(object[] values)
0x82de  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x82e3  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x82e8  pop
0x82e9  leave.s  loc_82F5
0x82eb  ldloc.1
0x82ec  brfalse.s loc_82F4
0x82ee  ldloc.1
0x82ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x82f4  endfinally
0x82f5  ldarg.1
0x82f6  ldc.i4   0x23B
0x82fb  ldloc.0
0x82fc  ldfld    int32 <>c__DisplayClass47_0::NumOfBulkEmailsCreatedPerDay
0x8301  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8306  ldarg.1
0x8307  ldc.i4   0x238
0x830c  ldloc.0
0x830d  ldfld    int32 <>c__DisplayClass47_0::NumOfEmailsCreatedPerDay
0x8312  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8317  ret
```
