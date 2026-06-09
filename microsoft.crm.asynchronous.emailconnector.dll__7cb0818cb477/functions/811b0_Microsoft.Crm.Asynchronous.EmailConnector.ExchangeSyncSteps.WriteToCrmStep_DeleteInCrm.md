# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::DeleteInCrm

- ea: `0x811b0`
- end: `0x8134a`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::DeleteInCrm`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x80370`

## callees

- `0x54a00`
- `0x54a30`
- `0x58c10`
- `0x5a990`
- `0x5a9e0`
- `0x5e6d0`
- `0x5eae0`
- `0x5eb00`
- `0x5f150`
- `0x5f170`
- `0x5f190`
- `0x5f1a0`
- `0x5fbd0`
- `0x61d30`
- `0x61f20`
- `0x701e0`
- `0x70580`
- `0x70590`
- `0x70990`
- `0x80500`
- `0x811b0`

## string_xrefs

- `0x811b7`: `DeleteInCrm`
- `0x81334`: `DeleteInCrm`

## pseudocode

```c

```

## disassembly

```asm
0x811b0  ldc.i4.0
0x811b1  ldarg.0
0x811b2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x811b7  ldstr    aDeleteincrm// "DeleteInCrm"
0x811bc  ldstr    asc_8A7C2// ""
0x811c1  ldstr    asc_8A7C2// ""
0x811c6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x811cb  ldarg.1
0x811cc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncData>::GetEnumerator()
0x811d1  stloc.0
0x811d2  br       loc_81316
0x811d7  ldloc.0
0x811d8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncData>::get_Current()
0x811dd  stloc.1
0x811de  ldarg.0
0x811df  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x811e4  ldloc.1
0x811e5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x811ea  ldloc.1
0x811eb  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x811f0  ldc.i4.2
0x811f1  ldloc.1
0x811f2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x811f7  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext stepContext, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo inputSyncInfo, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo outputSyncInfo, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x811fc  isinst   Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x81201  stloc.2
0x81202  ldloc.2
0x81203  brfalse  loc_812EA
0x81208  ldloc.2
0x81209  isinst   Microsoft.Crm.Asynchronous.EmailConnector.CrmAppointmentItem
0x8120e  stloc.3
0x8120f  ldloc.3
0x81210  brfalse.s loc_81250
0x81212  ldloc.3
0x81213  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmAppointmentItem::IsCurrentUserApptOrganizer()
0x81218  brtrue.s loc_81250
0x8121a  ldloc.2
0x8121b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItemChangeInfo()
0x81220  brfalse.s loc_81250
0x81222  ldloc.2
0x81223  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItemChangeInfo()
0x81228  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x8122d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x81232  brtrue.s loc_81250
0x81234  ldarg.0
0x81235  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x8123a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeFinder()
0x8123f  ldc.i4.2
0x81240  ldloc.2
0x81241  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItemChangeInfo()
0x81246  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x8124b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordCausedItemChange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, string itemId)
0x81250  ldarg.0
0x81251  ldloc.2
0x81252  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::InitSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase)
0x81257  ldloc.2
0x81258  callvirt instance valuetype BeforeDeleteResult Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::BeforeDelete()
0x8125d  stloc.s  6
0x8125f  ldloc.s  6
0x81261  brfalse.s loc_81272
0x81263  ldloc.s  6
0x81265  ldc.i4.1
0x81266  bne.un.s loc_81277
0x81268  ldloc.2
0x81269  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::DeleteItem()
0x8126e  stloc.s  4
0x81270  br.s     loc_8127D
0x81272  ldc.i4.0
0x81273  stloc.s  4
0x81275  br.s     loc_8127D
0x81277  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x8127c  throw
0x8127d  ldloc.2
0x8127e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItemChangeInfo()
0x81283  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x81288  stloc.s  5
0x8128a  ldloc.s  5
0x8128c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x81291  brtrue.s loc_812EA
0x81293  ldloc.s  4
0x81295  brfalse.s loc_812C4
0x81297  ldloc.2
0x81298  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::AfterDelete()
0x8129d  ldloc.1
0x8129e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x812a3  brfalse.s loc_812EA
0x812a5  ldarg.0
0x812a6  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x812ab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x812b0  ldloc.1
0x812b1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x812b6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::DeleteExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x812bb  ldloc.1
0x812bc  ldnull
0x812bd  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper value)
0x812c2  br.s     loc_812EA
0x812c4  ldloc.2
0x812c5  ldloc.s  5
0x812c7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::AfterUntrack(string id)
0x812cc  ldloc.1
0x812cd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x812d2  brfalse.s loc_812EA
0x812d4  ldarg.0
0x812d5  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x812da  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x812df  ldloc.1
0x812e0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x812e5  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::MarkDeletedInExchange(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x812ea  ldarg.0
0x812eb  ldloc.1
0x812ec  ldc.i4.2
0x812ed  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::MarkSyncStateAsComplete(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData, valuetype [Microsoft.Crm]Microsoft.Crm.SyncDirections)
0x812f2  leave.s  loc_81316
0x812f4  stloc.s  7
0x812f6  ldloc.s  7
0x812f8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x812fd  ldstr    aShutdownEventR// "Shutdown event received"
0x81302  callvirt instance bool [mscorlib]System.String::Contains(string)
0x81307  brfalse.s loc_8130B
0x81309  rethrow
0x8130b  ldarg.0
0x8130c  ldloc.s  7
0x8130e  ldloc.1
0x8130f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::HandlePerItemException(class [mscorlib]System.Exception ex, class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData)
0x81314  leave.s  loc_81316
0x81316  ldloc.0
0x81317  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8131c  brtrue   loc_811D7
0x81321  leave.s  loc_81349
0x81323  ldloc.0
0x81324  brfalse.s loc_8132C
0x81326  ldloc.0
0x81327  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8132c  endfinally
0x8132d  ldc.i4.1
0x8132e  ldarg.0
0x8132f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x81334  ldstr    aDeleteincrm// "DeleteInCrm"
0x81339  ldstr    asc_8A7C2// ""
0x8133e  ldstr    asc_8A7C2// ""
0x81343  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x81348  endfinally
0x81349  ret
```
