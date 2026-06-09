# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveByPuid_0

- ea: `0x37fc0`
- end: `0x380db`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveByPuid_0`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x37fb0`

## callees

- `0x37fc0`
- `0x380e0`

## string_xrefs

- `0x37ffe`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x3805e`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x37fc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x37fc5  stloc.0
0x37fc6  ldloc.0
0x37fc7  ldstr    aAuthinfo// "AuthInfo"
0x37fcc  ldarg.1
0x37fcd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x37fd2  ldc.i4.1
0x37fd3  newarr   [mscorlib]System.String
0x37fd8  dup
0x37fd9  ldc.i4.0
0x37fda  ldstr    aUserid// "UserId"
0x37fdf  stelem.ref
0x37fe0  stloc.1
0x37fe1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::.ctor()
0x37fe6  stloc.2
0x37fe7  ldarg.3
0x37fe8  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x37fed  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x37ff2  ldloc.1
0x37ff3  ldloc.0
0x37ff4  ldc.i4   0x21A
0x37ff9  ldstr    aRetrievebypuid// "RetrieveByPuid"
0x37ffe  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x38003  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x38008  stloc.3
0x38009  ldloc.3
0x3800a  brtrue.s loc_38014
0x3800c  ldnull
0x3800d  stloc.s  6
0x3800f  leave    loc_380D8
0x38014  ldloc.3
0x38015  ldstr    aUserid// "UserId"
0x3801a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3801f  unbox.any [mscorlib]System.Guid
0x38024  stloc.s  4
0x38026  ldarg.2
0x38027  ldloc.s  4
0x38029  call     class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveBySystemUserId(bool ignoreNonExistingUser, valuetype [mscorlib]System.Guid systemUserId)
0x3802e  stloc.s  5
0x38030  ldloc.2
0x38031  ldloc.s  5
0x38033  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::Add(var<u1>)
0x38038  leave    loc_380D1
0x3803d  pop
0x3803e  ldarg.3
0x3803f  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x38044  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x38049  ldloc.1
0x3804a  ldc.i4.1
0x3804b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x38050  dup
0x38051  ldc.i4.0
0x38052  ldloc.0
0x38053  stelem.ref
0x38054  ldc.i4   0x226
0x38059  ldstr    aRetrievebypuid// "RetrieveByPuid"
0x3805e  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x38063  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x38068  stloc.s  7
0x3806a  ldloc.s  7
0x3806c  brfalse.s loc_38077
0x3806e  ldloc.s  7
0x38070  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x38075  brtrue.s loc_3807C
0x38077  ldnull
0x38078  stloc.s  6
0x3807a  leave.s  loc_380D8
0x3807c  ldloc.s  7
0x3807e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x38083  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x38088  stloc.s  8
0x3808a  br.s     loc_380B6
0x3808c  ldloca.s 8
0x3808e  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x38093  ldstr    aUserid// "UserId"
0x38098  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3809d  unbox.any [mscorlib]System.Guid
0x380a2  stloc.s  9
0x380a4  ldarg.2
0x380a5  ldloc.s  9
0x380a7  call     class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveBySystemUserId(bool ignoreNonExistingUser, valuetype [mscorlib]System.Guid systemUserId)
0x380ac  stloc.s  0xA
0x380ae  ldloc.2
0x380af  ldloc.s  0xA
0x380b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::Add(var<u1>)
0x380b6  ldloca.s 8
0x380b8  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x380bd  brtrue.s loc_3808C
0x380bf  leave.s  loc_380CF
0x380c1  ldloca.s 8
0x380c3  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x380c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x380ce  endfinally
0x380cf  leave.s  loc_380D1
0x380d1  ldloc.2
0x380d2  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData>::ToArray()
0x380d7  ret
0x380d8  ldloc.s  6
0x380da  ret
```
