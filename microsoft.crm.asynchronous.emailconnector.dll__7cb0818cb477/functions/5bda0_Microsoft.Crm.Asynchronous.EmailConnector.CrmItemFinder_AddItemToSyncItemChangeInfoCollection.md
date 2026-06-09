# Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::AddItemToSyncItemChangeInfoCollection

- ea: `0x5bda0`
- end: `0x5c009`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::AddItemToSyncItemChangeInfoCollection`
- size: `617`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x5b480`
- `0x5b7f0`

## callees

- `0x4da80`
- `0x549e0`
- `0x56ec0`
- `0x58a40`
- `0x58a60`
- `0x58c10`
- `0x59a30`
- `0x5a9e0`
- `0x5bda0`
- `0x5c010`
- `0x5e4b0`
- `0x5e4c0`
- `0x5e500`
- `0x5e530`
- `0x5e560`
- `0x5e610`
- `0x5ead0`
- `0x5eae0`
- `0x5eaf0`
- `0x5eb30`
- `0x5eb50`
- `0x5ebb0`
- `0x5ebd0`
- `0x5ebe0`
- `0x60520`
- `0x70b20`

## string_xrefs

- `0x5be46`: `createdon`
- `0x5bebb`: `The item {0}, ownerId {1} has been added to the sync item collection for the mailbox : {2}. ItemObjectType: {3}, CreatedOn: {4}, ModifiedOn: {5}. Item Change type: {6}.`

## pseudocode

```c

```

## disassembly

```asm
0x5bda0  ldc.i4.0
0x5bda1  ldarg.0
0x5bda2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5bda7  ldstr    aAdditemstosync// "AddItemsToSyncItemChangeInfoCollection"
0x5bdac  ldarga.s 3
0x5bdae  constrained. Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5bdb4  callvirt instance string [mscorlib]System.Object::ToString()
0x5bdb9  ldarga.s 4
0x5bdbb  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5bdc1  callvirt instance string [mscorlib]System.Object::ToString()
0x5bdc6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5bdcb  ldarg.2
0x5bdcc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bdd1  brfalse.s loc_5BDDE
0x5bdd3  ldstr    aInvalidInput// "Invalid input."
0x5bdd8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5bddd  throw
0x5bdde  ldarg.s  4
0x5bde0  ldc.i4   0x1069
0x5bde5  bne.un.s loc_5BE10
0x5bde7  ldarg.3
0x5bde8  ldc.i4.2
0x5bde9  beq.s    loc_5BE10
0x5bdeb  ldarg.1
0x5bdec  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmAppointmentItem::GetSeriesIdIfIsException(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x5bdf1  stloc.s  4
0x5bdf3  ldloc.s  4
0x5bdf5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bdfa  brtrue.s loc_5BE10
0x5bdfc  ldc.i4   0x1F40
0x5be01  starg.s  4
0x5be03  ldarg.0
0x5be04  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::_recurringAppointmentSeriesId
0x5be09  ldloc.s  4
0x5be0b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5be10  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::.ctor()
0x5be15  stloc.0
0x5be16  ldloc.0
0x5be17  ldarg.0
0x5be18  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5be1d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_Provider(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider value)
0x5be22  ldloc.0
0x5be23  ldarg.2
0x5be24  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_CrmId(string value)
0x5be29  ldloc.0
0x5be2a  ldarg.3
0x5be2b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x5be30  ldloc.0
0x5be31  ldarg.s  4
0x5be33  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemObjectType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType value)
0x5be38  ldarg.1
0x5be39  ldstr    aOwnerid// "ownerid"
0x5be3e  ldnull
0x5be3f  call     T0x2B0000AB
0x5be44  stloc.1
0x5be45  ldarg.1
0x5be46  ldstr    aCreatedon// "createdon"
0x5be4b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x5be50  call     T0x2B0000AC
0x5be55  stloc.2
0x5be56  ldarg.1
0x5be57  ldstr    aModifiedon// "modifiedon"
0x5be5c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x5be61  call     T0x2B0000AC
0x5be66  stloc.3
0x5be67  ldarg.3
0x5be68  ldc.i4.2
0x5be69  beq.s    loc_5BEA7
0x5be6b  ldarg.0
0x5be6c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5be71  ldarg.s  4
0x5be73  ldarg.0
0x5be74  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5be79  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider
0x5be7e  ldarg.1
0x5be7f  ldarg.0
0x5be80  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappings Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_SyncPropertiesMappings()
0x5be85  ldarg.s  4
0x5be87  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappings::GetSyncPropertiesMapping(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType objectType)
0x5be8c  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType, class Microsoft.Crm.Asynchronous.EmailConnector.IProvider provider, object item, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping syncPropertiesMapping)
0x5be91  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x5be96  stloc.s  5
0x5be98  ldloc.0
0x5be99  ldloc.s  5
0x5be9b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_SyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase value)
0x5bea0  ldloc.0
0x5bea1  ldloc.3
0x5bea2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_Timestamp(valuetype [mscorlib]System.DateTime value)
0x5bea7  ldarg.0
0x5bea8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo> Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_SyncItemChangeInfoCollection()
0x5bead  ldloc.0
0x5beae  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5beb3  ldloc.0
0x5beb4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>::set_Item(var<u1>, !!T0)
0x5beb9  ldarg.0
0x5beba  ldc.i4.4
0x5bebb  ldstr    aTheItem0Owneri// "The item {0}, ownerId {1} has been adde"...
0x5bec0  ldc.i4.7
0x5bec1  newarr   [mscorlib]System.Object
0x5bec6  dup
0x5bec7  ldc.i4.0
0x5bec8  ldarg.2
0x5bec9  stelem.ref
0x5beca  dup
0x5becb  ldc.i4.1
0x5becc  ldloc.1
0x5becd  brtrue.s loc_5BED6
0x5becf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bed4  br.s     loc_5BEDC
0x5bed6  ldloc.1
0x5bed7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x5bedc  box      [mscorlib]System.Guid
0x5bee1  stelem.ref
0x5bee2  dup
0x5bee3  ldc.i4.2
0x5bee4  ldarg.0
0x5bee5  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5beea  stelem.ref
0x5beeb  dup
0x5beec  ldc.i4.3
0x5beed  ldarg.s  4
0x5beef  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5bef4  stelem.ref
0x5bef5  dup
0x5bef6  ldc.i4.4
0x5bef7  ldloc.2
0x5bef8  box      [mscorlib]System.DateTime
0x5befd  stelem.ref
0x5befe  dup
0x5beff  ldc.i4.5
0x5bf00  ldloc.3
0x5bf01  box      [mscorlib]System.DateTime
0x5bf06  stelem.ref
0x5bf07  dup
0x5bf08  ldc.i4.6
0x5bf09  ldarg.3
0x5bf0a  box      Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5bf0f  stelem.ref
0x5bf10  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5bf15  leave    loc_5C008
0x5bf1a  stloc.s  6
0x5bf1c  ldloc.s  6
0x5bf1e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5bf23  ldstr    aShutdownEventR// "Shutdown event received"
0x5bf28  callvirt instance bool [mscorlib]System.String::Contains(string)
0x5bf2d  brfalse.s loc_5BF31
0x5bf2f  rethrow
0x5bf31  ldarg.0
0x5bf32  ldc.i4.1
0x5bf33  ldstr    aFailedToAddThe// "Failed to add the item {0} to the sync "...
0x5bf38  ldc.i4.3
0x5bf39  newarr   [mscorlib]System.Object
0x5bf3e  dup
0x5bf3f  ldc.i4.0
0x5bf40  ldarg.2
0x5bf41  stelem.ref
0x5bf42  dup
0x5bf43  ldc.i4.1
0x5bf44  ldarg.0
0x5bf45  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5bf4a  stelem.ref
0x5bf4b  dup
0x5bf4c  ldc.i4.2
0x5bf4d  ldloc.s  6
0x5bf4f  ldarg.0
0x5bf50  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5bf55  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5bf5a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x5bf5f  stelem.ref
0x5bf60  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5bf65  ldsfld   string [mscorlib]System.String::Empty
0x5bf6a  stloc.s  7
0x5bf6c  ldarg.1
0x5bf6d  brfalse.s loc_5BFA8
0x5bf6f  ldarg.0
0x5bf70  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5bf75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5bf7a  ldarg.s  4
0x5bf7c  call     int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetCrmEntityCode(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x5bf81  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetPrimaryFieldAttributeName(valuetype [mscorlib]System.Guid organizationId, int32 entityCode)
0x5bf86  stloc.s  9
0x5bf88  ldarg.1
0x5bf89  ldloc.s  9
0x5bf8b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x5bf90  brtrue.s loc_5BF99
0x5bf92  ldsfld   string [mscorlib]System.String::Empty
0x5bf97  br.s     loc_5BFA6
0x5bf99  ldarg.1
0x5bf9a  ldloc.s  9
0x5bf9c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5bfa1  castclass [mscorlib]System.String
0x5bfa6  stloc.s  7
0x5bfa8  ldarg.0
0x5bfa9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5bfae  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_StepContext()
0x5bfb3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x5bfb8  ldsfld   string [mscorlib]System.String::Empty
0x5bfbd  ldarg.2
0x5bfbe  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::RetrieveExchangeSyncIdMappings(string exchangeEntryId, string crmId)
0x5bfc3  call     T0x2B00009C
0x5bfc8  stloc.s  8
0x5bfca  ldarg.0
0x5bfcb  ldarg.2
0x5bfcc  ldarg.3
0x5bfcd  ldarg.s  4
0x5bfcf  ldloc.s  7
0x5bfd1  ldloc.s  6
0x5bfd3  ldloc.s  8
0x5bfd5  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::AddItemToItemFinderSyncErrors(string crmId, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType, string itemSubject, class [mscorlib]System.Exception ex, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x5bfda  leave.s  loc_5C008
0x5bfdc  ldc.i4.1
0x5bfdd  ldarg.0
0x5bfde  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5bfe3  ldstr    aAdditemstosync// "AddItemsToSyncItemChangeInfoCollection"
0x5bfe8  ldarga.s 3
0x5bfea  constrained. Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5bff0  callvirt instance string [mscorlib]System.Object::ToString()
0x5bff5  ldarga.s 4
0x5bff7  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5bffd  callvirt instance string [mscorlib]System.Object::ToString()
0x5c002  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5c007  endfinally
0x5c008  ret
```
