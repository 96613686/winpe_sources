# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::AddPrivilegeToRole

- ea: `0x36cb0`
- end: `0x36e72`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::AddPrivilegeToRole`
- size: `450`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x36cb0`
- `0x37180`

## string_xrefs

- `0x36dde`: `PrivilegeId`
- `0x36cdb`: `SecurityRole`
- `0x36df1`: `SecurityRoleId`
- `0x36cf9`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36d5c`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36dca`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36e26`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36e5a`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36cf4`: `AddPrivilegeToRole`
- `0x36d57`: `AddPrivilegeToRole`
- `0x36dc5`: `AddPrivilegeToRole`
- `0x36e21`: `AddPrivilegeToRole`
- `0x36e55`: `AddPrivilegeToRole`
- `0x36d3e`: `Privilege`
- `0x36db9`: `Privilege`
- `0x36e07`: `SecurityRolePrivileges`
- `0x36e49`: `SecurityRolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x36cb0  ldarg.1
0x36cb1  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x36cb6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36cbb  stloc.0
0x36cbc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36cc1  stloc.1
0x36cc2  ldloc.1
0x36cc3  ldstr    aName// "Name"
0x36cc8  ldarga.s 1
0x36cca  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36cd0  callvirt instance string [mscorlib]System.Object::ToString()
0x36cd5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36cda  ldloc.0
0x36cdb  ldstr    aSecurityrole// "SecurityRole"
0x36ce0  ldc.i4.1
0x36ce1  newarr   [mscorlib]System.String
0x36ce6  dup
0x36ce7  ldc.i4.0
0x36ce8  ldstr    aId// "Id"
0x36ced  stelem.ref
0x36cee  ldloc.1
0x36cef  ldc.i4   0x12B
0x36cf4  ldstr    aAddprivilegeto// "AddPrivilegeToRole"
0x36cf9  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36cfe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36d03  stloc.2
0x36d04  ldloc.2
0x36d05  brtrue.s loc_36D2B
0x36d07  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36d0c  ldstr    a0RoleWasnTFoun// "{0} role wasn't found"
0x36d11  ldc.i4.1
0x36d12  newarr   [mscorlib]System.Object
0x36d17  dup
0x36d18  ldc.i4.0
0x36d19  ldarg.1
0x36d1a  box      Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36d1f  stelem.ref
0x36d20  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36d25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x36d2a  throw
0x36d2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36d30  stloc.3
0x36d31  ldloc.3
0x36d32  ldstr    aName// "Name"
0x36d37  ldarg.2
0x36d38  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36d3d  ldloc.0
0x36d3e  ldstr    aPrivilege// "Privilege"
0x36d43  ldc.i4.1
0x36d44  newarr   [mscorlib]System.String
0x36d49  dup
0x36d4a  ldc.i4.0
0x36d4b  ldstr    aId// "Id"
0x36d50  stelem.ref
0x36d51  ldloc.3
0x36d52  ldc.i4   0x134
0x36d57  ldstr    aAddprivilegeto// "AddPrivilegeToRole"
0x36d5c  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36d61  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36d66  stloc.s  4
0x36d68  ldloc.s  4
0x36d6a  brfalse.s loc_36D7F
0x36d6c  ldloc.s  4
0x36d6e  ldstr    aId// "Id"
0x36d73  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x36d78  unbox.any [mscorlib]System.Guid
0x36d7d  br.s     loc_36D84
0x36d7f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36d84  stloc.s  5
0x36d86  ldloc.s  4
0x36d88  brtrue.s loc_36DD5
0x36d8a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x36d8f  stloc.s  5
0x36d91  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36d96  stloc.s  7
0x36d98  ldloc.s  7
0x36d9a  ldstr    aId// "Id"
0x36d9f  ldloc.s  5
0x36da1  box      [mscorlib]System.Guid
0x36da6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36dab  ldloc.s  7
0x36dad  ldstr    aName// "Name"
0x36db2  ldarg.2
0x36db3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36db8  ldloc.0
0x36db9  ldstr    aPrivilege// "Privilege"
0x36dbe  ldloc.s  7
0x36dc0  ldc.i4   0x142
0x36dc5  ldstr    aAddprivilegeto// "AddPrivilegeToRole"
0x36dca  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36dcf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36dd4  pop
0x36dd5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36dda  stloc.s  6
0x36ddc  ldloc.s  6
0x36dde  ldstr    aPrivilegeid// "PrivilegeId"
0x36de3  ldloc.s  5
0x36de5  box      [mscorlib]System.Guid
0x36dea  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36def  ldloc.s  6
0x36df1  ldstr    aSecurityroleid// "SecurityRoleId"
0x36df6  ldloc.2
0x36df7  ldstr    aId// "Id"
0x36dfc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x36e01  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36e06  ldloc.0
0x36e07  ldstr    aSecurityrolepr// "SecurityRolePrivileges"
0x36e0c  ldc.i4.1
0x36e0d  newarr   [mscorlib]System.String
0x36e12  dup
0x36e13  ldc.i4.0
0x36e14  ldstr    aId// "Id"
0x36e19  stelem.ref
0x36e1a  ldloc.s  6
0x36e1c  ldc.i4   0x149
0x36e21  ldstr    aAddprivilegeto// "AddPrivilegeToRole"
0x36e26  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36e2b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36e30  brtrue.s loc_36E65
0x36e32  ldloc.s  6
0x36e34  ldstr    aId// "Id"
0x36e39  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x36e3e  box      [mscorlib]System.Guid
0x36e43  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36e48  ldloc.0
0x36e49  ldstr    aSecurityrolepr// "SecurityRolePrivileges"
0x36e4e  ldloc.s  6
0x36e50  ldc.i4   0x14C
0x36e55  ldstr    aAddprivilegeto// "AddPrivilegeToRole"
0x36e5a  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36e5f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36e64  pop
0x36e65  leave.s  loc_36E71
0x36e67  ldloc.0
0x36e68  brfalse.s loc_36E70
0x36e6a  ldloc.0
0x36e6b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36e70  endfinally
0x36e71  ret
```
