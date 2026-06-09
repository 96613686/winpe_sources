# Microsoft.Crm.BusinessEntities.SecurityLibrary::RetrievePrivilegeForUser

- ea: `0x62390`
- end: `0x625a6`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::RetrievePrivilegeForUser`
- size: `534`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x625b0`
- `0x8fe90`

## callees

- `0x51e40`
- `0x51eb0`
- `0x621a0`
- `0x62390`
- `0x636f0`
- `0x63b40`

## string_xrefs

- `0x623ef`: `Privilege does not exist for UserId: {0}, PrivilegeId: {1}. Returned index = {2}. Privileges total = {3}.`
- `0x62505`: `SecLib::RetrievePrivilegeForUser failed - no roles are assigned to user. Returned hr = {0}, User: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x62390  ldarg.0
0x62391  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x62396  ldarg.2
0x62397  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6239c  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::VerifyUserOrganization(valuetype [mscorlib]System.Guid userOrgId, valuetype [mscorlib]System.Guid contextOrgId)
0x623a1  ldc.i4.0
0x623a2  stloc.0
0x623a3  ldarg.0
0x623a4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x623a9  ldlen
0x623aa  brfalse  loc_6242F
0x623af  ldc.i4.1
0x623b0  stloc.0
0x623b1  ldarg.0
0x623b2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x623b7  ldarg.1
0x623b8  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::TryGetPrivilegeIndex(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] privileges, valuetype [mscorlib]System.Guid privilege)
0x623bd  stloc.1
0x623be  ldc.i4.0
0x623bf  ldloc.1
0x623c0  bgt.s    loc_623E8
0x623c2  call     class Microsoft.Crm.Platform.Server.SecurityLibraryEventSource Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::get_Instance()
0x623c7  ldarg.2
0x623c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x623cd  ldarg.0
0x623ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x623d3  ldarg.1
0x623d4  ldarg.0
0x623d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x623da  ldlen
0x623db  conv.i4
0x623dc  ldstr    a0_3// "0"
0x623e1  callvirt instance void Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::RequestedPrivilegeAccessInfo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid privilegeId, int32 privilegesLength, [opt] string indexReturned)
0x623e6  ldc.i4.0
0x623e7  ret
0x623e8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x623ed  ldc.i4.s 0x14
0x623ef  ldstr    aPrivilegeDoesN// "Privilege does not exist for UserId: {0"...
0x623f4  ldc.i4.4
0x623f5  newarr   [mscorlib]System.Object
0x623fa  dup
0x623fb  ldc.i4.0
0x623fc  ldarg.0
0x623fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x62402  box      [mscorlib]System.Guid
0x62407  stelem.ref
0x62408  dup
0x62409  ldc.i4.1
0x6240a  ldarg.1
0x6240b  box      [mscorlib]System.Guid
0x62410  stelem.ref
0x62411  dup
0x62412  ldc.i4.2
0x62413  ldloc.1
0x62414  box      [mscorlib]System.Int32
0x62419  stelem.ref
0x6241a  dup
0x6241b  ldc.i4.3
0x6241c  ldarg.0
0x6241d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62422  ldlen
0x62423  conv.i4
0x62424  box      [mscorlib]System.Int32
0x62429  stelem.ref
0x6242a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6242f  ldarg.0
0x62430  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x62435  ldc.i4.2
0x62436  bne.un.s loc_62485
0x62438  ldarg.2
0x62439  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6243e  ldarg.1
0x6243f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(valuetype [mscorlib]System.Guid)
0x62444  stloc.2
0x62445  ldarg.1
0x62446  ldloc.2
0x62447  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_AccessRight()
0x6244c  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::IsInvalidPrivilegeForReadOnlyUser(valuetype [mscorlib]System.Guid privilegeId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights)
0x62451  brfalse.s loc_62485
0x62453  call     class Microsoft.Crm.Platform.Server.SecurityLibraryEventSource Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::get_Instance()
0x62458  ldarg.2
0x62459  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6245e  ldarg.0
0x6245f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x62464  ldarg.1
0x62465  ldarg.0
0x62466  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x6246b  ldlen
0x6246c  conv.i4
0x6246d  ldc.i4   0x80040220
0x62472  stloc.3
0x62473  ldloca.s 3
0x62475  call     instance string [mscorlib]System.Int32::ToString()
0x6247a  callvirt instance void Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::RequestedPrivilegeAccessInfo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid privilegeId, int32 privilegesLength, [opt] string indexReturned)
0x6247f  ldc.i4   0x80040220
0x62484  ret
0x62485  ldarg.0
0x62486  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x6248b  ldc.i4.1
0x6248c  bne.un.s loc_624EC
0x6248e  ldarg.2
0x6248f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62494  ldarg.1
0x62495  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(valuetype [mscorlib]System.Guid)
0x6249a  stloc.s  4
0x6249c  ldc.i4.1
0x6249d  ldc.i4.1
0x6249e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmLicenseService::GetLicenseGuid(int32, bool)
0x624a3  ldloc.s  4
0x624a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x624aa  ldloc.s  4
0x624ac  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_ObjectTypeCode()
0x624b1  ldc.i4.1
0x624b2  ldc.i4.1
0x624b3  call     bool [Microsoft.Crm]Microsoft.Crm.CrmLicenseHelper::IsInvalidLicensePrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, int32, bool)
0x624b8  brfalse.s loc_624EC
0x624ba  call     class Microsoft.Crm.Platform.Server.SecurityLibraryEventSource Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::get_Instance()
0x624bf  ldarg.2
0x624c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x624c5  ldarg.0
0x624c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x624cb  ldarg.1
0x624cc  ldarg.0
0x624cd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x624d2  ldlen
0x624d3  conv.i4
0x624d4  ldc.i4   0x80040220
0x624d9  stloc.3
0x624da  ldloca.s 3
0x624dc  call     instance string [mscorlib]System.Int32::ToString()
0x624e1  callvirt instance void Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::RequestedPrivilegeAccessInfo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid privilegeId, int32 privilegesLength, [opt] string indexReturned)
0x624e6  ldc.i4   0x80040220
0x624eb  ret
0x624ec  ldarg.0
0x624ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_MaxDepthTeamPrivileges()
0x624f2  brfalse.s loc_624FD
0x624f4  ldarg.0
0x624f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_MaxDepthTeamPrivileges()
0x624fa  ldlen
0x624fb  brtrue.s loc_6253B
0x624fd  ldloc.0
0x624fe  brtrue.s loc_62574
0x62500  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62505  ldstr    aSeclibRetrieve// "SecLib::RetrievePrivilegeForUser failed"...
0x6250a  ldc.i4.2
0x6250b  newarr   [mscorlib]System.Object
0x62510  dup
0x62511  ldc.i4.0
0x62512  ldc.i4   0x80042F09
0x62517  box      [mscorlib]System.Int32
0x6251c  stelem.ref
0x6251d  dup
0x6251e  ldc.i4.1
0x6251f  ldarg.0
0x62520  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x62525  box      [mscorlib]System.Guid
0x6252a  stelem.ref
0x6252b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x62530  ldc.i4   0x80042F09
0x62535  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string, int32)
0x6253a  throw
0x6253b  ldarg.0
0x6253c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_MaxDepthTeamPrivileges()
0x62541  ldarg.1
0x62542  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::TryGetPrivilegeIndex(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] privileges, valuetype [mscorlib]System.Guid privilege)
0x62547  stloc.s  5
0x62549  ldc.i4.0
0x6254a  ldloc.s  5
0x6254c  bgt.s    loc_62574
0x6254e  call     class Microsoft.Crm.Platform.Server.SecurityLibraryEventSource Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::get_Instance()
0x62553  ldarg.2
0x62554  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x62559  ldarg.0
0x6255a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x6255f  ldarg.1
0x62560  ldarg.0
0x62561  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62566  ldlen
0x62567  conv.i4
0x62568  ldstr    a0_3// "0"
0x6256d  callvirt instance void Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::RequestedPrivilegeAccessInfo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid privilegeId, int32 privilegesLength, [opt] string indexReturned)
0x62572  ldc.i4.0
0x62573  ret
0x62574  call     class Microsoft.Crm.Platform.Server.SecurityLibraryEventSource Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::get_Instance()
0x62579  ldarg.2
0x6257a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6257f  ldarg.0
0x62580  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x62585  ldarg.1
0x62586  ldarg.0
0x62587  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x6258c  ldlen
0x6258d  conv.i4
0x6258e  ldc.i4   0x80040220
0x62593  stloc.3
0x62594  ldloca.s 3
0x62596  call     instance string [mscorlib]System.Int32::ToString()
0x6259b  callvirt instance void Microsoft.Crm.Platform.Server.SecurityLibraryEventSource::RequestedPrivilegeAccessInfo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid privilegeId, int32 privilegesLength, [opt] string indexReturned)
0x625a0  ldc.i4   0x80040220
0x625a5  ret
```
