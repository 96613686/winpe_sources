# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForReceivedEmails

- ea: `0x8260`
- end: `0x82b0`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForReceivedEmails`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8240`

## callees

- `0x8260`
- `0xf000`

## string_xrefs

- `0x8274`: `SELECT COUNT(1) FROM Email (NOLOCK) WHERE DirectionCode = 0 AND CreatedOn >= DATEADD(DAY, -1, GETUTCDATE())`

## pseudocode

```c

```

## disassembly

```asm
0x8260  newobj   instance void <>c__DisplayClass46_0::.ctor()
0x8265  stloc.0
0x8266  ldloc.0
0x8267  ldc.i4.0
0x8268  stfld    int32 <>c__DisplayClass46_0::NumOfEmailsReceivedPerDay
0x826d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8272  stloc.1
0x8273  ldloc.1
0x8274  ldstr    aSelectCount1Fr_0// "SELECT COUNT(1) FROM Email (NOLOCK) WHE"...
0x8279  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x827e  ldarg.0
0x827f  ldloc.1
0x8280  ldloc.0
0x8281  ldftn    instance void <>c__DisplayClass46_0::<CollectPointsForReceivedEmails>b__0(object[] values)
0x8287  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x828c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x8291  pop
0x8292  leave.s  loc_829E
0x8294  ldloc.1
0x8295  brfalse.s loc_829D
0x8297  ldloc.1
0x8298  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x829d  endfinally
0x829e  ldarg.1
0x829f  ldc.i4   0x23A
0x82a4  ldloc.0
0x82a5  ldfld    int32 <>c__DisplayClass46_0::NumOfEmailsReceivedPerDay
0x82aa  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x82af  ret
```
