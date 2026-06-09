# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveSecurityRolesForUser_0

- ea: `0x36920`
- end: `0x369f5`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveSecurityRolesForUser_0`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36900`

## callees

- `0x36890`
- `0x36920`

## string_xrefs

- `0x3692e`: `SecurityRoleId`
- `0x369ad`: `SecurityRoleId`
- `0x36971`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x3696c`: `RetrieveSecurityRolesForUser`

## pseudocode

```c

```

## disassembly

```asm
0x36920  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x36925  stloc.0
0x36926  ldc.i4.1
0x36927  newarr   [mscorlib]System.String
0x3692c  dup
0x3692d  ldc.i4.0
0x3692e  ldstr    aSecurityroleid// "SecurityRoleId"
0x36933  stelem.ref
0x36934  stloc.1
0x36935  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3693a  stloc.2
0x3693b  ldloc.2
0x3693c  ldstr    aSystemuserid// "SystemUserId"
0x36941  ldarg.1
0x36942  box      [mscorlib]System.Guid
0x36947  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3694c  ldc.i4.1
0x3694d  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x36952  dup
0x36953  ldc.i4.0
0x36954  ldloc.2
0x36955  stelem.ref
0x36956  stloc.3
0x36957  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x3695c  stloc.s  4
0x3695e  ldloc.s  4
0x36960  ldstr    aSystemuserrole// "SystemUserRoles"
0x36965  ldloc.1
0x36966  ldloc.3
0x36967  ldc.i4   0x8C
0x3696c  ldstr    aRetrievesecuri_0// "RetrieveSecurityRolesForUser"
0x36971  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36976  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3697b  stloc.s  5
0x3697d  ldloc.s  5
0x3697f  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x36984  brfalse.s loc_36990
0x36986  ldloc.0
0x36987  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x3698c  stloc.s  6
0x3698e  leave.s  loc_369F2
0x36990  ldloc.s  5
0x36992  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x36997  stloc.s  7
0x36999  br.s     loc_369C6
0x3699b  ldloca.s 7
0x3699d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x369a2  stloc.s  8
0x369a4  ldloc.0
0x369a5  ldarg.0
0x369a6  ldloca.s 8
0x369a8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x369ad  ldstr    aSecurityroleid// "SecurityRoleId"
0x369b2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x369b7  unbox.any [mscorlib]System.Guid
0x369bc  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveSecurityRoleName(valuetype [mscorlib]System.Guid roleId)
0x369c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x369c6  ldloca.s 7
0x369c8  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x369cd  brtrue.s loc_3699B
0x369cf  leave.s  loc_369EB
0x369d1  ldloca.s 7
0x369d3  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x369d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x369de  endfinally
0x369df  ldloc.s  4
0x369e1  brfalse.s loc_369EA
0x369e3  ldloc.s  4
0x369e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x369ea  endfinally
0x369eb  ldloc.0
0x369ec  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x369f1  ret
0x369f2  ldloc.s  6
0x369f4  ret
```
