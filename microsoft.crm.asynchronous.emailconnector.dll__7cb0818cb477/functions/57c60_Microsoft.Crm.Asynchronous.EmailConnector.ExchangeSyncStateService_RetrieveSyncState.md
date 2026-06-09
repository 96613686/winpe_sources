# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::RetrieveSyncState

- ea: `0x57c60`
- end: `0x57fe6`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::RetrieveSyncState`
- size: `902`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x57ab0`

## callees

- `0x7d00`
- `0x417a0`
- `0x42280`
- `0x4d8c0`
- `0x4da80`
- `0x50ea0`
- `0x53440`
- `0x53450`
- `0x53490`
- `0x57c60`
- `0x57ff0`
- `0x58630`
- `0x58b30`

## string_xrefs

- `0x57ca1`: `exchangesyncstatexml`
- `0x57e18`: `ExchangeSyncStateService.RetrieveSyncState()`
- `0x57e43`: `ExchangeSyncStateService.RetrieveSyncState()`
- `0x57e74`: `ExchangeSyncStateService.RetrieveSyncState()`
- `0x57ea5`: `ExchangeSyncStateService.RetrieveSyncState()`
- `0x57ef7`: `ExchangeSyncStateService.RetrieveSyncState()`
- `0x57eea`: `{0}: ExchangeSyncUtility.HasMailboxPrivilege(userId {1}, orgId {2}, privilegeType {3}) returned false`

## pseudocode

```c

```

## disassembly

```asm
0x57c60  ldc.i4.0
0x57c61  ldarg.0
0x57c62  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57c67  ldstr    aRetrievemultip// "RetrieveMultiple"
0x57c6c  ldstr    aMailbox_0// "Mailbox"
0x57c71  ldstr    aRetrievesyncst// "RetrieveSyncState"
0x57c76  ldstr    asc_8A7C2// ""
0x57c7b  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x57c80  ldstr    aMailbox// "mailbox"
0x57c85  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x57c8a  stloc.0
0x57c8b  ldloc.0
0x57c8c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x57c91  ldc.i4.3
0x57c92  newarr   [mscorlib]System.String
0x57c97  dup
0x57c98  ldc.i4.0
0x57c99  ldstr    aMailboxid// "mailboxid"
0x57c9e  stelem.ref
0x57c9f  dup
0x57ca0  ldc.i4.1
0x57ca1  ldstr    aExchangesyncst// "exchangesyncstatexml"
0x57ca6  stelem.ref
0x57ca7  dup
0x57ca8  ldc.i4.2
0x57ca9  ldstr    aEmailaddress// "emailaddress"
0x57cae  stelem.ref
0x57caf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x57cb4  ldarg.0
0x57cb5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57cba  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x57cbf  dup
0x57cc0  brtrue.s loc_57CC6
0x57cc2  pop
0x57cc3  ldnull
0x57cc4  br.s     loc_57CCB
0x57cc6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x57ccb  brfalse.s loc_57CE6
0x57ccd  ldloc.0
0x57cce  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x57cd3  ldc.i4.1
0x57cd4  newarr   [mscorlib]System.String
0x57cd9  dup
0x57cda  ldc.i4.0
0x57cdb  ldstr    aOrgmarkedaspri// "orgmarkedasprimaryforexchangesync"
0x57ce0  stelem.ref
0x57ce1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x57ce6  ldloc.0
0x57ce7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x57cec  ldstr    aMailboxid// "mailboxid"
0x57cf1  ldc.i4.0
0x57cf2  ldc.i4.1
0x57cf3  newarr   [mscorlib]System.Object
0x57cf8  dup
0x57cf9  ldc.i4.0
0x57cfa  ldarg.0
0x57cfb  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailboxId
0x57d00  stelem.ref
0x57d01  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x57d06  ldarg.0
0x57d07  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_crmService
0x57d0c  ldloc.0
0x57d0d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x57d12  stloc.1
0x57d13  ldloc.1
0x57d14  brtrue.s loc_57D19
0x57d16  ldnull
0x57d17  br.s     loc_57D1F
0x57d19  ldloc.1
0x57d1a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57d1f  brfalse.s loc_57D41
0x57d21  ldloc.1
0x57d22  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57d27  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x57d2c  ldc.i4.1
0x57d2d  bne.un.s loc_57D41
0x57d2f  ldloc.1
0x57d30  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57d35  ldc.i4.0
0x57d36  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x57d3b  stloc.2
0x57d3c  leave    loc_57FE4
0x57d41  ldnull
0x57d42  stloc.3
0x57d43  ldnull
0x57d44  stloc.s  4
0x57d46  ldarg.0
0x57d47  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57d4c  dup
0x57d4d  brtrue.s loc_57D5C
0x57d4f  pop
0x57d50  ldloca.s 8
0x57d52  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x57d58  ldloc.s  8
0x57d5a  br.s     loc_57D90
0x57d5c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x57d61  dup
0x57d62  brtrue.s loc_57D71
0x57d64  pop
0x57d65  ldloca.s 8
0x57d67  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x57d6d  ldloc.s  8
0x57d6f  br.s     loc_57D90
0x57d71  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x57d76  dup
0x57d77  brtrue.s loc_57D86
0x57d79  pop
0x57d7a  ldloca.s 8
0x57d7c  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x57d82  ldloc.s  8
0x57d84  br.s     loc_57D90
0x57d86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x57d8b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x57d90  stloc.s  7
0x57d92  ldloca.s 7
0x57d94  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x57d99  brtrue.s loc_57DA2
0x57d9b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x57da0  br.s     loc_57DA9
0x57da2  ldloca.s 7
0x57da4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x57da9  stloc.s  5
0x57dab  ldarg.0
0x57dac  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57db1  dup
0x57db2  brtrue.s loc_57DC1
0x57db4  pop
0x57db5  ldloca.s 8
0x57db7  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x57dbd  ldloc.s  8
0x57dbf  br.s     loc_57DF5
0x57dc1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x57dc6  dup
0x57dc7  brtrue.s loc_57DD6
0x57dc9  pop
0x57dca  ldloca.s 8
0x57dcc  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x57dd2  ldloc.s  8
0x57dd4  br.s     loc_57DF5
0x57dd6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x57ddb  dup
0x57ddc  brtrue.s loc_57DEB
0x57dde  pop
0x57ddf  ldloca.s 8
0x57de1  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x57de7  ldloc.s  8
0x57de9  br.s     loc_57DF5
0x57deb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x57df0  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x57df5  stloc.s  7
0x57df7  ldloca.s 7
0x57df9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x57dfe  brtrue.s loc_57E07
0x57e00  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x57e05  br.s     loc_57E0E
0x57e07  ldloca.s 7
0x57e09  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x57e0e  stloc.s  6
0x57e10  ldloc.1
0x57e11  brtrue.s loc_57E36
0x57e13  ldstr    a0UnexpectedlyN// "{0}: unexpectedly null entityCollection"
0x57e18  ldstr    aExchangesyncst_0// "ExchangeSyncStateService.RetrieveSyncSt"...
0x57e1d  call     string [mscorlib]System.String::Format(string, object)
0x57e22  stloc.3
0x57e23  ldloc.s  6
0x57e25  ldloc.s  5
0x57e27  ldc.i4.s 0x68
0x57e29  ldloc.3
0x57e2a  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::GetMailboxErrorInfo(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, int32 traceCode, string message)
0x57e2f  stloc.s  4
0x57e31  br       loc_57F2E
0x57e36  ldloc.1
0x57e37  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57e3c  brtrue.s loc_57E61
0x57e3e  ldstr    a0UnexpectedlyN_0// "{0}: unexpectedly null entityCollection"...
0x57e43  ldstr    aExchangesyncst_0// "ExchangeSyncStateService.RetrieveSyncSt"...
0x57e48  call     string [mscorlib]System.String::Format(string, object)
0x57e4d  stloc.3
0x57e4e  ldloc.s  6
0x57e50  ldloc.s  5
0x57e52  ldc.i4.s 0x68
0x57e54  ldloc.3
0x57e55  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::GetMailboxErrorInfo(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, int32 traceCode, string message)
0x57e5a  stloc.s  4
0x57e5c  br       loc_57F2E
0x57e61  ldloc.1
0x57e62  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57e67  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x57e6c  ldc.i4.0
0x57e6d  bgt.s    loc_57E92
0x57e6f  ldstr    a0UnexpectedlyE// "{0}: unexpectedly empty entityCollectio"...
0x57e74  ldstr    aExchangesyncst_0// "ExchangeSyncStateService.RetrieveSyncSt"...
0x57e79  call     string [mscorlib]System.String::Format(string, object)
0x57e7e  stloc.3
0x57e7f  ldloc.s  6
0x57e81  ldloc.s  5
0x57e83  ldc.i4.s 0x68
0x57e85  ldloc.3
0x57e86  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::GetMailboxErrorInfo(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, int32 traceCode, string message)
0x57e8b  stloc.s  4
0x57e8d  br       loc_57F2E
0x57e92  ldloc.1
0x57e93  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57e98  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x57e9d  ldc.i4.1
0x57e9e  ble.s    loc_57ED0
0x57ea0  ldstr    a0UnexpectedEnt// "{0}: unexpected entityCollection.Entiti"...
0x57ea5  ldstr    aExchangesyncst_0// "ExchangeSyncStateService.RetrieveSyncSt"...
0x57eaa  ldloc.1
0x57eab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x57eb0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x57eb5  box      [mscorlib]System.Int32
0x57eba  call     string [mscorlib]System.String::Format(string, object, object)
0x57ebf  stloc.3
0x57ec0  ldloc.s  6
0x57ec2  ldloc.s  5
0x57ec4  ldc.i4.s 0x68
0x57ec6  ldloc.3
0x57ec7  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::GetMailboxErrorInfo(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, int32 traceCode, string message)
0x57ecc  stloc.s  4
0x57ece  br.s     loc_57F2E
0x57ed0  ldloc.s  5
0x57ed2  ldloc.s  6
0x57ed4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x57ed9  ldc.i4.1
0x57eda  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x57edf  dup
0x57ee0  ldc.i4.0
0x57ee1  ldc.i4.1
0x57ee2  stelem.i4
0x57ee3  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::HasMailboxPrivilege(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType[] privilegeTypes)
0x57ee8  brtrue.s loc_57F2E
0x57eea  ldstr    a0Exchangesyncu// "{0}: ExchangeSyncUtility.HasMailboxPriv"...
0x57eef  ldc.i4.4
0x57ef0  newarr   [mscorlib]System.Object
0x57ef5  dup
0x57ef6  ldc.i4.0
0x57ef7  ldstr    aExchangesyncst_0// "ExchangeSyncStateService.RetrieveSyncSt"...
0x57efc  stelem.ref
0x57efd  dup
0x57efe  ldc.i4.1
0x57eff  ldloc.s  5
0x57f01  box      [mscorlib]System.Guid
0x57f06  stelem.ref
0x57f07  dup
0x57f08  ldc.i4.2
0x57f09  ldloc.s  6
0x57f0b  box      [mscorlib]System.Guid
0x57f10  stelem.ref
0x57f11  dup
0x57f12  ldc.i4.3
0x57f13  ldc.i4.1
0x57f14  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x57f19  stelem.ref
0x57f1a  call     string [mscorlib]System.String::Format(string, object[])
0x57f1f  stloc.3
0x57f20  ldloc.s  6
0x57f22  ldloc.s  5
0x57f24  ldc.i4.s 0x71
0x57f26  ldloc.3
0x57f27  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::GetMailboxErrorInfo(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, int32 traceCode, string message)
0x57f2c  stloc.s  4
0x57f2e  ldloc.s  6
0x57f30  ldarg.0
0x57f31  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x57f36  ldarg.0
0x57f37  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57f3c  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x57f41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x57f46  ldc.i4.s 0x3C
0x57f48  ldc.i4.1
0x57f49  ldstr    aUserid0Message// "userId: {0}, message: {1}"
0x57f4e  ldloc.s  5
0x57f50  box      [mscorlib]System.Guid
0x57f55  ldloc.3
0x57f56  call     string [mscorlib]System.String::Format(string, object, object)
0x57f5b  ldc.i4.1
0x57f5c  newarr   [mscorlib]System.Object
0x57f61  dup
0x57f62  ldc.i4.0
0x57f63  ldarg.0
0x57f64  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailboxId
0x57f69  stelem.ref
0x57f6a  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x57f6f  ldloc.3
0x57f70  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x57f75  dup
0x57f76  ldloc.s  4
0x57f78  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x57f7d  throw
0x57f7e  stloc.s  9
0x57f80  ldstr    aFailedToRetrie_0// "Failed to retrieve the sync state : "
0x57f85  ldloc.s  9
0x57f87  ldarg.0
0x57f88  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57f8d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x57f92  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x57f97  call     string [mscorlib]System.String::Concat(string, string)
0x57f9c  ldloc.s  9
0x57f9e  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message, class [mscorlib]System.Exception innerException)
  ... truncated ...
```
