# Microsoft.Crm.Security.User::GetPrivilegeInternal

- ea: `0xeec0`
- end: `0xefe8`
- name: `Microsoft.Crm.Security.User::GetPrivilegeInternal`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xa2910`

## callees

- `0xec90`
- `0xee20`
- `0xeec0`
- `0x2fb90`
- `0x2fbc0`

## string_xrefs

- `0xefc2`: `Invalid privilegeId: `
- `0xefd2`: `privilegeId`

## pseudocode

```c

```

## disassembly

```asm
0xeec0  ldarg.2
0xeec1  stloc.0
0xeec2  ldloc.0
0xeec3  brtrue.s loc_EEDA
0xeec5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0xeeca  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xeecf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xeed4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0xeed9  stloc.0
0xeeda  ldnull
0xeedb  stloc.1
0xeedc  ldarg.0
0xeedd  ldc.i4   0x3E9
0xeee2  beq.s    loc_EF22
0xeee4  ldarg.0
0xeee5  ldc.i4   0x232A
0xeeea  sub
0xeeeb  switch   loc_EF02, loc_EF0A, loc_EF12, loc_EF1A
0xef00  br.s     loc_EF3F
0xef02  ldstr    aLicense// "license"
0xef07  stloc.1
0xef08  br.s     loc_EF51
0xef0a  ldstr    aSystemuser// "systemuser"
0xef0f  stloc.1
0xef10  br.s     loc_EF51
0xef12  ldstr    aUserquery// "userquery"
0xef17  stloc.1
0xef18  br.s     loc_EF51
0xef1a  ldstr    aAsyncoperation// "asyncoperation"
0xef1f  stloc.1
0xef20  br.s     loc_EF51
0xef22  ldc.i4   0x106A
0xef27  ldarg.1
0xef28  ldarg.2
0xef29  call     bool Microsoft.Crm.Security.User::GetPrivilege(int32 objectType, valuetype Microsoft.Crm.Application.Types.PrivilegeId privilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xef2e  brtrue.s loc_EF3D
0xef30  ldc.i4   0x7DA
0xef35  ldarg.1
0xef36  ldarg.2
0xef37  call     bool Microsoft.Crm.Security.User::GetPrivilege(int32 objectType, valuetype Microsoft.Crm.Application.Types.PrivilegeId privilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xef3c  ret
0xef3d  ldc.i4.1
0xef3e  ret
0xef3f  ldloc.0
0xef40  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xef45  ldarg.0
0xef46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xef4b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xef50  stloc.1
0xef51  ldarg.1
0xef52  ldc.i4.s 0x20
0xef54  bgt.un.s loc_EF7A
0xef56  ldarg.1
0xef57  ldc.i4.1
0xef58  sub
0xef59  switch   loc_EFB2, loc_EFBE, loc_EFC2, loc_EF94
0xef6e  ldarg.1
0xef6f  ldc.i4.s 0x10
0xef71  beq.s    loc_EF98
0xef73  ldarg.1
0xef74  ldc.i4.s 0x20
0xef76  beq.s    loc_EFA5
0xef78  br.s     loc_EFC2
0xef7a  ldarg.1
0xef7b  ldc.i4   0x10000
0xef80  beq.s    loc_EFAA
0xef82  ldarg.1
0xef83  ldc.i4   0x40000
0xef88  beq.s    loc_EFB6
0xef8a  ldarg.1
0xef8b  ldc.i4   0x80000
0xef90  beq.s    loc_EF9D
0xef92  br.s     loc_EFC2
0xef94  ldc.i4.4
0xef95  stloc.2
0xef96  br.s     loc_EFDD
0xef98  ldc.i4.s 0x10
0xef9a  stloc.2
0xef9b  br.s     loc_EFDD
0xef9d  ldc.i4   0x80000
0xefa2  stloc.2
0xefa3  br.s     loc_EFDD
0xefa5  ldc.i4.s 0x20
0xefa7  stloc.2
0xefa8  br.s     loc_EFDD
0xefaa  ldc.i4   0x10000
0xefaf  stloc.2
0xefb0  br.s     loc_EFDD
0xefb2  ldc.i4.1
0xefb3  stloc.2
0xefb4  br.s     loc_EFDD
0xefb6  ldc.i4   0x40000
0xefbb  stloc.2
0xefbc  br.s     loc_EFDD
0xefbe  ldc.i4.2
0xefbf  stloc.2
0xefc0  br.s     loc_EFDD
0xefc2  ldstr    aInvalidPrivile_0// "Invalid privilegeId: "
0xefc7  ldarg.1
0xefc8  box      Microsoft.Crm.Application.Types.PrivilegeId
0xefcd  call     string [mscorlib]System.String::Concat(object, object)
0xefd2  ldstr    aPrivilegeid// "privilegeId"
0xefd7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xefdc  throw
0xefdd  ldloc.1
0xefde  ldloc.2
0xefdf  ldc.i4.0
0xefe0  ldc.i4.1
0xefe1  ldloc.0
0xefe2  call     bool Microsoft.Crm.Security.User::HasPrivilege(string entityName, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth privilegeDepth, bool filterOfflinePrivileges, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xefe7  ret
```
