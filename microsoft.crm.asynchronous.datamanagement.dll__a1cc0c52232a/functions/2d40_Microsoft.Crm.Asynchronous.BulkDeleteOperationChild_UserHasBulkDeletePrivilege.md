# Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::UserHasBulkDeletePrivilege

- ea: `0x2d40`
- end: `0x2dd1`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::UserHasBulkDeletePrivilege`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x2c50`

## callees

- `0x2d40`

## string_xrefs

- `0x2da2`: `prvBulkDelete`

## pseudocode

```c

```

## disassembly

```asm
0x2d40  ldarg.1
0x2d41  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x2d46  ldarg.2
0x2d47  ldarg.2
0x2d48  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2d4d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x2d52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SystemUserId()
0x2d57  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2d5c  brfalse.s loc_2D60
0x2d5e  ldc.i4.1
0x2d5f  ret
0x2d60  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesRequest::.ctor()
0x2d65  stloc.0
0x2d66  ldloc.0
0x2d67  ldarg.1
0x2d68  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesRequest::set_UserId(valuetype [mscorlib]System.Guid)
0x2d6d  ldarg.0
0x2d6e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_crmService
0x2d73  ldloc.0
0x2d74  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2d79  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesResponse
0x2d7e  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege[] [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveUserPrivilegesResponse::get_RolePrivileges()
0x2d83  stloc.1
0x2d84  ldc.i4.0
0x2d85  stloc.2
0x2d86  br.s     loc_2DC9
0x2d88  ldloc.1
0x2d89  ldloc.2
0x2d8a  ldelem.ref
0x2d8b  stloc.3
0x2d8c  ldloc.3
0x2d8d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege::get_PrivilegeId()
0x2d92  ldarg.0
0x2d93  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x2d98  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2d9d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2da2  ldstr    aPrvbulkdelete// "prvBulkDelete"
0x2da7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x2dac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x2db1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2db6  brfalse.s loc_2DC5
0x2db8  ldloc.3
0x2db9  callvirt instance valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PrivilegeDepth [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege::get_Depth()
0x2dbe  ldc.i4.3
0x2dbf  bne.un.s loc_2DC3
0x2dc1  ldc.i4.1
0x2dc2  ret
0x2dc3  ldc.i4.0
0x2dc4  ret
0x2dc5  ldloc.2
0x2dc6  ldc.i4.1
0x2dc7  add
0x2dc8  stloc.2
0x2dc9  ldloc.2
0x2dca  ldloc.1
0x2dcb  ldlen
0x2dcc  conv.i4
0x2dcd  blt.s    loc_2D88
0x2dcf  ldc.i4.0
0x2dd0  ret
```
