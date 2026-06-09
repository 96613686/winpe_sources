# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveUsers

- ea: `0x36fd0`
- end: `0x3716d`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrieveUsers`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x36fd0`
- `0x37180`
- `0x371e0`

## string_xrefs

- `0x36ffd`: `SecurityRole`
- `0x3705c`: `SecurityRoleId`
- `0x37024`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x3709a`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x37122`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x36fd0  ldarg.1
0x36fd1  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x36fd6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36fdb  stloc.0
0x36fdc  ldnull
0x36fdd  stloc.1
0x36fde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36fe3  stloc.2
0x36fe4  ldloc.2
0x36fe5  ldstr    aName// "Name"
0x36fea  ldarga.s 1
0x36fec  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36ff2  callvirt instance string [mscorlib]System.Object::ToString()
0x36ff7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36ffc  ldloc.0
0x36ffd  ldstr    aSecurityrole// "SecurityRole"
0x37002  ldc.i4.1
0x37003  newarr   [mscorlib]System.String
0x37008  dup
0x37009  ldc.i4.0
0x3700a  ldstr    aId// "Id"
0x3700f  stelem.ref
0x37010  ldc.i4.1
0x37011  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x37016  dup
0x37017  ldc.i4.0
0x37018  ldloc.2
0x37019  stelem.ref
0x3701a  ldc.i4   0x185
0x3701f  ldstr    aRetrieveusers// "RetrieveUsers"
0x37024  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x37029  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3702e  stloc.3
0x3702f  ldloc.3
0x37030  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x37035  brtrue.s loc_37043
0x37037  ldloc.3
0x37038  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3703d  call     T0x2B00005D
0x37042  stloc.1
0x37043  ldloc.1
0x37044  brtrue.s loc_37053
0x37046  ldc.i4.0
0x37047  newarr   Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData
0x3704c  stloc.s  8
0x3704e  leave    loc_3716A
0x37053  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x37058  stloc.s  4
0x3705a  ldloc.s  4
0x3705c  ldstr    aSecurityroleid// "SecurityRoleId"
0x37061  ldloc.1
0x37062  ldstr    aId// "Id"
0x37067  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3706c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x37071  ldloc.0
0x37072  ldstr    aSystemuserrole// "SystemUserRoles"
0x37077  ldc.i4.1
0x37078  newarr   [mscorlib]System.String
0x3707d  dup
0x3707e  ldc.i4.0
0x3707f  ldstr    aSystemuserid// "SystemUserId"
0x37084  stelem.ref
0x37085  ldc.i4.1
0x37086  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3708b  dup
0x3708c  ldc.i4.0
0x3708d  ldloc.s  4
0x3708f  stelem.ref
0x37090  ldc.i4   0x193
0x37095  ldstr    aRetrieveusers// "RetrieveUsers"
0x3709a  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3709f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x370a4  stloc.s  5
0x370a6  ldloc.s  5
0x370a8  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x370ad  brfalse.s loc_370BC
0x370af  ldc.i4.0
0x370b0  newarr   Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData
0x370b5  stloc.s  8
0x370b7  leave    loc_3716A
0x370bc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::.ctor()
0x370c1  stloc.s  6
0x370c3  ldc.i4.4
0x370c4  newarr   [mscorlib]System.String
0x370c9  dup
0x370ca  ldc.i4.0
0x370cb  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x370d0  stelem.ref
0x370d1  dup
0x370d2  ldc.i4.1
0x370d3  ldstr    aId// "Id"
0x370d8  stelem.ref
0x370d9  dup
0x370da  ldc.i4.2
0x370db  ldstr    aIsdisabled// "IsDisabled"
0x370e0  stelem.ref
0x370e1  dup
0x370e2  ldc.i4.3
0x370e3  ldstr    aName// "Name"
0x370e8  stelem.ref
0x370e9  stloc.s  7
0x370eb  ldloc.s  5
0x370ed  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x370f2  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x370f7  stloc.s  9
0x370f9  br.s     loc_3713C
0x370fb  ldloca.s 9
0x370fd  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x37102  stloc.s  0xA
0x37104  ldloc.0
0x37105  ldstr    aSystemuser// "SystemUser"
0x3710a  ldloc.s  0xA
0x3710c  ldstr    aSystemuserid// "SystemUserId"
0x37111  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x37116  ldloc.s  7
0x37118  ldc.i4   0x1A4
0x3711d  ldstr    aRetrieveusers// "RetrieveUsers"
0x37122  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x37127  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x3712c  stloc.s  0xB
0x3712e  ldloc.s  6
0x37130  ldloc.s  0xB
0x37132  newobj   instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x37137  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::Add(var<u1>)
0x3713c  ldloca.s 9
0x3713e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x37143  brtrue.s loc_370FB
0x37145  leave.s  loc_37155
0x37147  ldloca.s 9
0x37149  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x3714f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37154  endfinally
0x37155  ldloc.s  6
0x37157  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::ToArray()
0x3715c  stloc.s  8
0x3715e  leave.s  loc_3716A
0x37160  ldloc.0
0x37161  brfalse.s loc_37169
0x37163  ldloc.0
0x37164  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37169  endfinally
0x3716a  ldloc.s  8
0x3716c  ret
```
