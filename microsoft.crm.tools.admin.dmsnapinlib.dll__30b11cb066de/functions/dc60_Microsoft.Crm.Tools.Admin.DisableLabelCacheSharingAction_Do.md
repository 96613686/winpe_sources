# Microsoft.Crm.Tools.Admin.DisableLabelCacheSharingAction::Do

- ea: `0xdc60`
- end: `0xdd2b`
- name: `Microsoft.Crm.Tools.Admin.DisableLabelCacheSharingAction::Do`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0x9120`
- `0xdc60`

## string_xrefs

- `0xdcd2`: `LabelCacheSharingEnabled`

## pseudocode

```c

```

## disassembly

```asm
0xdc60  ldarg.1
0xdc61  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xdc66  stloc.0
0xdc67  ldloc.0
0xdc68  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xdc6d  stloc.1
0xdc6e  ldloc.1
0xdc6f  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xdc74  ldc.i4.0
0xdc75  ldc.i4.0
0xdc76  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xdc7b  stloc.2
0xdc7c  ldloc.2
0xdc7d  ldloc.1
0xdc7e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0xdc83  stloc.3
0xdc84  ldloc.3
0xdc85  ldc.i4.1
0xdc86  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool)
0xdc8b  ldloc.3
0xdc8c  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService::DoesLabelCacheSharingColumnExist(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0xdc91  brfalse.s loc_DD05
0xdc93  ldarg.0
0xdc94  ldfld    bool Microsoft.Crm.Tools.Admin.DisableLabelCacheSharingAction::_isCreate
0xdc99  brtrue.s loc_DCAE
0xdc9b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xdca0  ldloc.1
0xdca1  ldloc.3
0xdca2  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xdca7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0xdcac  br.s     loc_DCB4
0xdcae  ldloc.0
0xdcaf  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0xdcb4  stloc.s  4
0xdcb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xdcbb  stloc.s  5
0xdcbd  ldloc.s  5
0xdcbf  ldstr    aLanguageid_0// "LanguageId"
0xdcc4  ldloc.s  4
0xdcc6  box      [mscorlib]System.Int32
0xdccb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xdcd0  ldloc.s  5
0xdcd2  ldstr    aLabelcacheshar// "LabelCacheSharingEnabled"
0xdcd7  ldc.i4.0
0xdcd8  box      [mscorlib]System.Boolean
0xdcdd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xdce2  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService::.ctor()
0xdce7  ldloc.s  5
0xdce9  ldloc.3
0xdcea  ldc.i4.0
0xdceb  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService::Update(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, bool)
0xdcf0  ldarg.0
0xdcf1  ldfld    bool Microsoft.Crm.Tools.Admin.DisableLabelCacheSharingAction::_isCreate
0xdcf6  brtrue.s loc_DD05
0xdcf8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Instance()
0xdcfd  ldloc.3
0xdcfe  ldc.i4.1
0xdcff  ldc.i4.0
0xdd00  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, bool, bool)
0xdd05  ldloc.3
0xdd06  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0xdd0b  leave.s  loc_DD2A
0xdd0d  pop
0xdd0e  ldloc.3
0xdd0f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0xdd14  rethrow
0xdd16  ldloc.3
0xdd17  brfalse.s loc_DD1F
0xdd19  ldloc.3
0xdd1a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd1f  endfinally
0xdd20  ldloc.2
0xdd21  brfalse.s loc_DD29
0xdd23  ldloc.2
0xdd24  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd29  endfinally
0xdd2a  ret
```
