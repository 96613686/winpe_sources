# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::UpdateInCrm

- ea: `0x80d00`
- end: `0x811a1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::UpdateInCrm`
- size: `1185`
- prototype: ``
- caller_count: `1`
- callee_count: `45`
- tags: `installer_update, broker_com_uri`

## callers

- `0x80370`

## callees

- `0x4da80`
- `0x54a20`
- `0x58c10`
- `0x59a50`
- `0x5a930`
- `0x5a960`
- `0x5a990`
- `0x5a9e0`
- `0x5aa10`
- `0x5e6d0`
- `0x5eac0`
- `0x5ead0`
- `0x5eae0`
- `0x5eaf0`
- `0x5eb00`
- `0x5eb30`
- `0x5ebd0`
- `0x5ebe0`
- `0x5f0b0`
- `0x5f0c0`
- `0x5f0e0`
- `0x5f0f0`
- `0x5f100`
- `0x5f120`
- `0x5f140`
- `0x5f150`
- `0x5f160`
- `0x5f170`
- `0x5f190`
- `0x61f70`
- `0x65bc0`
- `0x69840`
- `0x6fb90`
- `0x701d0`
- `0x701e0`
- `0x701f0`
- `0x702a0`
- `0x70300`
- `0x704e0`
- `0x70540`
- `0x70570`
- `0x70990`
- `0x80500`
- `0x80d00`
- `0x814a0`

## string_xrefs

- `0x80d07`: `UpdateInCrm`
- `0x8118b`: `UpdateInCrm`
- `0x80e10`: `Item {0} can't be updated because it is in FinishedProcessing state. Exchange Id: {1} with object type {2} for the mailbox: {3}.`
- `0x80e79`: `Item {0} updated in CRM. Exchange id: {1} with object type {2} for the mailbox: {3}.`
- `0x80f36`: `Item {0} failed update in CRM. Exchange id: {1} with object type {2} for the mailbox: {3}.`
- `0x80f9d`: `Item {0} can't be updated because it is in UntrackCurrent state. Exchange id: {1} ItemObjectType {2} for the mailbox: {3}.`
- `0x80ffb`: `Item {0} can't be updated because it is in CreateNew state. Setting FromCrmId to empty and ItemChangeType to Insert. Exchange id: {1} ItemObjectType {2} for the mailbox: {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x80d00  ldc.i4.0
0x80d01  ldarg.0
0x80d02  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x80d07  ldstr    aUpdateincrm// "UpdateInCrm"
0x80d0c  ldstr    asc_8A7C2// ""
0x80d11  ldstr    asc_8A7C2// ""
0x80d16  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x80d1b  ldarg.1
0x80d1c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncData>::GetEnumerator()
0x80d21  stloc.0
0x80d22  br       loc_8116D
0x80d27  ldloc.0
0x80d28  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncData>::get_Current()
0x80d2d  stloc.1
0x80d2e  ldarg.0
0x80d2f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80d34  ldloc.1
0x80d35  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80d3a  ldloc.1
0x80d3b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x80d40  ldc.i4.3
0x80d41  ldloc.1
0x80d42  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80d47  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext stepContext, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo inputSyncInfo, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo outputSyncInfo, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x80d4c  isinst   Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x80d51  stloc.2
0x80d52  ldloc.2
0x80d53  brfalse  loc_810A8
0x80d58  ldloc.2
0x80d59  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x80d5e  brfalse.s loc_80DAD
0x80d60  ldloc.2
0x80d61  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x80d66  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem
0x80d6b  stloc.3
0x80d6c  ldloc.3
0x80d6d  brfalse.s loc_80DAD
0x80d6f  ldloc.3
0x80d70  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::get_IsMailboxUserApptOrganizer()
0x80d75  brtrue.s loc_80DAD
0x80d77  ldloc.3
0x80d78  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x80d7d  brfalse.s loc_80DAD
0x80d7f  ldloc.3
0x80d80  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x80d85  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x80d8a  brfalse.s loc_80DAD
0x80d8c  ldarg.0
0x80d8d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80d92  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeFinder()
0x80d97  ldc.i4.2
0x80d98  ldloc.3
0x80d99  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x80d9e  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x80da3  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x80da8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordCausedItemChange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, string itemId)
0x80dad  ldarg.0
0x80dae  ldloc.2
0x80daf  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::InitSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase)
0x80db4  ldloc.2
0x80db5  callvirt instance valuetype BeforeUpdateResult Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::BeforeUpdate()
0x80dba  stloc.s  4
0x80dbc  ldloc.s  4
0x80dbe  switch   loc_80DD8, loc_80FF9, loc_80E6C, loc_80F92
0x80dd3  br       loc_810A2
0x80dd8  ldloc.2
0x80dd9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x80dde  brfalse.s loc_80E0E
0x80de0  ldloc.2
0x80de1  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80de6  ldc.i4   0x1069
0x80deb  bne.un.s loc_80E0E
0x80ded  ldloc.2
0x80dee  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x80df3  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80df8  ldc.i4   0x109B
0x80dfd  bne.un.s loc_80E0E
0x80dff  ldloc.1
0x80e00  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncQueue Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncQueue()
0x80e05  brfalse.s loc_80E0E
0x80e07  ldloc.1
0x80e08  ldc.i4.0
0x80e09  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSyncQueue(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncQueue value)
0x80e0e  ldarg.0
0x80e0f  ldc.i4.3
0x80e10  ldstr    aItem0CanTBeUpd// "Item {0} can't be updated because it is"...
0x80e15  ldc.i4.4
0x80e16  newarr   [mscorlib]System.Object
0x80e1b  dup
0x80e1c  ldc.i4.0
0x80e1d  ldloc.2
0x80e1e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x80e23  stelem.ref
0x80e24  dup
0x80e25  ldc.i4.1
0x80e26  ldloc.1
0x80e27  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80e2c  brtrue.s loc_80E35
0x80e2e  ldsfld   string [mscorlib]System.String::Empty
0x80e33  br.s     loc_80E40
0x80e35  ldloc.1
0x80e36  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80e3b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80e40  stelem.ref
0x80e41  dup
0x80e42  ldc.i4.2
0x80e43  ldloc.2
0x80e44  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80e49  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80e4e  stelem.ref
0x80e4f  dup
0x80e50  ldc.i4.3
0x80e51  ldarg.0
0x80e52  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80e57  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80e5c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80e61  stelem.ref
0x80e62  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80e67  br       loc_810A8
0x80e6c  ldloc.2
0x80e6d  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::UpdateItem()
0x80e72  brfalse  loc_80F34
0x80e77  ldarg.0
0x80e78  ldc.i4.3
0x80e79  ldstr    aItem0UpdatedIn// "Item {0} updated in CRM. Exchange id: {"...
0x80e7e  ldc.i4.4
0x80e7f  newarr   [mscorlib]System.Object
0x80e84  dup
0x80e85  ldc.i4.0
0x80e86  ldloc.2
0x80e87  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x80e8c  stelem.ref
0x80e8d  dup
0x80e8e  ldc.i4.1
0x80e8f  ldloc.1
0x80e90  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80e95  brtrue.s loc_80E9E
0x80e97  ldsfld   string [mscorlib]System.String::Empty
0x80e9c  br.s     loc_80EA9
0x80e9e  ldloc.1
0x80e9f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80ea4  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80ea9  stelem.ref
0x80eaa  dup
0x80eab  ldc.i4.2
0x80eac  ldloc.2
0x80ead  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80eb2  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80eb7  stelem.ref
0x80eb8  dup
0x80eb9  ldc.i4.3
0x80eba  ldarg.0
0x80ebb  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80ec0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80ec5  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80eca  stelem.ref
0x80ecb  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80ed0  ldloc.2
0x80ed1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::AfterUpdate()
0x80ed6  ldarg.0
0x80ed7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80edc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x80ee1  ldloc.1
0x80ee2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80ee7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x80eec  ldloc.1
0x80eed  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80ef2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x80ef7  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem
0x80efc  dup
0x80efd  ldloc.1
0x80efe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x80f03  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::set_InputSyncItemChangeInfo(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo value)
0x80f08  dup
0x80f09  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItemChangeInfo()
0x80f0e  ldloc.2
0x80f0f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_SyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase value)
0x80f14  ldc.i4.3
0x80f15  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetAdditionalData(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType)
0x80f1a  ldloc.1
0x80f1b  ldc.i4.2
0x80f1c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSyncQueue(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncQueue value)
0x80f21  ldloc.1
0x80f22  ldc.i4.1
0x80f23  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_DirectExchangeOperation(bool value)
0x80f28  ldloc.1
0x80f29  ldc.i4.0
0x80f2a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncState value)
0x80f2f  br       loc_810A8
0x80f34  ldarg.0
0x80f35  ldc.i4.3
0x80f36  ldstr    aItem0FailedUpd// "Item {0} failed update in CRM. Exchange"...
0x80f3b  ldc.i4.4
0x80f3c  newarr   [mscorlib]System.Object
0x80f41  dup
0x80f42  ldc.i4.0
0x80f43  ldloc.2
0x80f44  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x80f49  stelem.ref
0x80f4a  dup
0x80f4b  ldc.i4.1
0x80f4c  ldloc.1
0x80f4d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80f52  brtrue.s loc_80F5B
0x80f54  ldsfld   string [mscorlib]System.String::Empty
0x80f59  br.s     loc_80F66
0x80f5b  ldloc.1
0x80f5c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80f61  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80f66  stelem.ref
0x80f67  dup
0x80f68  ldc.i4.2
0x80f69  ldloc.2
0x80f6a  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80f6f  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80f74  stelem.ref
0x80f75  dup
0x80f76  ldc.i4.3
0x80f77  ldarg.0
0x80f78  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80f7d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80f82  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80f87  stelem.ref
0x80f88  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80f8d  br       loc_810A8
0x80f92  ldarg.0
0x80f93  ldloc.2
0x80f94  ldloc.1
0x80f95  ldc.i4.3
0x80f96  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::UntrackItemIfNeeded(class Microsoft.Crm.Asynchronous.EmailConnector.CrmItem crmItem, class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType)
0x80f9b  ldarg.0
0x80f9c  ldc.i4.3
0x80f9d  ldstr    aItem0CanTBeUpd_0// "Item {0} can't be updated because it is"...
0x80fa2  ldc.i4.4
0x80fa3  newarr   [mscorlib]System.Object
0x80fa8  dup
0x80fa9  ldc.i4.0
0x80faa  ldloc.2
0x80fab  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x80fb0  stelem.ref
0x80fb1  dup
0x80fb2  ldc.i4.1
0x80fb3  ldloc.1
0x80fb4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80fb9  brtrue.s loc_80FC2
0x80fbb  ldsfld   string [mscorlib]System.String::Empty
0x80fc0  br.s     loc_80FCD
0x80fc2  ldloc.1
0x80fc3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80fc8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80fcd  stelem.ref
0x80fce  dup
0x80fcf  ldc.i4.2
0x80fd0  ldloc.2
0x80fd1  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80fd6  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80fdb  stelem.ref
0x80fdc  dup
0x80fdd  ldc.i4.3
0x80fde  ldarg.0
0x80fdf  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80fe4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80fe9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80fee  stelem.ref
0x80fef  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80ff4  br       loc_810A8
0x80ff9  ldarg.0
0x80ffa  ldc.i4.3
0x80ffb  ldstr    aItem0CanTBeUpd_1// "Item {0} can't be updated because it is"...
0x81000  ldc.i4.4
0x81001  newarr   [mscorlib]System.Object
0x81006  dup
0x81007  ldc.i4.0
0x81008  ldloc.2
0x81009  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x8100e  stelem.ref
0x8100f  dup
0x81010  ldc.i4.1
0x81011  ldloc.1
0x81012  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x81017  brtrue.s loc_81020
0x81019  ldsfld   string [mscorlib]System.String::Empty
0x8101e  br.s     loc_8102B
0x81020  ldloc.1
0x81021  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x81026  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x8102b  stelem.ref
0x8102c  dup
0x8102d  ldc.i4.2
0x8102e  ldloc.2
0x8102f  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x81034  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x81039  stelem.ref
0x8103a  dup
0x8103b  ldc.i4.3
0x8103c  ldarg.0
0x8103d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x81042  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x81047  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x8104c  stelem.ref
  ... truncated ...
```
