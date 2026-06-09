# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RevokeRoleFromSystemUser

- ea: `0x38280`
- end: `0x38322`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RevokeRoleFromSystemUser`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x367b0`
- `0x367c0`
- `0x37180`
- `0x37200`
- `0x37760`
- `0x381e0`
- `0x38280`

## string_xrefs

- `0x382c0`: `SecurityRoleId`
- `0x38308`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x38280  ldarg.1
0x38281  ldstr    aSystemusername// "systemUserName"
0x38286  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3828b  ldarg.0
0x3828c  ldarg.1
0x3828d  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GetCaseSafeName(string name)
0x38292  stloc.0
0x38293  ldarg.2
0x38294  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x38299  ldarg.0
0x3829a  ldloc.0
0x3829b  call     instance class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::Retrieve(string systemUserName)
0x382a0  stloc.1
0x382a1  newobj   instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::.ctor()
0x382a6  ldarga.s 2
0x382a8  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x382ae  callvirt instance string [mscorlib]System.Object::ToString()
0x382b3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::GetIdFromName(string roleName)
0x382b8  stloc.2
0x382b9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x382be  stloc.3
0x382bf  ldloc.3
0x382c0  ldstr    aSecurityroleid// "SecurityRoleId"
0x382c5  ldloc.2
0x382c6  box      [mscorlib]System.Guid
0x382cb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x382d0  ldloc.3
0x382d1  ldstr    aSystemuserid// "SystemUserId"
0x382d6  ldloc.1
0x382d7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_Id()
0x382dc  box      [mscorlib]System.Guid
0x382e1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x382e6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x382eb  stloc.s  4
0x382ed  ldloc.s  4
0x382ef  ldstr    aSystemuserrole// "SystemUserRoles"
0x382f4  ldc.i4.1
0x382f5  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x382fa  dup
0x382fb  ldc.i4.0
0x382fc  ldloc.3
0x382fd  stelem.ref
0x382fe  ldc.i4   0x294
0x38303  ldstr    aRevokerolefrom// "RevokeRoleFromSystemUser"
0x38308  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3830d  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x38312  pop
0x38313  leave.s  loc_38321
0x38315  ldloc.s  4
0x38317  brfalse.s loc_38320
0x38319  ldloc.s  4
0x3831b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38320  endfinally
0x38321  ret
```
