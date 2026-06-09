# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.RebuildMappingStep::ProvisionalFetchChangesForRebuildIdMapping

- ea: `0x7ecb0`
- end: `0x7ede9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.RebuildMappingStep::ProvisionalFetchChangesForRebuildIdMapping`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x7ea60`

## callees

- `0x4da80`
- `0x58c10`
- `0x5a940`
- `0x5a990`
- `0x5cb00`
- `0x5cd00`
- `0x6add0`
- `0x7ecb0`

## string_xrefs

- `0x7ed77`: `IPM.Task`
- `0x7ed85`: `IPM.Task`

## pseudocode

```c

```

## disassembly

```asm
0x7ecb0  ldc.i4.0
0x7ecb1  ldarg.0
0x7ecb2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_ACTContext()
0x7ecb7  ldstr    aProvisionalfet// "ProvisionalFetchChangesForRebuildIdMapp"...
0x7ecbc  ldstr    asc_8A7C2// ""
0x7ecc1  ldstr    asc_8A7C2// ""
0x7ecc6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x7eccb  ldarg.0
0x7eccc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_StepContext()
0x7ecd1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeFinder()
0x7ecd6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>>::.ctor()
0x7ecdb  stloc.0
0x7ecdc  ldarg.0
0x7ecdd  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_StepContext()
0x7ece2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeDataProvider()
0x7ece7  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::get_ExchangeService()
0x7ecec  ldc.i4.0
0x7eced  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::Bind(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName)
0x7ecf2  stloc.1
0x7ecf3  ldloc.1
0x7ecf4  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_Id()
0x7ecf9  stloc.2
0x7ecfa  dup
0x7ecfb  ldloc.2
0x7ecfc  ldstr    aIpmAppointment// "IPM.Appointment"
0x7ed01  ldloc.0
0x7ed02  ldc.i4.2
0x7ed03  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::PagedFindItemMappingIdsByFolder(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId folderId, string folderClass, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7ed08  dup
0x7ed09  ldloc.1
0x7ed0a  ldstr    aIpmAppointment// "IPM.Appointment"
0x7ed0f  ldloc.0
0x7ed10  ldc.i4.2
0x7ed11  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::SubFolderFetchChangesForRebuildIdMapping(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder parentFolder, string folderClass, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7ed16  ldarg.0
0x7ed17  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_StepContext()
0x7ed1c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeDataProvider()
0x7ed21  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::get_ExchangeService()
0x7ed26  ldc.i4.1
0x7ed27  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::Bind(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName)
0x7ed2c  stloc.3
0x7ed2d  ldloc.3
0x7ed2e  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_Id()
0x7ed33  stloc.s  4
0x7ed35  dup
0x7ed36  ldloc.s  4
0x7ed38  ldstr    aIpmContact// "IPM.Contact"
0x7ed3d  ldloc.0
0x7ed3e  ldc.i4.1
0x7ed3f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::PagedFindItemMappingIdsByFolder(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId folderId, string folderClass, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7ed44  dup
0x7ed45  ldloc.3
0x7ed46  ldstr    aIpmContact// "IPM.Contact"
0x7ed4b  ldloc.0
0x7ed4c  ldc.i4.1
0x7ed4d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::SubFolderFetchChangesForRebuildIdMapping(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder parentFolder, string folderClass, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7ed52  ldarg.0
0x7ed53  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_StepContext()
0x7ed58  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeDataProvider()
0x7ed5d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::get_ExchangeService()
0x7ed62  ldc.i4.s 9
0x7ed64  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::Bind(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName)
0x7ed69  stloc.s  5
0x7ed6b  ldloc.s  5
0x7ed6d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_Id()
0x7ed72  stloc.s  6
0x7ed74  dup
0x7ed75  ldloc.s  6
0x7ed77  ldstr    aIpmTask// "IPM.Task"
0x7ed7c  ldloc.0
0x7ed7d  ldc.i4.3
0x7ed7e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::PagedFindItemMappingIdsByFolder(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId folderId, string folderClass, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7ed83  ldloc.s  5
0x7ed85  ldstr    aIpmTask// "IPM.Task"
0x7ed8a  ldloc.0
0x7ed8b  ldc.i4.3
0x7ed8c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::SubFolderFetchChangesForRebuildIdMapping(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder parentFolder, string folderClass, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7ed91  ldloc.0
0x7ed92  stloc.s  7
0x7ed94  leave.s  loc_7EDE6
0x7ed96  stloc.s  8
0x7ed98  ldarg.0
0x7ed99  ldc.i4.1
0x7ed9a  ldstr    aFailedToFetchT_3// "Failed to fetch the changes from the ex"...
0x7ed9f  ldc.i4.2
0x7eda0  newarr   [mscorlib]System.Object
0x7eda5  dup
0x7eda6  ldc.i4.0
0x7eda7  ldarg.0
0x7eda8  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7edad  stelem.ref
0x7edae  dup
0x7edaf  ldc.i4.1
0x7edb0  ldloc.s  8
0x7edb2  ldarg.0
0x7edb3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_ACTContext()
0x7edb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x7edbd  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x7edc2  stelem.ref
0x7edc3  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7edc8  rethrow
0x7edca  ldc.i4.1
0x7edcb  ldarg.0
0x7edcc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>>::get_ACTContext()
0x7edd1  ldstr    aProvisionalfet// "ProvisionalFetchChangesForRebuildIdMapp"...
0x7edd6  ldstr    asc_8A7C2// ""
0x7eddb  ldstr    asc_8A7C2// ""
0x7ede0  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x7ede5  endfinally
0x7ede6  ldloc.s  7
0x7ede8  ret
```
