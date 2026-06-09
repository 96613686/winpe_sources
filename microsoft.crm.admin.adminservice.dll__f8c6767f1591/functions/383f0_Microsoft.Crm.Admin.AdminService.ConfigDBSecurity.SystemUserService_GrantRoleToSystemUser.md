# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GrantRoleToSystemUser

- ea: `0x383f0`
- end: `0x384f6`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GrantRoleToSystemUser`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18790`
- `0x367b0`
- `0x367c0`
- `0x37180`
- `0x37200`
- `0x37330`
- `0x37350`
- `0x37370`
- `0x37390`
- `0x373b0`
- `0x373d0`
- `0x373f0`
- `0x37760`
- `0x381e0`
- `0x383f0`

## string_xrefs

- `0x38474`: `SecurityRoleId`
- `0x384a6`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x384d6`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x383f0  ldarg.1
0x383f1  ldstr    aSystemusername// "systemUserName"
0x383f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x383fb  ldarg.0
0x383fc  ldarg.1
0x383fd  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GetCaseSafeName(string name)
0x38402  stloc.0
0x38403  ldarg.2
0x38404  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x38409  ldarg.0
0x3840a  ldloc.0
0x3840b  call     instance class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::Retrieve(string systemUserName)
0x38410  stloc.1
0x38411  newobj   instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::.ctor()
0x38416  ldarga.s 2
0x38418  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x3841e  callvirt instance string [mscorlib]System.Object::ToString()
0x38423  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::GetIdFromName(string roleName)
0x38428  stloc.2
0x38429  newobj   instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::.ctor()
0x3842e  stloc.3
0x3842f  ldloc.3
0x38430  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x38435  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::set_Id(valuetype [mscorlib]System.Guid value)
0x3843a  ldloc.3
0x3843b  ldloc.2
0x3843c  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::set_SecurityRoleId(valuetype [mscorlib]System.Guid value)
0x38441  ldloc.3
0x38442  ldloc.1
0x38443  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_Id()
0x38448  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::set_SystemUserId(valuetype [mscorlib]System.Guid value)
0x3844d  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x38452  stloc.s  4
0x38454  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x38459  stloc.s  5
0x3845b  ldloc.s  5
0x3845d  ldstr    aSystemuserid// "SystemUserId"
0x38462  ldloc.3
0x38463  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::get_SystemUserId()
0x38468  box      [mscorlib]System.Guid
0x3846d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x38472  ldloc.s  5
0x38474  ldstr    aSecurityroleid// "SecurityRoleId"
0x38479  ldloc.3
0x3847a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::get_SecurityRoleId()
0x3847f  box      [mscorlib]System.Guid
0x38484  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x38489  ldloc.s  4
0x3848b  ldstr    aSystemuserrole// "SystemUserRoles"
0x38490  ldnull
0x38491  ldc.i4.1
0x38492  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x38497  dup
0x38498  ldc.i4.0
0x38499  ldloc.s  5
0x3849b  stelem.ref
0x3849c  ldc.i4   0x2CF
0x384a1  ldstr    aGrantroletosys// "GrantRoleToSystemUser"
0x384a6  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x384ab  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x384b0  stloc.s  6
0x384b2  ldloc.s  6
0x384b4  brfalse.s loc_384BF
0x384b6  ldloc.s  6
0x384b8  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x384bd  brtrue.s loc_384E1
0x384bf  ldloc.s  4
0x384c1  ldstr    aSystemuserrole// "SystemUserRoles"
0x384c6  ldloc.3
0x384c7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x384cc  ldc.i4   0x2D3
0x384d1  ldstr    aGrantroletosys// "GrantRoleToSystemUser"
0x384d6  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x384db  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x384e0  pop
0x384e1  leave.s  loc_384EF
0x384e3  ldloc.s  4
0x384e5  brfalse.s loc_384EE
0x384e7  ldloc.s  4
0x384e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x384ee  endfinally
0x384ef  ldloc.3
0x384f0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserSecurityRolesData::get_Id()
0x384f5  ret
```
