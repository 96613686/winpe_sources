# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::TryCheckPrivilege_4

- ea: `0x38690`
- end: `0x38811`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::TryCheckPrivilege_4`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x38650`
- `0x38670`

## callees

- `0x38690`

## string_xrefs

- `0x3878e`: `PrivilegeId`
- `0x386bb`: `SecurityRoleId`
- `0x38776`: `SecurityRoleId`
- `0x3877d`: `SecurityRoleId`
- `0x38703`: `Privilege`
- `0x387a5`: `SecurityRolePrivileges`
- `0x386d5`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x3872a`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x387cd`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x386d0`: `TryCheckPrivilege`
- `0x38725`: `TryCheckPrivilege`
- `0x387c8`: `TryCheckPrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x38690  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x38695  stloc.0
0x38696  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3869b  stloc.1
0x3869c  ldloc.1
0x3869d  ldstr    aSystemuserid// "SystemUserId"
0x386a2  ldarg.2
0x386a3  box      [mscorlib]System.Guid
0x386a8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x386ad  ldloc.0
0x386ae  ldstr    aSystemuserrole// "SystemUserRoles"
0x386b3  ldc.i4.1
0x386b4  newarr   [mscorlib]System.String
0x386b9  dup
0x386ba  ldc.i4.0
0x386bb  ldstr    aSecurityroleid// "SecurityRoleId"
0x386c0  stelem.ref
0x386c1  ldc.i4.1
0x386c2  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x386c7  dup
0x386c8  ldc.i4.0
0x386c9  ldloc.1
0x386ca  stelem.ref
0x386cb  ldc.i4   0x346
0x386d0  ldstr    aTrycheckprivil// "TryCheckPrivilege"
0x386d5  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x386da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x386df  stloc.2
0x386e0  ldloc.2
0x386e1  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x386e6  brfalse.s loc_386F0
0x386e8  ldc.i4.0
0x386e9  stloc.s  6
0x386eb  leave    loc_3880E
0x386f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x386f5  stloc.3
0x386f6  ldloc.3
0x386f7  ldstr    aName// "Name"
0x386fc  ldarg.1
0x386fd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x38702  ldloc.0
0x38703  ldstr    aPrivilege// "Privilege"
0x38708  ldc.i4.1
0x38709  newarr   [mscorlib]System.String
0x3870e  dup
0x3870f  ldc.i4.0
0x38710  ldstr    aId// "Id"
0x38715  stelem.ref
0x38716  ldc.i4.1
0x38717  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3871c  dup
0x3871d  ldc.i4.0
0x3871e  ldloc.3
0x3871f  stelem.ref
0x38720  ldc.i4   0x34F
0x38725  ldstr    aTrycheckprivil// "TryCheckPrivilege"
0x3872a  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3872f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x38734  stloc.s  4
0x38736  ldloc.s  4
0x38738  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x3873d  brfalse.s loc_38747
0x3873f  ldc.i4.0
0x38740  stloc.s  6
0x38742  leave    loc_3880E
0x38747  ldloc.s  4
0x38749  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3874e  call     T0x2B00005D
0x38753  stloc.s  5
0x38755  ldloc.2
0x38756  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3875b  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x38760  stloc.s  7
0x38762  br.s     loc_387E3
0x38764  ldloca.s 7
0x38766  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x3876b  stloc.s  8
0x3876d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x38772  stloc.s  9
0x38774  ldloc.s  9
0x38776  ldstr    aSecurityroleid// "SecurityRoleId"
0x3877b  ldloc.s  8
0x3877d  ldstr    aSecurityroleid// "SecurityRoleId"
0x38782  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x38787  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3878c  ldloc.s  9
0x3878e  ldstr    aPrivilegeid// "PrivilegeId"
0x38793  ldloc.s  5
0x38795  ldstr    aId// "Id"
0x3879a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3879f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x387a4  ldloc.0
0x387a5  ldstr    aSecurityrolepr// "SecurityRolePrivileges"
0x387aa  ldc.i4.1
0x387ab  newarr   [mscorlib]System.String
0x387b0  dup
0x387b1  ldc.i4.0
0x387b2  ldstr    aId// "Id"
0x387b7  stelem.ref
0x387b8  ldc.i4.1
0x387b9  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x387be  dup
0x387bf  ldc.i4.0
0x387c0  ldloc.s  9
0x387c2  stelem.ref
0x387c3  ldc.i4   0x35D
0x387c8  ldstr    aTrycheckprivil// "TryCheckPrivilege"
0x387cd  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x387d2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x387d7  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x387dc  brtrue.s loc_387E3
0x387de  ldc.i4.1
0x387df  stloc.s  6
0x387e1  leave.s  loc_3880E
0x387e3  ldloca.s 7
0x387e5  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x387ea  brtrue   loc_38764
0x387ef  leave.s  loc_387FF
0x387f1  ldloca.s 7
0x387f3  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x387f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x387fe  endfinally
0x387ff  ldc.i4.0
0x38800  stloc.s  6
0x38802  leave.s  loc_3880E
0x38804  ldloc.0
0x38805  brfalse.s loc_3880D
0x38807  ldloc.0
0x38808  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3880d  endfinally
0x3880e  ldloc.s  6
0x38810  ret
```
