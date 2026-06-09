# Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessRegularMailbox

- ea: `0x3e6e0`
- end: `0x3f04c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessRegularMailbox`
- size: `2412`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0x144f0`
- `0x305c0`
- `0x305e0`
- `0x30650`
- `0x30660`
- `0x32820`
- `0x32960`
- `0x32970`
- `0x329c0`
- `0x329e0`
- `0x32a00`
- `0x32a20`
- `0x32a60`
- `0x3ab40`
- `0x3ab80`
- `0x3ad70`
- `0x3adb0`
- `0x3ae30`
- `0x3ae70`
- `0x3dbf0`
- `0x3e6e0`
- `0x3f6a0`
- `0x41980`
- `0x41a10`
- `0x41a20`
- `0x41a30`
- `0x41ab0`
- `0x41ac0`
- `0x41af0`
- `0x41b90`
- `0x41bb0`
- `0x41d20`
- `0x41d50`
- `0x41dd0`
- `0x41fa0`
- `0x41fc0`
- `0x41fd0`
- `0x41fe0`
- `0x41ff0`
- `0x42050`
- `0x42060`
- `0x420a0`
- `0x71330`
- `0x714f0`
- `0x71550`
- `0x71570`
- `0x7aa20`
- `0x814e0`
- `0x81500`
- `0x82060`

## string_xrefs

- `0x3e839`: `No processing needed for NotLinked message if not folder tracking item. Also, no processing needed for WillBeUnlinked message. CrmId:{0}. ExchangeId:{1}. Link state:{2}. Mailbox:{3}.`
- `0x3e912`: `Update regarding object info in crm for an item. CrmId:{0}. ExchangeId:{1}. Link state:{2}. Mailbox:{3}.`
- `0x3e9e2`: `Item which can be promoted has attachments and hence processresult is set to GettingAttachmentPromoteLater. CrmId:{0}. ExchangeId:{1}. Link state:{2}. Mailbox:{3}.`
- `0x3ec8b`: `Updated regarding object info for the email enity under folder. CrmId:{0}. Exchange Id:{1}. Folder:{2}. Mailbox:{3}.`
- `0x3ef9e`: `Couldn't accept message to get-attachment. CrmId:{0}. ExchangeId:{1} DeleteEmailsAfterProcessing:{2}. Mailbox:{3}.`

## pseudocode

```c

```

## disassembly

```asm
0x3e6e0  ldc.i4.0
0x3e6e1  stloc.0
0x3e6e2  br       loc_3F030
0x3e6e7  ldarg.0
0x3e6e8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e6ed  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e6f2  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x3e6f7  ldarg.0
0x3e6f8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e6fd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e702  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x3e707  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3e70c  unbox.any [mscorlib]System.Int32
0x3e711  ldc.i4.1
0x3e712  add
0x3e713  box      [mscorlib]System.Int32
0x3e718  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::set_Item(string attributeName, object value)
0x3e71d  ldarg.0
0x3e71e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e723  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e728  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3e72d  ldloc.0
0x3e72e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::get_Item(!!T0)
0x3e733  castclass Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage
0x3e738  stloc.1
0x3e739  ldloc.1
0x3e73a  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x3e73f  ldarg.0
0x3e740  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3e745  callvirt instance valuetype [mscorlib]System.DateTime LoadingEmailCollection::get_LoadingStartTimeStamp()
0x3e74a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_LoadPropertiesStartTimeStamp(valuetype [mscorlib]System.DateTime value)
0x3e74f  ldloc.1
0x3e750  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x3e755  ldarg.0
0x3e756  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3e75b  callvirt instance valuetype [mscorlib]System.DateTime LoadingEmailCollection::get_LoadingEndTimeStamp()
0x3e760  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_LoadPropertiesEndTimeStamp(valuetype [mscorlib]System.DateTime value)
0x3e765  ldarg.0
0x3e766  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e76b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e770  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::set_DeliveredEmailCrmId(valuetype [mscorlib]System.Guid value)
0x3e775  ldarg.0
0x3e776  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3e77b  ldarg.0
0x3e77c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e781  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e786  ldstr    aMailboxid// "mailboxid"
0x3e78b  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3e790  unbox.any [mscorlib]System.Guid
0x3e795  ldloc.1
0x3e796  ldarg.0
0x3e797  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3e79c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetEmptySyncResponse()
0x3e7a1  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, valuetype [mscorlib]System.Guid mailboxId, class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse)
0x3e7a6  stloc.2
0x3e7a7  ldarg.0
0x3e7a8  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::EmailMessageUpdateRequired()
0x3e7ad  stloc.3
0x3e7ae  ldloc.3
0x3e7af  brtrue.s loc_3E7C7
0x3e7b1  ldarg.0
0x3e7b2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e7b7  ldloc.1
0x3e7b8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_ParentFolderId()
0x3e7bd  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::IsFolderBasedTrackingFolder(string p)
0x3e7c2  brfalse  loc_3ED30
0x3e7c7  ldloc.1
0x3e7c8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_CrmId()
0x3e7cd  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3e7d2  brfalse.s loc_3E7D7
0x3e7d4  ldnull
0x3e7d5  br.s     loc_3E7E8
0x3e7d7  ldarg.0
0x3e7d8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e7dd  ldloc.1
0x3e7de  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_CrmId()
0x3e7e3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::RetrieveEmailEntity(string p)
0x3e7e8  stloc.s  4
0x3e7ea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e7ef  stloc.s  5
0x3e7f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x3e7f6  stloc.s  6
0x3e7f8  ldloc.1
0x3e7f9  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3e7fe  brtrue.s loc_3E813
0x3e800  ldarg.0
0x3e801  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e806  ldloc.1
0x3e807  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_ParentFolderId()
0x3e80c  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::IsFolderBasedTrackingFolder(string p)
0x3e811  brfalse.s loc_3E81F
0x3e813  ldloc.1
0x3e814  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3e819  ldc.i4.3
0x3e81a  bne.un   loc_3E8D3
0x3e81f  ldloc.s  4
0x3e821  brtrue.s loc_3E830
0x3e823  ldarg.0
0x3e824  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e829  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_DeliveredEmailCrmId()
0x3e82e  br.s     loc_3E837
0x3e830  ldloc.s  4
0x3e832  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x3e837  stloc.s  5
0x3e839  ldstr    aNoProcessingNe// "No processing needed for NotLinked mess"...
0x3e83e  ldc.i4.4
0x3e83f  newarr   [mscorlib]System.Object
0x3e844  dup
0x3e845  ldc.i4.0
0x3e846  ldloc.s  5
0x3e848  box      [mscorlib]System.Guid
0x3e84d  stelem.ref
0x3e84e  dup
0x3e84f  ldc.i4.1
0x3e850  ldloc.1
0x3e851  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3e856  brtrue.s loc_3E85F
0x3e858  ldsfld   string [mscorlib]System.String::Empty
0x3e85d  br.s     loc_3E86A
0x3e85f  ldloc.1
0x3e860  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3e865  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType::get_Id()
0x3e86a  stelem.ref
0x3e86b  dup
0x3e86c  ldc.i4.2
0x3e86d  ldloc.1
0x3e86e  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3e873  box      Microsoft.Crm.Asynchronous.EmailConnector.LinkState
0x3e878  stelem.ref
0x3e879  dup
0x3e87a  ldc.i4.3
0x3e87b  ldarg.0
0x3e87c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e881  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e886  ldstr    aMailboxid// "mailboxid"
0x3e88b  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3e890  stelem.ref
0x3e891  call     string [mscorlib]System.String::Format(string, object[])
0x3e896  stloc.s  7
0x3e898  ldarg.0
0x3e899  ldc.i4.3
0x3e89a  ldloc.s  7
0x3e89c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x3e8a1  ldloc.2
0x3e8a2  ldarg.0
0x3e8a3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3e8a8  ldloc.s  7
0x3e8aa  ldc.i4.0
0x3e8ab  ldc.i4.0
0x3e8ac  ldstr    asc_8A7C2// ""
0x3e8b1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x3e8b6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x3e8bb  ldloc.2
0x3e8bc  ldloca.s 5
0x3e8be  constrained. [mscorlib]System.Guid
0x3e8c4  callvirt instance string [mscorlib]System.Object::ToString()
0x3e8c9  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::set_CrmId(string value)
0x3e8ce  br       loc_3ECE2
0x3e8d3  ldloc.s  4
0x3e8d5  brfalse  loc_3E98C
0x3e8da  ldarg.0
0x3e8db  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e8e0  ldloc.1
0x3e8e1  ldloc.s  4
0x3e8e3  ldloc.s  6
0x3e8e5  ldarg.0
0x3e8e6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e8eb  ldloc.1
0x3e8ec  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_ParentFolderId()
0x3e8f1  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::IsFolderBasedTrackingFolder(string p)
0x3e8f6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::UpdateRegardingInfoInCrm(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity emailEntity, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> regardingInfoForExchange, bool p)
0x3e8fb  ldloc.s  4
0x3e8fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x3e902  stloc.s  5
0x3e904  ldloc.1
0x3e905  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x3e90a  ldc.i4.6
0x3e90b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_ProcessResult(int32 value)
0x3e910  ldarg.0
0x3e911  ldc.i4.3
0x3e912  ldstr    aUpdateRegardin// "Update regarding object info in crm for"...
0x3e917  ldc.i4.4
0x3e918  newarr   [mscorlib]System.Object
0x3e91d  dup
0x3e91e  ldc.i4.0
0x3e91f  ldloc.s  5
0x3e921  box      [mscorlib]System.Guid
0x3e926  stelem.ref
0x3e927  dup
0x3e928  ldc.i4.1
0x3e929  ldloc.1
0x3e92a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3e92f  brtrue.s loc_3E938
0x3e931  ldsfld   string [mscorlib]System.String::Empty
0x3e936  br.s     loc_3E943
0x3e938  ldloc.1
0x3e939  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3e93e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType::get_Id()
0x3e943  stelem.ref
0x3e944  dup
0x3e945  ldc.i4.2
0x3e946  ldloc.1
0x3e947  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3e94c  box      Microsoft.Crm.Asynchronous.EmailConnector.LinkState
0x3e951  stelem.ref
0x3e952  dup
0x3e953  ldc.i4.3
0x3e954  ldarg.0
0x3e955  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e95a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e95f  ldstr    aMailboxid// "mailboxid"
0x3e964  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3e969  stelem.ref
0x3e96a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3e96f  ldloc.2
0x3e970  ldarg.0
0x3e971  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e976  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_SyncResponse()
0x3e97b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x3e980  ldloc.2
0x3e981  ldc.i4.2
0x3e982  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_ChangeTypeInRemoteServer(valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType value)
0x3e987  br       loc_3ECE2
0x3e98c  ldarg.0
0x3e98d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e992  ldloc.1
0x3e993  ldloca.s 5
0x3e995  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::CheckPromote(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, [out] valuetype [mscorlib]System.Guid& crmidOfItemToUpdate)
0x3e99a  brfalse  loc_3EBAD
0x3e99f  ldloc.1
0x3e9a0  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_HasAttachments()
0x3e9a5  brfalse  loc_3EA44
0x3e9aa  ldarg.0
0x3e9ab  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e9b0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e9b5  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x3e9ba  brfalse.s loc_3E9C4
0x3e9bc  ldarg.0
0x3e9bd  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessAttachmentsForSynchronousEws()
0x3e9c2  br.s     loc_3E9C8
0x3e9c4  ldloc.0
0x3e9c5  ldc.i4.1
0x3e9c6  add
0x3e9c7  stloc.0
0x3e9c8  ldloc.1
0x3e9c9  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x3e9ce  ldc.i4.4
0x3e9cf  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_ProcessResult(int32 value)
0x3e9d4  ldarg.0
0x3e9d5  ldloc.1
0x3e9d6  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x3e9db  call     T0x2B000078
0x3e9e0  ldarg.0
0x3e9e1  ldc.i4.3
0x3e9e2  ldstr    aItemWhichCanBe// "Item which can be promoted has attachme"...
0x3e9e7  ldc.i4.4
0x3e9e8  newarr   [mscorlib]System.Object
0x3e9ed  dup
0x3e9ee  ldc.i4.0
0x3e9ef  ldloc.s  5
0x3e9f1  box      [mscorlib]System.Guid
0x3e9f6  stelem.ref
0x3e9f7  dup
0x3e9f8  ldc.i4.1
0x3e9f9  ldloc.1
0x3e9fa  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3e9ff  brtrue.s loc_3EA08
0x3ea01  ldsfld   string [mscorlib]System.String::Empty
0x3ea06  br.s     loc_3EA13
0x3ea08  ldloc.1
0x3ea09  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3ea0e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType::get_Id()
0x3ea13  stelem.ref
0x3ea14  dup
0x3ea15  ldc.i4.2
0x3ea16  ldloc.1
0x3ea17  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3ea1c  box      Microsoft.Crm.Asynchronous.EmailConnector.LinkState
0x3ea21  stelem.ref
0x3ea22  dup
0x3ea23  ldc.i4.3
0x3ea24  ldarg.0
0x3ea25  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ea2a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3ea2f  ldstr    aMailboxid// "mailboxid"
0x3ea34  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3ea39  stelem.ref
0x3ea3a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3ea3f  br       loc_3F030
0x3ea44  ldarg.0
0x3ea45  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ea4a  ldloc.1
0x3ea4b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::DeliverPromote(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage)
0x3ea50  ldarg.0
0x3ea51  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ea56  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_DeliveredEmailCrmId()
0x3ea5b  stloc.s  5
0x3ea5d  ldarg.0
0x3ea5e  ldloc.1
0x3ea5f  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
  ... truncated ...
```
