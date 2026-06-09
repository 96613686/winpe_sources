# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectMailboxEmailDeliveryOptions

- ea: `0x86e0`
- end: `0x87f1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectMailboxEmailDeliveryOptions`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x86c0`

## callees

- `0x86e0`
- `0xf370`

## string_xrefs

- `0x871e`: `SELECT IncomingEmailDeliveryMethod, COUNT(1) FROM Mailbox (NOLOCK) WHERE StateCode = 0 AND RegardingObjectTypeCode = 8 GROUP BY IncomingEmailDeliveryMethod`

## pseudocode

```c

```

## disassembly

```asm
0x86e0  newobj   instance void <>c__DisplayClass57_0::.ctor()
0x86e5  stloc.0
0x86e6  ldloc.0
0x86e7  ldc.i4.0
0x86e8  stfld    int32 <>c__DisplayClass57_0::NumOfNoneIncomingMethodMailbox
0x86ed  ldloc.0
0x86ee  ldc.i4.0
0x86ef  stfld    int32 <>c__DisplayClass57_0::NumOfOutlookClientIncomingMethodMailbox
0x86f4  ldloc.0
0x86f5  ldc.i4.0
0x86f6  stfld    int32 <>c__DisplayClass57_0::NumOfEmailRouterIncomingMethodMailbox
0x86fb  ldloc.0
0x86fc  ldc.i4.0
0x86fd  stfld    int32 <>c__DisplayClass57_0::NumOfForwardMailboxIncomingMethodMailbox
0x8702  ldloc.0
0x8703  ldc.i4.0
0x8704  stfld    int32 <>c__DisplayClass57_0::NumOfNoneOutgoingMethodMailbox
0x8709  ldloc.0
0x870a  ldc.i4.0
0x870b  stfld    int32 <>c__DisplayClass57_0::NumOfOutlookClientOutgoingMethodMailbox
0x8710  ldloc.0
0x8711  ldc.i4.0
0x8712  stfld    int32 <>c__DisplayClass57_0::NumOfEmailRouterOutgoingMethodMailbox
0x8717  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x871c  stloc.1
0x871d  ldloc.1
0x871e  ldstr    aSelectIncoming_0// "SELECT IncomingEmailDeliveryMethod, COU"...
0x8723  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8728  ldarg.0
0x8729  ldloc.1
0x872a  ldloc.0
0x872b  ldftn    instance void <>c__DisplayClass57_0::<CollectMailboxEmailDeliveryOptions>b__0(object[] values)
0x8731  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8736  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x873b  pop
0x873c  leave.s  loc_8748
0x873e  ldloc.1
0x873f  brfalse.s loc_8747
0x8741  ldloc.1
0x8742  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8747  endfinally
0x8748  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x874d  stloc.2
0x874e  ldloc.2
0x874f  ldstr    aSelectOutgoing_1// "SELECT OutgoingEmailDeliveryMethod, COU"...
0x8754  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8759  ldarg.0
0x875a  ldloc.2
0x875b  ldloc.0
0x875c  ldftn    instance void <>c__DisplayClass57_0::<CollectMailboxEmailDeliveryOptions>b__1(object[] values)
0x8762  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8767  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x876c  pop
0x876d  leave.s  loc_8779
0x876f  ldloc.2
0x8770  brfalse.s loc_8778
0x8772  ldloc.2
0x8773  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8778  endfinally
0x8779  ldarg.1
0x877a  ldc.i4   0x24D
0x877f  ldloc.0
0x8780  ldfld    int32 <>c__DisplayClass57_0::NumOfNoneIncomingMethodMailbox
0x8785  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x878a  ldarg.1
0x878b  ldc.i4   0x24F
0x8790  ldloc.0
0x8791  ldfld    int32 <>c__DisplayClass57_0::NumOfOutlookClientIncomingMethodMailbox
0x8796  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x879b  ldarg.1
0x879c  ldc.i4   0x251
0x87a1  ldloc.0
0x87a2  ldfld    int32 <>c__DisplayClass57_0::NumOfEmailRouterIncomingMethodMailbox
0x87a7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x87ac  ldarg.1
0x87ad  ldc.i4   0x252
0x87b2  ldloc.0
0x87b3  ldfld    int32 <>c__DisplayClass57_0::NumOfForwardMailboxIncomingMethodMailbox
0x87b8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x87bd  ldarg.1
0x87be  ldc.i4   0x24E
0x87c3  ldloc.0
0x87c4  ldfld    int32 <>c__DisplayClass57_0::NumOfNoneOutgoingMethodMailbox
0x87c9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x87ce  ldarg.1
0x87cf  ldc.i4   0x250
0x87d4  ldloc.0
0x87d5  ldfld    int32 <>c__DisplayClass57_0::NumOfOutlookClientOutgoingMethodMailbox
0x87da  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x87df  ldarg.1
0x87e0  ldc.i4   0x25A
0x87e5  ldloc.0
0x87e6  ldfld    int32 <>c__DisplayClass57_0::NumOfEmailRouterOutgoingMethodMailbox
0x87eb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x87f0  ret
```
