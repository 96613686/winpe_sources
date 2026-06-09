# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RemovePrivilegeFromRole

- ea: `0x36e80`
- end: `0x36fc4`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RemovePrivilegeFromRole`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x36e80`
- `0x37180`

## string_xrefs

- `0x36f7b`: `PrivilegeId`
- `0x36eab`: `SecurityRole`
- `0x36f64`: `SecurityRoleId`
- `0x36ec9`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36f2c`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36fac`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36f0e`: `Privilege`
- `0x36f92`: `SecurityRolePrivileges`
- `0x36ec4`: `RemovePrivilegeFromRole`
- `0x36f27`: `RemovePrivilegeFromRole`
- `0x36fa7`: `RemovePrivilegeFromRole`
- `0x36f41`: `{0} privilege wasn't found`

## pseudocode

```c

```

## disassembly

```asm
0x36e80  ldarg.1
0x36e81  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x36e86  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36e8b  stloc.0
0x36e8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36e91  stloc.1
0x36e92  ldloc.1
0x36e93  ldstr    aName// "Name"
0x36e98  ldarga.s 1
0x36e9a  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36ea0  callvirt instance string [mscorlib]System.Object::ToString()
0x36ea5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36eaa  ldloc.0
0x36eab  ldstr    aSecurityrole// "SecurityRole"
0x36eb0  ldc.i4.1
0x36eb1  newarr   [mscorlib]System.String
0x36eb6  dup
0x36eb7  ldc.i4.0
0x36eb8  ldstr    aId// "Id"
0x36ebd  stelem.ref
0x36ebe  ldloc.1
0x36ebf  ldc.i4   0x15F
0x36ec4  ldstr    aRemoveprivileg// "RemovePrivilegeFromRole"
0x36ec9  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36ece  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36ed3  stloc.2
0x36ed4  ldloc.2
0x36ed5  brtrue.s loc_36EFB
0x36ed7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36edc  ldstr    a0RoleWasnTFoun// "{0} role wasn't found"
0x36ee1  ldc.i4.1
0x36ee2  newarr   [mscorlib]System.Object
0x36ee7  dup
0x36ee8  ldc.i4.0
0x36ee9  ldarg.1
0x36eea  box      Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36eef  stelem.ref
0x36ef0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36ef5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x36efa  throw
0x36efb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36f00  stloc.3
0x36f01  ldloc.3
0x36f02  ldstr    aName// "Name"
0x36f07  ldarg.2
0x36f08  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36f0d  ldloc.0
0x36f0e  ldstr    aPrivilege// "Privilege"
0x36f13  ldc.i4.1
0x36f14  newarr   [mscorlib]System.String
0x36f19  dup
0x36f1a  ldc.i4.0
0x36f1b  ldstr    aId// "Id"
0x36f20  stelem.ref
0x36f21  ldloc.3
0x36f22  ldc.i4   0x168
0x36f27  ldstr    aRemoveprivileg// "RemovePrivilegeFromRole"
0x36f2c  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36f31  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x36f36  stloc.s  4
0x36f38  ldloc.s  4
0x36f3a  brtrue.s loc_36F5B
0x36f3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36f41  ldstr    a0PrivilegeWasn// "{0} privilege wasn't found"
0x36f46  ldc.i4.1
0x36f47  newarr   [mscorlib]System.Object
0x36f4c  dup
0x36f4d  ldc.i4.0
0x36f4e  ldarg.2
0x36f4f  stelem.ref
0x36f50  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36f55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x36f5a  throw
0x36f5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36f60  stloc.s  5
0x36f62  ldloc.s  5
0x36f64  ldstr    aSecurityroleid// "SecurityRoleId"
0x36f69  ldloc.2
0x36f6a  ldstr    aId// "Id"
0x36f6f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x36f74  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36f79  ldloc.s  5
0x36f7b  ldstr    aPrivilegeid// "PrivilegeId"
0x36f80  ldloc.s  4
0x36f82  ldstr    aId// "Id"
0x36f87  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x36f8c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36f91  ldloc.0
0x36f92  ldstr    aSecurityrolepr// "SecurityRolePrivileges"
0x36f97  ldc.i4.1
0x36f98  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x36f9d  dup
0x36f9e  ldc.i4.0
0x36f9f  ldloc.s  5
0x36fa1  stelem.ref
0x36fa2  ldc.i4   0x172
0x36fa7  ldstr    aRemoveprivileg// "RemovePrivilegeFromRole"
0x36fac  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36fb1  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x36fb6  pop
0x36fb7  leave.s  loc_36FC3
0x36fb9  ldloc.0
0x36fba  brfalse.s loc_36FC2
0x36fbc  ldloc.0
0x36fbd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36fc2  endfinally
0x36fc3  ret
```
