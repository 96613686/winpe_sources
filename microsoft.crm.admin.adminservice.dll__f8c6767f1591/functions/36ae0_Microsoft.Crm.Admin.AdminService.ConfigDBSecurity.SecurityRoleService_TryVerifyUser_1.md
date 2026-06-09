# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::TryVerifyUser_1

- ea: `0x36ae0`
- end: `0x36ba4`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::TryVerifyUser_1`
- size: `196`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36a00`
- `0x36aa0`
- `0x36bb0`

## callees

- `0x367c0`
- `0x36ae0`
- `0x37180`

## string_xrefs

- `0x36b10`: `SecurityRoleId`
- `0x36b56`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x36ae0  ldarg.2
0x36ae1  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x36ae6  ldarg.0
0x36ae7  ldarga.s 2
0x36ae9  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36aef  callvirt instance string [mscorlib]System.Object::ToString()
0x36af4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::GetIdFromName(string roleName)
0x36af9  stloc.0
0x36afa  ldc.i4.1
0x36afb  newarr   [mscorlib]System.String
0x36b00  dup
0x36b01  ldc.i4.0
0x36b02  ldstr    aId// "Id"
0x36b07  stelem.ref
0x36b08  stloc.1
0x36b09  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x36b0e  stloc.2
0x36b0f  ldloc.2
0x36b10  ldstr    aSecurityroleid// "SecurityRoleId"
0x36b15  ldloc.0
0x36b16  box      [mscorlib]System.Guid
0x36b1b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36b20  ldloc.2
0x36b21  ldstr    aSystemuserid// "SystemUserId"
0x36b26  ldarg.1
0x36b27  box      [mscorlib]System.Guid
0x36b2c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x36b31  ldc.i4.1
0x36b32  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x36b37  dup
0x36b38  ldc.i4.0
0x36b39  ldloc.2
0x36b3a  stelem.ref
0x36b3b  stloc.3
0x36b3c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36b41  stloc.s  4
0x36b43  ldloc.s  4
0x36b45  ldstr    aSystemuserrole// "SystemUserRoles"
0x36b4a  ldloc.1
0x36b4b  ldloc.3
0x36b4c  ldc.i4   0xE1
0x36b51  ldstr    aTryverifyuser// "TryVerifyUser"
0x36b56  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36b5b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x36b60  stloc.s  5
0x36b62  ldloc.s  5
0x36b64  brtrue.s loc_36B6B
0x36b66  ldc.i4.0
0x36b67  stloc.s  6
0x36b69  leave.s  loc_36BA1
0x36b6b  ldloc.s  5
0x36b6d  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x36b72  stloc.s  7
0x36b74  ldloca.s 7
0x36b76  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x36b7b  brtrue.s loc_36B82
0x36b7d  ldc.i4.0
0x36b7e  stloc.s  6
0x36b80  leave.s  loc_36BA1
0x36b82  ldc.i4.1
0x36b83  stloc.s  6
0x36b85  leave.s  loc_36BA1
0x36b87  ldloca.s 7
0x36b89  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x36b8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36b94  endfinally
0x36b95  ldloc.s  4
0x36b97  brfalse.s loc_36BA0
0x36b99  ldloc.s  4
0x36b9b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36ba0  endfinally
0x36ba1  ldloc.s  6
0x36ba3  ret
```
