# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::HasExchangeSyncIdMappingAccess

- ea: `0x586b0`
- end: `0x587ed`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::HasExchangeSyncIdMappingAccess`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x5a580`

## callees

- `0x7d00`
- `0x417a0`
- `0x42280`
- `0x4d8c0`
- `0x586b0`

## string_xrefs

- `0x58775`: `User {0} does not have write access to {1}.`
- `0x587b8`: `Unknown error occured while attempting to get write privcheck for User {0} to {1}`

## pseudocode

```c

```

## disassembly

```asm
0x586b0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x586b5  stloc.0
0x586b6  ldarg.2
0x586b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x586bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x586c1  stloc.1
0x586c2  ldarg.1
0x586c3  ldc.i4.8
0x586c4  beq.s    loc_586CD
0x586c6  ldarg.1
0x586c7  ldc.i4.s 9
0x586c9  beq.s    loc_586E8
0x586cb  br.s     loc_58703
0x586cd  ldarg.0
0x586ce  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::CreateSecurityPrincipalUser(valuetype [mscorlib]System.Guid)
0x586d3  stloc.2
0x586d4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x586d9  ldarg.0
0x586da  ldloc.1
0x586db  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x586e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x586e5  stloc.3
0x586e6  br.s     loc_58705
0x586e8  ldarg.0
0x586e9  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::CreateSecurityPrincipalTeam(valuetype [mscorlib]System.Guid)
0x586ee  stloc.2
0x586ef  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache::Instance()
0x586f4  ldarg.0
0x586f5  ldloc.1
0x586f6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ITeam>::LookupEntry(void, var<u1>)
0x586fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x58700  stloc.3
0x58701  br.s     loc_58705
0x58703  ldc.i4.1
0x58704  ret
0x58705  ldarg.0
0x58706  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::CreateSecurityPrincipalUser(valuetype [mscorlib]System.Guid)
0x5870b  stloc.s  4
0x5870d  ldloca.s 3
0x5870f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x58714  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x58719  brfalse.s loc_5871D
0x5871b  ldc.i4.0
0x5871c  ret
0x5871d  ldarg.2
0x5871e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x58723  ldc.i4.0
0x58724  ldc.i4.0
0x58725  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x5872a  stloc.s  5
0x5872c  ldloc.s  5
0x5872e  ldc.i4.0
0x5872f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x58734  ldloc.s  5
0x58736  ldloc.s  4
0x58738  ldloc.2
0x58739  ldloc.0
0x5873a  ldc.i4   0x1018
0x5873f  ldloc.3
0x58740  ldarg.3
0x58741  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx2(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0x58746  ldloc.s  5
0x58748  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x5874d  ldc.i4.1
0x5874e  stloc.s  6
0x58750  leave    loc_587EA
0x58755  pop
0x58756  ldarg.2
0x58757  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5875c  ldarg.2
0x5875d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x58762  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x58767  ldarg.2
0x58768  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x5876d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x58772  ldc.i4.s 0x3C
0x58774  ldc.i4.1
0x58775  ldstr    aUser0DoesNotHa// "User {0} does not have write access to "...
0x5877a  ldc.i4.2
0x5877b  newarr   [mscorlib]System.Object
0x58780  dup
0x58781  ldc.i4.0
0x58782  ldarg.0
0x58783  box      [mscorlib]System.Guid
0x58788  stelem.ref
0x58789  dup
0x5878a  ldc.i4.1
0x5878b  ldstr    aExchangesyncid_6// "ExchangeSyncIdMapping"
0x58790  stelem.ref
0x58791  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x58796  rethrow
0x58798  pop
0x58799  ldarg.2
0x5879a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5879f  ldarg.2
0x587a0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x587a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x587aa  ldarg.2
0x587ab  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x587b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x587b5  ldc.i4.s 0x3C
0x587b7  ldc.i4.1
0x587b8  ldstr    aUnknownErrorOc// "Unknown error occured while attempting "...
0x587bd  ldc.i4.2
0x587be  newarr   [mscorlib]System.Object
0x587c3  dup
0x587c4  ldc.i4.0
0x587c5  ldarg.0
0x587c6  box      [mscorlib]System.Guid
0x587cb  stelem.ref
0x587cc  dup
0x587cd  ldc.i4.1
0x587ce  ldstr    aExchangesyncid_6// "ExchangeSyncIdMapping"
0x587d3  stelem.ref
0x587d4  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x587d9  ldc.i4.1
0x587da  stloc.s  6
0x587dc  leave.s  loc_587EA
0x587de  ldloc.s  5
0x587e0  brfalse.s loc_587E9
0x587e2  ldloc.s  5
0x587e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x587e9  endfinally
0x587ea  ldloc.s  6
0x587ec  ret
```
