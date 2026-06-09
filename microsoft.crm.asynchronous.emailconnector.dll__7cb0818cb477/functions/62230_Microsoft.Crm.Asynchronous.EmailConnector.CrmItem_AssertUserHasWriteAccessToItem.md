# Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::AssertUserHasWriteAccessToItem

- ea: `0x62230`
- end: `0x624b7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::AssertUserHasWriteAccessToItem`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x5fc60`
- `0x61f30`

## callees

- `0x7d00`
- `0x42280`
- `0x4da80`
- `0x60cc0`
- `0x62180`
- `0x62230`
- `0x6ace0`
- `0x70120`
- `0x701d0`
- `0x70300`
- `0x70330`

## string_xrefs

- `0x623fd`: `User {0} does not have write access to {1} {2}. Exception: {3}.`
- `0x62452`: `Unknown error occured while attempting to get write privcheck for User {0} to {1} {2}. Exception: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x62230  ldarg.0
0x62231  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x62236  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem
0x6223b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_CrmIdPropertyName()
0x62240  stloc.0
0x62241  ldarg.0
0x62242  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x62247  ldloc.0
0x62248  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x6224d  stloc.1
0x6224e  ldloc.1
0x6224f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x62254  brtrue.s loc_6225E
0x62256  ldloc.1
0x62257  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6225c  br.s     loc_62263
0x6225e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62263  stloc.2
0x62264  ldarg.0
0x62265  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6226a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x6226f  brfalse.s loc_62283
0x62271  ldarg.0
0x62272  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x62277  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x6227c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x62281  brtrue.s loc_6228A
0x62283  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62288  br.s     loc_6229F
0x6228a  ldarg.0
0x6228b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x62290  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x62295  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x6229a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x6229f  stloc.3
0x622a0  ldarg.0
0x622a1  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::GetOwnerId()
0x622a6  ldloca.s 4
0x622a8  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x622ad  brfalse.s loc_622E3
0x622af  ldloca.s 2
0x622b1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x622b6  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x622bb  brtrue.s loc_622E3
0x622bd  ldloca.s 3
0x622bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x622c4  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x622c9  brtrue.s loc_622E3
0x622cb  ldloca.s 4
0x622cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x622d2  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x622d7  brtrue.s loc_622E3
0x622d9  ldloc.s  4
0x622db  ldloc.3
0x622dc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x622e1  brfalse.s loc_622E4
0x622e3  ret
0x622e4  ldarg.0
0x622e5  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x622ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x622ef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x622f4  stloc.s  5
0x622f6  ldarg.0
0x622f7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x622fc  ldstr    aOwneridtype// "owneridtype"
0x62301  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x62306  stloc.s  6
0x62308  ldloc.s  6
0x6230a  ldstr    a8// "8"
0x6230f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62314  brtrue.s loc_62326
0x62316  ldloc.s  6
0x62318  ldstr    a9// "9"
0x6231d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62322  brtrue.s loc_62355
0x62324  br.s     loc_62384
0x62326  ldloc.s  4
0x62328  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::CreateSecurityPrincipalUser(valuetype [mscorlib]System.Guid)
0x6232d  stloc.s  7
0x6232f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x62334  ldloc.s  4
0x62336  ldloc.s  5
0x62338  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x6233d  stloc.s  9
0x6233f  ldloc.s  9
0x62341  brtrue.s loc_6234A
0x62343  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62348  br.s     loc_62351
0x6234a  ldloc.s  9
0x6234c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x62351  stloc.s  8
0x62353  br.s     loc_623A5
0x62355  ldloc.s  4
0x62357  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::CreateSecurityPrincipalTeam(valuetype [mscorlib]System.Guid)
0x6235c  stloc.s  7
0x6235e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache::Instance()
0x62363  ldloc.s  4
0x62365  ldloc.s  5
0x62367  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ITeam>::LookupEntry(void, var<u1>)
0x6236c  stloc.s  0xA
0x6236e  ldloc.s  0xA
0x62370  brtrue.s loc_62379
0x62372  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62377  br.s     loc_62380
0x62379  ldloc.s  0xA
0x6237b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x62380  stloc.s  8
0x62382  br.s     loc_623A5
0x62384  ldarg.0
0x62385  ldc.i4.1
0x62386  ldstr    aUnexpectedOwne// "Unexpected OwnerIdType of {0} for Item "...
0x6238b  ldc.i4.2
0x6238c  newarr   [mscorlib]System.Object
0x62391  dup
0x62392  ldc.i4.0
0x62393  ldloc.s  6
0x62395  stelem.ref
0x62396  dup
0x62397  ldc.i4.1
0x62398  ldloc.2
0x62399  box      [mscorlib]System.Guid
0x6239e  stelem.ref
0x6239f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x623a4  ret
0x623a5  ldloca.s 8
0x623a7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x623ac  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x623b1  brfalse.s loc_623B4
0x623b3  ret
0x623b4  ldarg.0
0x623b5  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x623ba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x623bf  ldc.i4.0
0x623c0  ldc.i4.0
0x623c1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x623c6  stloc.s  0xB
0x623c8  ldloc.3
0x623c9  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::CreateSecurityPrincipalUser(valuetype [mscorlib]System.Guid)
0x623ce  stloc.s  0xC
0x623d0  ldloc.s  0xB
0x623d2  ldc.i4.0
0x623d3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x623d8  ldloc.s  0xB
0x623da  ldloc.s  0xC
0x623dc  ldloc.s  7
0x623de  ldloc.2
0x623df  ldarg.0
0x623e0  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x623e5  ldloc.s  8
0x623e7  ldc.i4.2
0x623e8  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx2(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0x623ed  ldloc.s  0xB
0x623ef  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x623f4  leave    loc_624B6
0x623f9  stloc.s  0xD
0x623fb  ldarg.0
0x623fc  ldc.i4.2
0x623fd  ldstr    aUser0DoesNotHa_0// "User {0} does not have write access to "...
0x62402  ldc.i4.4
0x62403  newarr   [mscorlib]System.Object
0x62408  dup
0x62409  ldc.i4.0
0x6240a  ldloc.3
0x6240b  box      [mscorlib]System.Guid
0x62410  stelem.ref
0x62411  dup
0x62412  ldc.i4.1
0x62413  ldarg.0
0x62414  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x62419  stloc.s  0xE
0x6241b  ldloca.s 0xE
0x6241d  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62423  callvirt instance string [mscorlib]System.Object::ToString()
0x62428  stelem.ref
0x62429  dup
0x6242a  ldc.i4.2
0x6242b  ldloc.2
0x6242c  box      [mscorlib]System.Guid
0x62431  stelem.ref
0x62432  dup
0x62433  ldc.i4.3
0x62434  ldloc.s  0xD
0x62436  ldarg.0
0x62437  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6243c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x62441  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x62446  stelem.ref
0x62447  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6244c  rethrow
0x6244e  stloc.s  0xF
0x62450  ldarg.0
0x62451  ldc.i4.1
0x62452  ldstr    aUnknownErrorOc_0// "Unknown error occured while attempting "...
0x62457  ldc.i4.4
0x62458  newarr   [mscorlib]System.Object
0x6245d  dup
0x6245e  ldc.i4.0
0x6245f  ldloc.3
0x62460  box      [mscorlib]System.Guid
0x62465  stelem.ref
0x62466  dup
0x62467  ldc.i4.1
0x62468  ldarg.0
0x62469  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x6246e  stloc.s  0xE
0x62470  ldloca.s 0xE
0x62472  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62478  callvirt instance string [mscorlib]System.Object::ToString()
0x6247d  stelem.ref
0x6247e  dup
0x6247f  ldc.i4.2
0x62480  ldloc.2
0x62481  box      [mscorlib]System.Guid
0x62486  stelem.ref
0x62487  dup
0x62488  ldc.i4.3
0x62489  ldloc.s  0xF
0x6248b  ldarg.0
0x6248c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x62491  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x62496  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6249b  stelem.ref
0x6249c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x624a1  ldloc.s  0xB
0x624a3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x624a8  rethrow
0x624aa  ldloc.s  0xB
0x624ac  brfalse.s loc_624B5
0x624ae  ldloc.s  0xB
0x624b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x624b5  endfinally
0x624b6  ret
```
