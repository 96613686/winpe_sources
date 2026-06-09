# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveSecurityRoleName

- ea: `0x36890`
- end: `0x368f5`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveSecurityRoleName`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36920`

## callees

- `0x17810`
- `0x36890`

## string_xrefs

- `0x36897`: `SecurityRole`
- `0x368c5`: `SecurityRole`
- `0x368b7`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x368b2`: `RetrieveSecurityRoleName`

## pseudocode

```c

```

## disassembly

```asm
0x36890  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36895  stloc.0
0x36896  ldloc.0
0x36897  ldstr    aSecurityrole// "SecurityRole"
0x3689c  ldarg.1
0x3689d  box      [mscorlib]System.Guid
0x368a2  ldc.i4.1
0x368a3  newarr   [mscorlib]System.String
0x368a8  dup
0x368a9  ldc.i4.0
0x368aa  ldstr    aName// "Name"
0x368af  stelem.ref
0x368b0  ldc.i4.s 0x60
0x368b2  ldstr    aRetrievesecuri// "RetrieveSecurityRoleName"
0x368b7  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x368bc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x368c1  stloc.1
0x368c2  ldloc.1
0x368c3  brtrue.s loc_368D6
0x368c5  ldstr    aSecurityrole// "SecurityRole"
0x368ca  ldarg.1
0x368cb  box      [mscorlib]System.Guid
0x368d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBObjectDoesNotExist(string objectType, object value)
0x368d5  throw
0x368d6  ldloc.1
0x368d7  ldstr    aName// "Name"
0x368dc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x368e1  castclass [mscorlib]System.String
0x368e6  stloc.2
0x368e7  leave.s  loc_368F3
0x368e9  ldloc.0
0x368ea  brfalse.s loc_368F2
0x368ec  ldloc.0
0x368ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x368f2  endfinally
0x368f3  ldloc.2
0x368f4  ret
```
