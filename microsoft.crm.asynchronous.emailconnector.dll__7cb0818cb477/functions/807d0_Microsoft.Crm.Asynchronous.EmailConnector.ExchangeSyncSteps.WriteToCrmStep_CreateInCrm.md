# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::CreateInCrm

- ea: `0x807d0`
- end: `0x80cf4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::CreateInCrm`
- size: `1316`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `broker_com_uri`

## callers

- `0x80370`

## callees

- `0x4da80`
- `0x549d0`
- `0x54a20`
- `0x54b90`
- `0x54d20`
- `0x54d70`
- `0x54dc0`
- `0x55f60`
- `0x58c10`
- `0x59010`
- `0x59a50`
- `0x5a930`
- `0x5a990`
- `0x5a9e0`
- `0x5aa10`
- `0x5e6d0`
- `0x5eac0`
- `0x5ead0`
- `0x5eae0`
- `0x5eaf0`
- `0x5eb00`
- `0x5f0b0`
- `0x5f0c0`
- `0x5f0f0`
- `0x5f100`
- `0x5f120`
- `0x5f150`
- `0x5f170`
- `0x5f190`
- `0x5f1a0`
- `0x61cf0`
- `0x61d90`
- `0x6fb90`
- `0x70170`
- `0x701e0`
- `0x701f0`
- `0x70280`
- `0x70290`
- `0x702d0`
- `0x70300`
- `0x70390`
- `0x704e0`
- `0x704f0`
- `0x70520`
- `0x70990`
- `0x80500`
- `0x807d0`
- `0x814a0`

## string_xrefs

- `0x807d7`: `CreateInCrm`
- `0x80cde`: `CreateInCrm`
- `0x808b2`: `New Item created in CRM. Crmid: {0}, Exchange id: {1} with object type {2} for the mailbox: {3}.`
- `0x80911`: `Item can't be created because it is in FinishedProcessing state. Exchange id: {0} with object type {1} for the mailbox: {2}.`
- `0x80983`: `Item can't be created because an existing item is found in CRM. Crmid: {0}, Exchange id: {1} ExchangeItemType {2} for the mailbox: {3}.`
- `0x809de`: `Item can't be created because it is in UntrackCurrent state. Exchange id: {0} ItemObjectType {1} for the mailbox: {2}.`
- `0x80ac7`: `Item created in CRM and added idmapping for it. CrmId: {0}, Exchange id: {1} ItemObjectType {2} for the mailbox: {3}.`
- `0x80bd4`: `Item {0} removed from the error table. Exchange id: {1} ItemObjectType {2} for the mailbox: {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x807d0  ldc.i4.0
0x807d1  ldarg.0
0x807d2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x807d7  ldstr    aCreateincrm// "CreateInCrm"
0x807dc  ldstr    asc_8A7C2// ""
0x807e1  ldstr    asc_8A7C2// ""
0x807e6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x807eb  ldarg.1
0x807ec  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncData>::GetEnumerator()
0x807f1  stloc.0
0x807f2  br       loc_80CC0
0x807f7  ldloc.0
0x807f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncData>::get_Current()
0x807fd  stloc.1
0x807fe  ldarg.0
0x807ff  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80804  ldloc.1
0x80805  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x8080a  ldloc.1
0x8080b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x80810  ldc.i4.1
0x80811  ldloc.1
0x80812  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80817  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext stepContext, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo inputSyncInfo, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo outputSyncInfo, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x8081c  isinst   Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x80821  stloc.2
0x80822  ldloc.2
0x80823  brfalse  loc_80BA5
0x80828  ldarg.0
0x80829  ldloc.2
0x8082a  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::InitSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase)
0x8082f  ldloc.2
0x80830  ldloca.s 3
0x80832  callvirt instance valuetype BeforeCreateResult Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::BeforeCreate([out] string& itemId)
0x80837  stloc.s  4
0x80839  ldloc.s  4
0x8083b  switch   loc_8090F, loc_80859, loc_80966, loc_80A2E, loc_809D3
0x80854  br       loc_80A2E
0x80859  ldarg.0
0x8085a  ldc.i4.3
0x8085b  ldstr    aCreatingANewIt// "Creating a new item with Exchange id: {"...
0x80860  ldc.i4.3
0x80861  newarr   [mscorlib]System.Object
0x80866  dup
0x80867  ldc.i4.0
0x80868  ldloc.1
0x80869  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x8086e  brtrue.s loc_80877
0x80870  ldsfld   string [mscorlib]System.String::Empty
0x80875  br.s     loc_80882
0x80877  ldloc.1
0x80878  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x8087d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80882  stelem.ref
0x80883  dup
0x80884  ldc.i4.1
0x80885  ldloc.2
0x80886  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x8088b  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80890  stelem.ref
0x80891  dup
0x80892  ldc.i4.2
0x80893  ldarg.0
0x80894  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80899  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x8089e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x808a3  stelem.ref
0x808a4  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x808a9  ldloc.2
0x808aa  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::CreateItem()
0x808af  stloc.3
0x808b0  ldarg.0
0x808b1  ldc.i4.3
0x808b2  ldstr    aNewItemCreated// "New Item created in CRM. Crmid: {0}, Ex"...
0x808b7  ldc.i4.4
0x808b8  newarr   [mscorlib]System.Object
0x808bd  dup
0x808be  ldc.i4.0
0x808bf  ldloc.3
0x808c0  stelem.ref
0x808c1  dup
0x808c2  ldc.i4.1
0x808c3  ldloc.1
0x808c4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x808c9  brtrue.s loc_808D2
0x808cb  ldsfld   string [mscorlib]System.String::Empty
0x808d0  br.s     loc_808DD
0x808d2  ldloc.1
0x808d3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x808d8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x808dd  stelem.ref
0x808de  dup
0x808df  ldc.i4.2
0x808e0  ldloc.2
0x808e1  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x808e6  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x808eb  stelem.ref
0x808ec  dup
0x808ed  ldc.i4.3
0x808ee  ldarg.0
0x808ef  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x808f4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x808f9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x808fe  stelem.ref
0x808ff  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80904  ldloc.2
0x80905  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::AfterCreate()
0x8090a  br       loc_80A34
0x8090f  ldarg.0
0x80910  ldc.i4.3
0x80911  ldstr    aItemCanTBeCrea// "Item can't be created because it is in "...
0x80916  ldc.i4.3
0x80917  newarr   [mscorlib]System.Object
0x8091c  dup
0x8091d  ldc.i4.0
0x8091e  ldloc.1
0x8091f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80924  brtrue.s loc_8092D
0x80926  ldsfld   string [mscorlib]System.String::Empty
0x8092b  br.s     loc_80938
0x8092d  ldloc.1
0x8092e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80933  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80938  stelem.ref
0x80939  dup
0x8093a  ldc.i4.1
0x8093b  ldloc.2
0x8093c  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80941  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80946  stelem.ref
0x80947  dup
0x80948  ldc.i4.2
0x80949  ldarg.0
0x8094a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x8094f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80954  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80959  stelem.ref
0x8095a  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x8095f  ldnull
0x80960  stloc.3
0x80961  br       loc_80A34
0x80966  ldloc.1
0x80967  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData)
0x8096c  stloc.s  5
0x8096e  ldarg.0
0x8096f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80974  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeFinder()
0x80979  ldloc.s  5
0x8097b  ldloc.3
0x8097c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordCausedItemChange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, string itemId)
0x80981  ldarg.0
0x80982  ldc.i4.3
0x80983  ldstr    aItemCanTBeCrea_0// "Item can't be created because an existi"...
0x80988  ldc.i4.4
0x80989  newarr   [mscorlib]System.Object
0x8098e  dup
0x8098f  ldc.i4.0
0x80990  ldloc.3
0x80991  stelem.ref
0x80992  dup
0x80993  ldc.i4.1
0x80994  ldloc.1
0x80995  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x8099a  brtrue.s loc_809A3
0x8099c  ldsfld   string [mscorlib]System.String::Empty
0x809a1  br.s     loc_809AE
0x809a3  ldloc.1
0x809a4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x809a9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x809ae  stelem.ref
0x809af  dup
0x809b0  ldc.i4.2
0x809b1  ldloc.s  5
0x809b3  box      Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x809b8  stelem.ref
0x809b9  dup
0x809ba  ldc.i4.3
0x809bb  ldarg.0
0x809bc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x809c1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x809c6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x809cb  stelem.ref
0x809cc  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x809d1  br.s     loc_80A34
0x809d3  ldarg.0
0x809d4  ldloc.2
0x809d5  ldloc.1
0x809d6  ldc.i4.1
0x809d7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::UntrackItemIfNeeded(class Microsoft.Crm.Asynchronous.EmailConnector.CrmItem crmItem, class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType)
0x809dc  ldarg.0
0x809dd  ldc.i4.3
0x809de  ldstr    aItemCanTBeCrea_1// "Item can't be created because it is in "...
0x809e3  ldc.i4.3
0x809e4  newarr   [mscorlib]System.Object
0x809e9  dup
0x809ea  ldc.i4.0
0x809eb  ldloc.1
0x809ec  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x809f1  brtrue.s loc_809FA
0x809f3  ldsfld   string [mscorlib]System.String::Empty
0x809f8  br.s     loc_80A05
0x809fa  ldloc.1
0x809fb  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80a00  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80a05  stelem.ref
0x80a06  dup
0x80a07  ldc.i4.1
0x80a08  ldloc.2
0x80a09  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80a0e  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80a13  stelem.ref
0x80a14  dup
0x80a15  ldc.i4.2
0x80a16  ldarg.0
0x80a17  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80a1c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80a21  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80a26  stelem.ref
0x80a27  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80a2c  br.s     loc_80A34
0x80a2e  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x80a33  throw
0x80a34  ldloc.3
0x80a35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x80a3a  brtrue   loc_80B87
0x80a3f  ldloc.1
0x80a40  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80a45  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x80a4a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x80a4f  stloc.s  6
0x80a51  ldloc.1
0x80a52  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80a57  brfalse.s loc_80AA6
0x80a59  ldloc.1
0x80a5a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80a5f  ldloc.3
0x80a60  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x80a65  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_CrmId(valuetype [mscorlib]System.Guid value)
0x80a6a  ldloc.1
0x80a6b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80a70  ldc.i4.m1
0x80a71  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_Retries(int32 value)
0x80a76  ldloc.1
0x80a77  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80a7c  ldc.i4.0
0x80a7d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_ToCrmChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x80a82  ldloc.1
0x80a83  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80a88  ldc.i4.0
0x80a89  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_FromCrmChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x80a8e  ldarg.0
0x80a8f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80a94  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x80a99  ldloc.1
0x80a9a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x80a9f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x80aa4  br.s     loc_80AC5
0x80aa6  ldloc.1
0x80aa7  ldarg.0
0x80aa8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80aad  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x80ab2  ldloc.3
0x80ab3  ldloc.s  6
0x80ab5  ldloc.2
0x80ab6  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80abb  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::AddExchangeSyncIdMapping(string crmId, string exchangeEntryId, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x80ac0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper value)
0x80ac5  ldarg.0
0x80ac6  ldc.i4.3
0x80ac7  ldstr    aItemCreatedInC// "Item created in CRM and added idmapping"...
0x80acc  ldc.i4.4
0x80acd  newarr   [mscorlib]System.Object
0x80ad2  dup
0x80ad3  ldc.i4.0
0x80ad4  ldloc.3
0x80ad5  stelem.ref
0x80ad6  dup
0x80ad7  ldc.i4.1
0x80ad8  ldloc.s  6
0x80ada  stelem.ref
0x80adb  dup
0x80adc  ldc.i4.2
0x80add  ldloc.2
0x80ade  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x80ae3  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80ae8  stelem.ref
0x80ae9  dup
0x80aea  ldc.i4.3
0x80aeb  ldarg.0
0x80aec  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80af1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80af6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80afb  stelem.ref
0x80afc  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80b01  ldloc.1
0x80b02  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80b07  ldloc.3
0x80b08  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_CrmId(string value)
0x80b0d  ldloc.1
0x80b0e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
  ... truncated ...
```
