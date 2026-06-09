# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::AddToCrmChange

- ea: `0x5d9e0`
- end: `0x5dcdf`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::AddToCrmChange`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5d870`

## callees

- `0xac40`
- `0x4da80`
- `0x52650`
- `0x54a10`
- `0x54b60`
- `0x54bb0`
- `0x54c00`
- `0x54ca0`
- `0x54e80`
- `0x58190`
- `0x58270`
- `0x58c10`
- `0x5d3b0`
- `0x5d9e0`
- `0x5dce0`
- `0x5e290`
- `0x5e3a0`
- `0x5e4b0`
- `0x5e4c0`
- `0x5e510`
- `0x5e520`
- `0x5e610`
- `0x5ea60`
- `0x5eac0`
- `0x5eae0`
- `0x5eaf0`
- `0x5eb00`
- `0x5eb20`
- `0x5eb30`
- `0x5eb40`
- `0x5eb50`
- `0x5ebd0`
- `0x5ebe0`
- `0x5f090`
- `0x5f160`
- `0x5f180`
- `0x5f1a0`
- `0x69840`
- `0x70310`
- `0x829c0`

## string_xrefs

- `0x5da1b`: `SyncItemChangeInfo CrmId updated from {0} to {1} for mailbox {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x5d9e0  ldc.i4.0
0x5d9e1  ldarg.0
0x5d9e2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5d9e7  ldstr    aAddtocrmchange// "AddToCrmChange"
0x5d9ec  ldstr    asc_8A7C2// ""
0x5d9f1  ldstr    asc_8A7C2// ""
0x5d9f6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5d9fb  ldarg.3
0x5d9fc  brfalse.s loc_5DA6E
0x5d9fe  ldarg.3
0x5d9ff  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x5da04  stloc.1
0x5da05  ldloca.s 1
0x5da07  constrained. [mscorlib]System.Guid
0x5da0d  callvirt instance string [mscorlib]System.Object::ToString()
0x5da12  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsValidCrmId(string crmIdString)
0x5da17  brfalse.s loc_5DA6E
0x5da19  ldarg.0
0x5da1a  ldc.i4.4
0x5da1b  ldstr    aSyncitemchange_1// "SyncItemChangeInfo CrmId updated from {"...
0x5da20  ldc.i4.3
0x5da21  newarr   [mscorlib]System.Object
0x5da26  dup
0x5da27  ldc.i4.0
0x5da28  ldarg.1
0x5da29  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5da2e  stelem.ref
0x5da2f  dup
0x5da30  ldc.i4.1
0x5da31  ldarg.3
0x5da32  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x5da37  stloc.1
0x5da38  ldloca.s 1
0x5da3a  constrained. [mscorlib]System.Guid
0x5da40  callvirt instance string [mscorlib]System.Object::ToString()
0x5da45  stelem.ref
0x5da46  dup
0x5da47  ldc.i4.2
0x5da48  ldarg.0
0x5da49  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5da4e  stelem.ref
0x5da4f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5da54  ldarg.1
0x5da55  ldarg.3
0x5da56  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x5da5b  stloc.1
0x5da5c  ldloca.s 1
0x5da5e  constrained. [mscorlib]System.Guid
0x5da64  callvirt instance string [mscorlib]System.Object::ToString()
0x5da69  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_CrmId(string value)
0x5da6e  ldarg.1
0x5da6f  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x5da74  brtrue.s loc_5DAB5
0x5da76  ldc.i4.0
0x5da77  stloc.2
0x5da78  ldarg.3
0x5da79  brfalse.s loc_5DA82
0x5da7b  ldarg.3
0x5da7c  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x5da81  stloc.2
0x5da82  ldloc.2
0x5da83  brtrue.s loc_5DAAE
0x5da85  ldarg.0
0x5da86  ldc.i4.4
0x5da87  ldstr    aTheItem0Object// "The item {0} object type is none, don't"...
0x5da8c  ldc.i4.2
0x5da8d  newarr   [mscorlib]System.Object
0x5da92  dup
0x5da93  ldc.i4.0
0x5da94  ldarg.1
0x5da95  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5da9a  stelem.ref
0x5da9b  dup
0x5da9c  ldc.i4.1
0x5da9d  ldarg.0
0x5da9e  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5daa3  stelem.ref
0x5daa4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5daa9  leave    loc_5DCDE
0x5daae  ldarg.1
0x5daaf  ldloc.2
0x5dab0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemObjectType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType value)
0x5dab5  ldarg.1
0x5dab6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x5dabb  brfalse.s loc_5DB15
0x5dabd  ldarg.1
0x5dabe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x5dac3  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem
0x5dac8  stloc.3
0x5dac9  ldarg.0
0x5daca  ldloc.3
0x5dacb  ldarg.3
0x5dacc  ldloca.s 4
0x5dace  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::ItemNeedsIdMappingRepair(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem exchangeItem, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping, [out] string& crmId)
0x5dad3  brfalse.s loc_5DAE6
0x5dad5  ldarg.1
0x5dad6  ldc.i4.7
0x5dad7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x5dadc  ldarg.1
0x5dadd  ldloc.s  4
0x5dadf  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_CrmId(string value)
0x5dae4  br.s     loc_5DB15
0x5dae6  ldarg.0
0x5dae7  ldloc.3
0x5dae8  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x5daed  ldarg.3
0x5daee  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::IsCopiedItem(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x5daf3  brfalse.s loc_5DB15
0x5daf5  ldarg.1
0x5daf6  ldc.i4.6
0x5daf7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x5dafc  ldarg.3
0x5dafd  brfalse.s loc_5DB15
0x5daff  ldarg.3
0x5db00  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x5db05  ldarg.1
0x5db06  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5db0b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5db10  brfalse.s loc_5DB15
0x5db12  ldnull
0x5db13  starg.s  3
0x5db15  ldarg.3
0x5db16  brfalse.s loc_5DB35
0x5db18  ldarg.3
0x5db19  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_IsUnlinkedInCrm()
0x5db1e  brfalse.s loc_5DB35
0x5db20  ldarg.1
0x5db21  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5db26  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5db2b  brtrue.s loc_5DB35
0x5db2d  ldarg.2
0x5db2e  ldarg.3
0x5db2f  ldc.i4.0
0x5db30  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::UpdateUnlinkedInCrm(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping, bool isUnlinkedInCrm)
0x5db35  ldarg.3
0x5db36  brtrue.s loc_5DB3B
0x5db38  ldc.i4.m1
0x5db39  br.s     loc_5DB41
0x5db3b  ldarg.3
0x5db3c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.UserDecision Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_UserDecision()
0x5db41  brtrue.s loc_5DB48
0x5db43  leave    loc_5DCDE
0x5db48  ldarg.0
0x5db49  ldarg.1
0x5db4a  ldarg.2
0x5db4b  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::CheckExceptionAppointmentChange(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo syncItemChangeInfo, class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations exchangeSyncIdMappingOperations)
0x5db50  brtrue.s loc_5DB92
0x5db52  ldarg.0
0x5db53  ldc.i4.4
0x5db54  ldstr    aDonTProcessThe// "Don't process the exception appointment"...
0x5db59  ldc.i4.4
0x5db5a  newarr   [mscorlib]System.Object
0x5db5f  dup
0x5db60  ldc.i4.0
0x5db61  ldarg.1
0x5db62  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5db67  stelem.ref
0x5db68  dup
0x5db69  ldc.i4.1
0x5db6a  ldarg.0
0x5db6b  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5db70  stelem.ref
0x5db71  dup
0x5db72  ldc.i4.2
0x5db73  ldarg.1
0x5db74  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5db79  stelem.ref
0x5db7a  dup
0x5db7b  ldc.i4.3
0x5db7c  ldarg.1
0x5db7d  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemChangeType()
0x5db82  box      Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5db87  stelem.ref
0x5db88  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5db8d  leave    loc_5DCDE
0x5db92  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::.ctor()
0x5db97  dup
0x5db98  ldarg.1
0x5db99  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSideSyncItemChangeInfo(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo value)
0x5db9e  dup
0x5db9f  ldarg.3
0x5dba0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper value)
0x5dba5  dup
0x5dba6  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::.ctor()
0x5dbab  dup
0x5dbac  ldarg.0
0x5dbad  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_OutputProvider()
0x5dbb2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_Provider(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider value)
0x5dbb7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_CrmSyncItemChangeInfo(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo value)
0x5dbbc  stloc.0
0x5dbbd  ldloc.0
0x5dbbe  ldstr    a297c518cA3a94a// "{297C518C-A3A9-4AF3-A88B-11A8546B813B}"
0x5dbc3  ldarg.0
0x5dbc4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5dbc9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5dbce  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::TestHookForSyncFailure(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData, string failureGuid, valuetype [mscorlib]System.Guid orgId)
0x5dbd3  ldarg.0
0x5dbd4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ISyncDataProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_SyncDataProvider()
0x5dbd9  ldloc.0
0x5dbda  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ISyncDataProvider::AddToCrmChange(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData)
0x5dbdf  leave    loc_5DCDE
0x5dbe4  stloc.s  5
0x5dbe6  ldloc.s  5
0x5dbe8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5dbed  ldstr    aShutdownEventR// "Shutdown event received"
0x5dbf2  callvirt instance bool [mscorlib]System.String::Contains(string)
0x5dbf7  brfalse.s loc_5DBFB
0x5dbf9  rethrow
0x5dbfb  ldarg.0
0x5dbfc  ldc.i4.1
0x5dbfd  ldstr    aFailedToAddThe_4// "Failed to add the items fetched from th"...
0x5dc02  ldc.i4.2
0x5dc03  newarr   [mscorlib]System.Object
0x5dc08  dup
0x5dc09  ldc.i4.0
0x5dc0a  ldarg.0
0x5dc0b  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5dc10  stelem.ref
0x5dc11  dup
0x5dc12  ldc.i4.1
0x5dc13  ldloc.s  5
0x5dc15  ldarg.0
0x5dc16  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5dc1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5dc20  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x5dc25  stelem.ref
0x5dc26  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5dc2b  ldarg.1
0x5dc2c  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x5dc31  stloc.s  6
0x5dc33  ldloc.s  6
0x5dc35  brtrue.s loc_5DC42
0x5dc37  ldarg.3
0x5dc38  brfalse.s loc_5DC42
0x5dc3a  ldarg.3
0x5dc3b  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x5dc40  stloc.s  6
0x5dc42  ldarg.1
0x5dc43  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x5dc48  brtrue.s loc_5DC51
0x5dc4a  ldsfld   string [mscorlib]System.String::Empty
0x5dc4f  br.s     loc_5DC5C
0x5dc51  ldarg.1
0x5dc52  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x5dc57  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Subject()
0x5dc5c  stloc.s  7
0x5dc5e  ldloc.s  5
0x5dc60  ldarg.0
0x5dc61  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5dc66  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x5dc6b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x5dc70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5dc75  ldloc.s  6
0x5dc77  ldloc.s  7
0x5dc79  ldc.i4.0
0x5dc7a  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::LogError(class [mscorlib]System.Exception ex, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, [opt] valuetype [mscorlib]System.Guid itemObjectId, [opt] int32 itemObjectTypeCode, [opt] string itemSubject, [opt] bool forceItemLevel)
0x5dc7f  ldloc.s  6
0x5dc81  brfalse.s loc_5DC9C
0x5dc83  ldarg.0
0x5dc84  ldarg.1
0x5dc85  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5dc8a  ldarg.1
0x5dc8b  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemChangeType()
0x5dc90  ldloc.s  6
0x5dc92  ldloc.s  5
0x5dc94  ldarg.3
0x5dc95  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::AddItemToItemFinderSyncErrors(string itemId, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType, class [mscorlib]System.Exception ex, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x5dc9a  br.s     loc_5DCC0
0x5dc9c  ldarg.0
0x5dc9d  ldc.i4.4
0x5dc9e  ldstr    aFailedToAddThe_5// "Failed to add the sync data {0} (the ob"...
0x5dca3  ldc.i4.2
0x5dca4  newarr   [mscorlib]System.Object
0x5dca9  dup
0x5dcaa  ldc.i4.0
0x5dcab  ldarg.1
0x5dcac  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5dcb1  stelem.ref
0x5dcb2  dup
0x5dcb3  ldc.i4.1
0x5dcb4  ldarg.0
0x5dcb5  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5dcba  stelem.ref
0x5dcbb  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5dcc0  leave.s  loc_5DCDE
0x5dcc2  ldc.i4.1
0x5dcc3  ldarg.0
0x5dcc4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5dcc9  ldstr    aAddtocrmchange// "AddToCrmChange"
0x5dcce  ldstr    asc_8A7C2// ""
0x5dcd3  ldstr    asc_8A7C2// ""
0x5dcd8  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5dcdd  endfinally
0x5dcde  ret
```
