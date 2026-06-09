# Microsoft.Crm.Admin.AdminService.UserService::RemovePrincipalFromConfigDB

- ea: `0x34c90`
- end: `0x350cd`
- name: `Microsoft.Crm.Admin.AdminService.UserService::RemovePrincipalFromConfigDB`
- size: `1085`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x282b0`

## callees

- `0x34c90`

## string_xrefs

- `0x34d16`: `RemovePrincipalFromConfigDB`
- `0x34dc7`: `RemovePrincipalFromConfigDB`
- `0x34e04`: `RemovePrincipalFromConfigDB`
- `0x34e53`: `RemovePrincipalFromConfigDB`
- `0x34ebc`: `RemovePrincipalFromConfigDB`
- `0x34f10`: `RemovePrincipalFromConfigDB`
- `0x34f86`: `RemovePrincipalFromConfigDB`
- `0x34fc3`: `RemovePrincipalFromConfigDB`
- `0x35068`: `RemovePrincipalFromConfigDB`
- `0x34d1b`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34dcc`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34e09`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34e58`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34ec1`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34f15`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34f8b`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34fc8`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x3506d`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x34e40`: `SecurityRole`
- `0x34e83`: `SecurityRoleId`

## pseudocode

```c

```

## disassembly

```asm
0x34c90  ldarg.0
0x34c91  ldstr    aOrganizationid// "organizationId"
0x34c96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x34c9b  ldarg.1
0x34c9c  ldstr    aCrmid// "crmId"
0x34ca1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x34ca6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x34cab  stloc.0
0x34cac  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x34cb1  stloc.1
0x34cb2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34cb7  stloc.2
0x34cb8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34cbd  stloc.3
0x34cbe  ldloc.1
0x34cbf  ldc.i4.2
0x34cc0  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x34cc5  stloc.s  4
0x34cc7  ldloc.s  4
0x34cc9  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x34cce  ldloc.s  4
0x34cd0  callvirt instance class [System.Data]System.Data.IDbTransaction [System.Data]System.Data.IDbConnection::BeginTransaction()
0x34cd5  stloc.s  5
0x34cd7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34cdc  stloc.s  6
0x34cde  ldloc.s  6
0x34ce0  ldstr    aCrmuserid// "CrmUserId"
0x34ce5  ldarg.1
0x34ce6  box      [mscorlib]System.Guid
0x34ceb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34cf0  ldloc.s  6
0x34cf2  ldstr    aOrganizationid_0// "OrganizationId"
0x34cf7  ldarg.0
0x34cf8  box      [mscorlib]System.Guid
0x34cfd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34d02  ldloc.1
0x34d03  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x34d08  ldnull
0x34d09  ldc.i4.1
0x34d0a  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34d0f  dup
0x34d10  ldc.i4.0
0x34d11  ldloc.s  6
0x34d13  stelem.ref
0x34d14  ldc.i4.s 0x31
0x34d16  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34d1b  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34d20  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x34d25  stloc.s  7
0x34d27  ldloc.s  7
0x34d29  brtrue.s loc_34D30
0x34d2b  leave    loc_350CC
0x34d30  ldloc.s  7
0x34d32  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x34d37  stloc.s  9
0x34d39  br.s     loc_34D5D
0x34d3b  ldloca.s 9
0x34d3d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x34d42  stloc.s  0xA
0x34d44  ldloca.s 0xA
0x34d46  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x34d4b  ldstr    aUserid// "UserId"
0x34d50  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x34d55  unbox.any [mscorlib]System.Guid
0x34d5a  stloc.2
0x34d5b  leave.s  loc_34D76
0x34d5d  ldloca.s 9
0x34d5f  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x34d64  brtrue.s loc_34D3B
0x34d66  leave.s  loc_34D76
0x34d68  ldloca.s 9
0x34d6a  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x34d70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34d75  endfinally
0x34d76  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34d7b  stloc.s  8
0x34d7d  ldloc.s  8
0x34d7f  ldstr    aUserid// "UserId"
0x34d84  ldloc.2
0x34d85  box      [mscorlib]System.Guid
0x34d8a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34d8f  ldloc.s  8
0x34d91  ldstr    aCrmuserid// "CrmUserId"
0x34d96  ldarg.1
0x34d97  box      [mscorlib]System.Guid
0x34d9c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34da1  ldloc.s  8
0x34da3  ldstr    aOrganizationid_0// "OrganizationId"
0x34da8  ldarg.0
0x34da9  box      [mscorlib]System.Guid
0x34dae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34db3  ldloc.1
0x34db4  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x34db9  ldc.i4.1
0x34dba  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34dbf  dup
0x34dc0  ldc.i4.0
0x34dc1  ldloc.s  8
0x34dc3  stelem.ref
0x34dc4  ldc.i4.0
0x34dc5  ldc.i4.s 0x47
0x34dc7  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34dcc  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34dd1  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], bool, int32, string, string)
0x34dd6  pop
0x34dd7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34ddc  stloc.s  6
0x34dde  ldloc.s  6
0x34de0  ldstr    aUserid// "UserId"
0x34de5  ldloc.2
0x34de6  box      [mscorlib]System.Guid
0x34deb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34df0  ldloc.1
0x34df1  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x34df6  ldnull
0x34df7  ldc.i4.1
0x34df8  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34dfd  dup
0x34dfe  ldc.i4.0
0x34dff  ldloc.s  6
0x34e01  stelem.ref
0x34e02  ldc.i4.s 0x4B
0x34e04  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34e09  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34e0e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x34e13  stloc.s  7
0x34e15  ldloc.s  7
0x34e17  brtrue   loc_34FD8
0x34e1c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34e21  stloc.s  6
0x34e23  ldloc.s  6
0x34e25  ldstr    aName// "Name"
0x34e2a  ldc.i4.1
0x34e2b  stloc.s  0xC
0x34e2d  ldloca.s 0xC
0x34e2f  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x34e35  callvirt instance string [mscorlib]System.Object::ToString()
0x34e3a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34e3f  ldloc.1
0x34e40  ldstr    aSecurityrole// "SecurityRole"
0x34e45  ldnull
0x34e46  ldc.i4.1
0x34e47  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34e4c  dup
0x34e4d  ldc.i4.0
0x34e4e  ldloc.s  6
0x34e50  stelem.ref
0x34e51  ldc.i4.s 0x53
0x34e53  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34e58  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34e5d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x34e62  stloc.s  7
0x34e64  ldloc.s  7
0x34e66  brfalse.s loc_34ED6
0x34e68  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34e6d  stloc.s  6
0x34e6f  ldloc.s  6
0x34e71  ldstr    aSystemuserid// "SystemUserId"
0x34e76  ldloc.2
0x34e77  box      [mscorlib]System.Guid
0x34e7c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34e81  ldloc.s  6
0x34e83  ldstr    aSecurityroleid// "SecurityRoleId"
0x34e88  ldloc.s  7
0x34e8a  ldc.i4.0
0x34e8b  call     T0x2B0000B1
0x34e90  stloc.s  0xA
0x34e92  ldloca.s 0xA
0x34e94  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Key()
0x34e99  unbox.any [mscorlib]System.Guid
0x34e9e  box      [mscorlib]System.Guid
0x34ea3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34ea8  ldloc.1
0x34ea9  ldstr    aSystemuserrole// "SystemUserRoles"
0x34eae  ldnull
0x34eaf  ldc.i4.1
0x34eb0  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34eb5  dup
0x34eb6  ldc.i4.0
0x34eb7  ldloc.s  6
0x34eb9  stelem.ref
0x34eba  ldc.i4.s 0x59
0x34ebc  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34ec1  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34ec6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x34ecb  stloc.s  7
0x34ecd  ldloc.s  7
0x34ecf  brfalse.s loc_34ED6
0x34ed1  leave    loc_350CC
0x34ed6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34edb  stloc.s  8
0x34edd  ldloc.s  8
0x34edf  ldstr    aUserid// "UserId"
0x34ee4  ldloc.2
0x34ee5  box      [mscorlib]System.Guid
0x34eea  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34eef  ldloc.1
0x34ef0  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x34ef5  ldc.i4.1
0x34ef6  newarr   [mscorlib]System.String
0x34efb  dup
0x34efc  ldc.i4.0
0x34efd  ldstr    aAuthinfo// "AuthInfo"
0x34f02  stelem.ref
0x34f03  ldc.i4.1
0x34f04  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34f09  dup
0x34f0a  ldc.i4.0
0x34f0b  ldloc.s  8
0x34f0d  stelem.ref
0x34f0e  ldc.i4.s 0x63
0x34f10  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34f15  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34f1a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x34f1f  stloc.s  0xB
0x34f21  ldloc.s  0xB
0x34f23  brfalse.s loc_34F72
0x34f25  ldloc.s  0xB
0x34f27  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x34f2c  stloc.s  0xD
0x34f2e  br.s     loc_34F59
0x34f30  ldloca.s 0xD
0x34f32  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x34f37  stloc.s  0xA
0x34f39  ldloca.s 0xA
0x34f3b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x34f40  stloc.s  0xE
0x34f42  ldloc.0
0x34f43  ldloc.s  0xE
0x34f45  ldstr    aAuthinfo// "AuthInfo"
0x34f4a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x34f4f  castclass [mscorlib]System.String
0x34f54  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x34f59  ldloca.s 0xD
0x34f5b  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x34f60  brtrue.s loc_34F30
0x34f62  leave.s  loc_34F72
0x34f64  ldloca.s 0xD
0x34f66  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x34f6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34f71  endfinally
0x34f72  ldloc.1
0x34f73  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x34f78  ldc.i4.1
0x34f79  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34f7e  dup
0x34f7f  ldc.i4.0
0x34f80  ldloc.s  8
0x34f82  stelem.ref
0x34f83  ldc.i4.0
0x34f84  ldc.i4.s 0x71
0x34f86  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34f8b  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34f90  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], bool, int32, string, string)
0x34f95  pop
0x34f96  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34f9b  stloc.s  8
0x34f9d  ldloc.s  8
0x34f9f  ldstr    aId// "Id"
0x34fa4  ldloc.2
0x34fa5  box      [mscorlib]System.Guid
0x34faa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x34faf  ldloc.1
0x34fb0  ldstr    aSystemuser// "SystemUser"
0x34fb5  ldc.i4.1
0x34fb6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x34fbb  dup
0x34fbc  ldc.i4.0
0x34fbd  ldloc.s  8
0x34fbf  stelem.ref
0x34fc0  ldc.i4.0
0x34fc1  ldc.i4.s 0x75
0x34fc3  ldstr    aRemoveprincipa// "RemovePrincipalFromConfigDB"
0x34fc8  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x34fcd  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], bool, int32, string, string)
0x34fd2  pop
0x34fd3  leave    loc_3509C
0x34fd8  ldloc.s  7
0x34fda  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x34fdf  stloc.s  0x10
0x34fe1  br.s     loc_35005
0x34fe3  ldloca.s 0x10
0x34fe5  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x34fea  stloc.s  0xA
0x34fec  ldloca.s 0xA
0x34fee  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x34ff3  ldstr    aOrganizationid_0// "OrganizationId"
0x34ff8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x34ffd  unbox.any [mscorlib]System.Guid
0x35002  stloc.3
0x35003  leave.s  loc_3501E
0x35005  ldloca.s 0x10
0x35007  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x3500c  brtrue.s loc_34FE3
0x3500e  leave.s  loc_3501E
0x35010  ldloca.s 0x10
0x35012  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x35018  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3501d  endfinally
0x3501e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
  ... truncated ...
```
