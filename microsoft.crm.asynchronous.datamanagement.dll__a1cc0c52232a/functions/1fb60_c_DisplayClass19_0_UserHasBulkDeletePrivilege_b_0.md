# <>c__DisplayClass19_0::<UserHasBulkDeletePrivilege>b__0

- ea: `0x1fb60`
- end: `0x1fc0f`
- name: `<>c__DisplayClass19_0::<UserHasBulkDeletePrivilege>b__0`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1fb60`

## string_xrefs

- `0x1fbe0`: `prvBulkDelete`

## pseudocode

```c

```

## disassembly

```asm
0x1fb60  ldarg.0
0x1fb61  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass19_0::userId
0x1fb66  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1fb6b  ldarg.0
0x1fb6c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass19_0::organizationId
0x1fb71  ldarg.0
0x1fb72  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass19_0::organizationId
0x1fb77  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1fb7c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1fb81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SystemUserId()
0x1fb86  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1fb8b  brfalse.s loc_1FB8F
0x1fb8d  ldc.i4.1
0x1fb8e  ret
0x1fb8f  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesRequest::.ctor()
0x1fb94  stloc.0
0x1fb95  ldloc.0
0x1fb96  ldarg.0
0x1fb97  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass19_0::userId
0x1fb9c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesRequest::set_UserId(valuetype [mscorlib]System.Guid)
0x1fba1  ldarg.0
0x1fba2  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass19_0::<>4__this
0x1fba7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x1fbac  ldloc.0
0x1fbad  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1fbb2  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesResponse
0x1fbb7  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege[] [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesResponse::get_RolePrivileges()
0x1fbbc  stloc.1
0x1fbbd  ldc.i4.0
0x1fbbe  stloc.2
0x1fbbf  br.s     loc_1FC07
0x1fbc1  ldloc.1
0x1fbc2  ldloc.2
0x1fbc3  ldelem.ref
0x1fbc4  stloc.3
0x1fbc5  ldloc.3
0x1fbc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege::get_PrivilegeId()
0x1fbcb  ldarg.0
0x1fbcc  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass19_0::<>4__this
0x1fbd1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1fbd6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1fbdb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fbe0  ldstr    aPrvbulkdelete// "prvBulkDelete"
0x1fbe5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x1fbea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x1fbef  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1fbf4  brfalse.s loc_1FC03
0x1fbf6  ldloc.3
0x1fbf7  callvirt instance valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PrivilegeDepth [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege::get_Depth()
0x1fbfc  ldc.i4.3
0x1fbfd  bne.un.s loc_1FC01
0x1fbff  ldc.i4.1
0x1fc00  ret
0x1fc01  ldc.i4.0
0x1fc02  ret
0x1fc03  ldloc.2
0x1fc04  ldc.i4.1
0x1fc05  add
0x1fc06  stloc.2
0x1fc07  ldloc.2
0x1fc08  ldloc.1
0x1fc09  ldlen
0x1fc0a  conv.i4
0x1fc0b  blt.s    loc_1FBC1
0x1fc0d  ldc.i4.0
0x1fc0e  ret
```
