# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::GetIdFromName

- ea: `0x367c0`
- end: `0x36882`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::GetIdFromName`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36ae0`
- `0x38280`
- `0x383f0`

## callees

- `0x17810`
- `0x17830`
- `0x367c0`

## string_xrefs

- `0x367ea`: `SecurityRole`
- `0x36806`: `SecurityRole`
- `0x36823`: `SecurityRole`
- `0x36857`: `SecurityRole`
- `0x367f8`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x367c0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x367c5  pop
0x367c6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x367cb  stloc.0
0x367cc  ldloc.0
0x367cd  ldstr    aName// "Name"
0x367d2  ldarg.1
0x367d3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x367d8  ldc.i4.1
0x367d9  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x367de  dup
0x367df  ldc.i4.0
0x367e0  ldloc.0
0x367e1  stelem.ref
0x367e2  stloc.1
0x367e3  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x367e8  stloc.2
0x367e9  ldloc.2
0x367ea  ldstr    aSecurityrole// "SecurityRole"
0x367ef  ldnull
0x367f0  ldloc.1
0x367f1  ldc.i4.s 0x3B
0x367f3  ldstr    aGetidfromname// "GetIdFromName"
0x367f8  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x367fd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x36802  stloc.3
0x36803  ldloc.3
0x36804  brtrue.s loc_36812
0x36806  ldstr    aSecurityrole// "SecurityRole"
0x3680b  ldarg.1
0x3680c  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBObjectDoesNotExist(string objectType, object value)
0x36811  throw
0x36812  ldloc.3
0x36813  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x36818  stloc.s  4
0x3681a  ldloca.s 4
0x3681c  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x36821  brtrue.s loc_3682F
0x36823  ldstr    aSecurityrole// "SecurityRole"
0x36828  ldarg.1
0x36829  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBObjectDoesNotExist(string objectType, object value)
0x3682e  throw
0x3682f  ldloca.s 4
0x36831  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x36836  stloc.s  5
0x36838  ldloca.s 5
0x3683a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x3683f  ldstr    aId// "Id"
0x36844  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x36849  unbox.any [mscorlib]System.Guid
0x3684e  ldloca.s 4
0x36850  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x36855  brfalse.s loc_36863
0x36857  ldstr    aSecurityrole// "SecurityRole"
0x3685c  ldarg.1
0x3685d  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBDuplicateRecord(string objectType, object value)
0x36862  throw
0x36863  stloc.s  6
0x36865  leave.s  loc_3687F
0x36867  ldloca.s 4
0x36869  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x3686f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36874  endfinally
0x36875  ldloc.2
0x36876  brfalse.s loc_3687E
0x36878  ldloc.2
0x36879  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3687e  endfinally
0x3687f  ldloc.s  6
0x36881  ret
```
