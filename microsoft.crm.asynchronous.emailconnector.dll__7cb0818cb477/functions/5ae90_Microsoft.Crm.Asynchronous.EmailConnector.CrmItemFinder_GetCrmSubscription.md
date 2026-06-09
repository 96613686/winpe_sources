# Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::GetCrmSubscription

- ea: `0x5ae90`
- end: `0x5b194`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::GetCrmSubscription`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x5acf0`

## callees

- `0x7d00`
- `0x42280`
- `0x4da80`
- `0x57580`
- `0x57590`
- `0x575a0`
- `0x575b0`
- `0x575d0`
- `0x58a20`
- `0x58b30`
- `0x58c10`
- `0x5acd0`
- `0x5ae90`
- `0x5e4b0`
- `0x5e4c0`
- `0x5e500`
- `0x5e610`
- `0x62db0`

## string_xrefs

- `0x5aecf`: `CreateOutlookSubscriptionSubscriptionClientsRequest`
- `0x5af3a`: `CreateOutlookSubscriptionSubscriptionClientsRequest`

## pseudocode

```c

```

## disassembly

```asm
0x5ae90  ldc.i4.0
0x5ae91  ldarg.0
0x5ae92  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5ae97  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5ae9c  ldstr    asc_8A7C2// ""
0x5aea1  ldstr    asc_8A7C2// ""
0x5aea6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5aeab  ldarg.1
0x5aeac  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5aeb1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5aeb6  brtrue.s loc_5AEC8
0x5aeb8  ldarg.1
0x5aeb9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_SubscriptionId()
0x5aebe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5aec3  brfalse  loc_5B021
0x5aec8  ldc.i4.0
0x5aec9  ldarg.0
0x5aeca  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5aecf  ldstr    aCreateoutlooks// "CreateOutlookSubscriptionSubscriptionCl"...
0x5aed4  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5aed9  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5aede  ldstr    asc_8A7C2// ""
0x5aee3  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5aee8  ldstr    aSubscriptioncl_0// "subscriptionclients"
0x5aeed  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x5aef2  stloc.1
0x5aef3  ldloc.1
0x5aef4  ldstr    aMachinename_0// "machinename"
0x5aef9  ldstr    aExchangesync// "ExchangeSync"
0x5aefe  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x5af03  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.CreateOutlookSubscriptionSubscriptionClientsRequest::.ctor()
0x5af08  stloc.2
0x5af09  ldloc.2
0x5af0a  ldloc.1
0x5af0b  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.CreateOutlookSubscriptionSubscriptionClientsRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x5af10  ldarg.0
0x5af11  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::get__crmService()
0x5af16  ldloc.2
0x5af17  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5af1c  castclass [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.CreateOutlookSubscriptionSubscriptionClientsResponse
0x5af21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.CreateOutlookSubscriptionSubscriptionClientsResponse::get_id()
0x5af26  stloc.3
0x5af27  ldarg.1
0x5af28  ldloc.3
0x5af29  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x5af2e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::set_ClientId(string value)
0x5af33  ldc.i4.1
0x5af34  ldarg.0
0x5af35  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5af3a  ldstr    aCreateoutlooks// "CreateOutlookSubscriptionSubscriptionCl"...
0x5af3f  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5af44  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5af49  ldstr    asc_8A7C2// ""
0x5af4e  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5af53  ldc.i4.0
0x5af54  ldarg.0
0x5af55  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5af5a  ldstr    aRetrieveclient// "RetrieveClientSubscriptionSubscriptionC"...
0x5af5f  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5af64  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5af69  ldstr    asc_8A7C2// ""
0x5af6e  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5af73  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RetrieveClientSubscriptionSubscriptionClientsRequest::.ctor()
0x5af78  stloc.s  4
0x5af7a  ldloc.s  4
0x5af7c  ldloc.3
0x5af7d  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RetrieveClientSubscriptionSubscriptionClientsRequest::set_ClientId(valuetype [mscorlib]System.Guid)
0x5af82  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x5af87  stloc.s  5
0x5af89  ldloc.s  5
0x5af8b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::get_Columns()
0x5af90  ldstr    aSubscriptionid// "subscriptionid"
0x5af95  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5af9a  ldloc.s  4
0x5af9c  ldloc.s  5
0x5af9e  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RetrieveClientSubscriptionSubscriptionClientsRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x5afa3  ldarg.0
0x5afa4  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::get__crmService()
0x5afa9  ldloc.s  4
0x5afab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5afb0  castclass [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RetrieveClientSubscriptionSubscriptionClientsResponse
0x5afb5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RetrieveClientSubscriptionSubscriptionClientsResponse::get_Entity()
0x5afba  stloc.s  6
0x5afbc  ldarg.1
0x5afbd  ldloc.s  6
0x5afbf  ldstr    aSubscriptionid// "subscriptionid"
0x5afc4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5afc9  unbox.any [mscorlib]System.Guid
0x5afce  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x5afd3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::set_SubscriptionId(string value)
0x5afd8  ldc.i4.1
0x5afd9  ldarg.0
0x5afda  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5afdf  ldstr    aRetrieveclient// "RetrieveClientSubscriptionSubscriptionC"...
0x5afe4  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5afe9  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5afee  ldstr    asc_8A7C2// ""
0x5aff3  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5aff8  ldarg.0
0x5aff9  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5affe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x5b003  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x5b008  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x5b00d  stloc.s  7
0x5b00f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x5b014  ldloc.s  7
0x5b016  ldarg.0
0x5b017  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b01c  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::RemoveEntry(var<u1>, !!T0)
0x5b021  ldc.i4.0
0x5b022  ldarg.0
0x5b023  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b028  ldstr    aIsprimaryclien// "IsPrimaryClientSubscriptionClientsReque"...
0x5b02d  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5b032  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5b037  ldstr    asc_8A7C2// ""
0x5b03c  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5b041  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.IsPrimaryClientSubscriptionClientsRequest::.ctor()
0x5b046  stloc.0
0x5b047  ldloc.0
0x5b048  ldarg.1
0x5b049  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5b04e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5b053  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.IsPrimaryClientSubscriptionClientsRequest::set_ClientId(valuetype [mscorlib]System.Guid)
0x5b058  ldarg.0
0x5b059  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::get__crmService()
0x5b05e  ldloc.0
0x5b05f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5b064  castclass [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.IsPrimaryClientSubscriptionClientsResponse
0x5b069  ldc.i4.1
0x5b06a  ldarg.0
0x5b06b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b070  ldstr    aIsprimaryclien// "IsPrimaryClientSubscriptionClientsReque"...
0x5b075  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5b07a  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5b07f  ldstr    asc_8A7C2// ""
0x5b084  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5b089  callvirt instance bool [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.IsPrimaryClientSubscriptionClientsResponse::get_isPrimaryClient()
0x5b08e  brtrue.s loc_5B0FE
0x5b090  ldc.i4.0
0x5b091  ldarg.0
0x5b092  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b097  ldstr    aSetprimaryclie// "SetPrimaryClientSubscriptionClientsRequ"...
0x5b09c  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5b0a1  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5b0a6  ldstr    asc_8A7C2// ""
0x5b0ab  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5b0b0  ldarg.1
0x5b0b1  ldc.i4.1
0x5b0b2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::set_RebuildIdMapping(bool value)
0x5b0b7  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetPrimaryClientSubscriptionClientsRequest::.ctor()
0x5b0bc  stloc.s  8
0x5b0be  ldloc.s  8
0x5b0c0  ldarg.1
0x5b0c1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5b0c6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5b0cb  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetPrimaryClientSubscriptionClientsRequest::set_ClientId(valuetype [mscorlib]System.Guid)
0x5b0d0  ldarg.0
0x5b0d1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::get__crmService()
0x5b0d6  ldloc.s  8
0x5b0d8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5b0dd  pop
0x5b0de  ldc.i4.1
0x5b0df  ldarg.0
0x5b0e0  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b0e5  ldstr    aSetprimaryclie// "SetPrimaryClientSubscriptionClientsRequ"...
0x5b0ea  ldstr    aSubscriptioncl// "SubscriptionClients"
0x5b0ef  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5b0f4  ldstr    asc_8A7C2// ""
0x5b0f9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x5b0fe  ldarg.0
0x5b0ff  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5b104  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider
0x5b109  ldarg.1
0x5b10a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_SubscriptionId()
0x5b10f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::set_SubscriptionId(string value)
0x5b114  ldarg.0
0x5b115  ldc.i4.4
0x5b116  ldstr    aGotTheClientId// "Got the client id {0} and subscription "...
0x5b11b  ldc.i4.3
0x5b11c  newarr   [mscorlib]System.Object
0x5b121  dup
0x5b122  ldc.i4.0
0x5b123  ldarg.1
0x5b124  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5b129  stelem.ref
0x5b12a  dup
0x5b12b  ldc.i4.1
0x5b12c  ldarg.1
0x5b12d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_SubscriptionId()
0x5b132  stelem.ref
0x5b133  dup
0x5b134  ldc.i4.2
0x5b135  ldarg.0
0x5b136  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5b13b  stelem.ref
0x5b13c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5b141  leave.s  loc_5B193
0x5b143  stloc.s  9
0x5b145  ldarg.0
0x5b146  ldc.i4.2
0x5b147  ldstr    aFailedToGetThe_2// "Failed to Get the client id and subscri"...
0x5b14c  ldc.i4.2
0x5b14d  newarr   [mscorlib]System.Object
0x5b152  dup
0x5b153  ldc.i4.0
0x5b154  ldarg.0
0x5b155  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5b15a  stelem.ref
0x5b15b  dup
0x5b15c  ldc.i4.1
0x5b15d  ldloc.s  9
0x5b15f  ldarg.0
0x5b160  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b165  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5b16a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x5b16f  stelem.ref
0x5b170  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5b175  rethrow
0x5b177  ldc.i4.1
0x5b178  ldarg.0
0x5b179  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b17e  ldstr    aGetcrmsubscrip// "GetCrmSubscription"
0x5b183  ldstr    asc_8A7C2// ""
0x5b188  ldstr    asc_8A7C2// ""
0x5b18d  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5b192  endfinally
0x5b193  ret
```
