# Microsoft.Crm.Tools.Admin.DBImportHelper::ReadUser

- ea: `0x13d90`
- end: `0x13e80`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::ReadUser`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x13c90`

## callees

- `0x13d90`

## string_xrefs

- `0x13d93`: `reader`
- `0x13e02`: `IsActiveDirectoryUser`
- `0x13e18`: `ActiveDirectoryGuid`

## pseudocode

```c

```

## disassembly

```asm
0x13d90  ldarg.0
0x13d91  brtrue.s loc_13D9E
0x13d93  ldstr    aReader// "reader"
0x13d98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13d9d  throw
0x13d9e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::.ctor()
0x13da3  dup
0x13da4  ldarg.0
0x13da5  ldstr    aFullname// "FullName"
0x13daa  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13daf  isinst   [mscorlib]System.String
0x13db4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBFullName(string)
0x13db9  dup
0x13dba  ldarg.0
0x13dbb  ldstr    aFirstname// "FirstName"
0x13dc0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13dc5  isinst   [mscorlib]System.String
0x13dca  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBFirstName(string)
0x13dcf  dup
0x13dd0  ldarg.0
0x13dd1  ldstr    aLastname// "LastName"
0x13dd6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13ddb  isinst   [mscorlib]System.String
0x13de0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBLastName(string)
0x13de5  dup
0x13de6  ldarg.0
0x13de7  ldstr    aDomainname_0// "DomainName"
0x13dec  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13df1  castclass [mscorlib]System.String
0x13df6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::.ctor(string)
0x13dfb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBDomainName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount)
0x13e00  dup
0x13e01  ldarg.0
0x13e02  ldstr    aIsactivedirect_0// "IsActiveDirectoryUser"
0x13e07  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13e0c  unbox.any [mscorlib]System.Boolean
0x13e11  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBIsActiveDirectoryUser(bool)
0x13e16  dup
0x13e17  ldarg.0
0x13e18  ldstr    aActivedirector// "ActiveDirectoryGuid"
0x13e1d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13e22  isinst   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x13e27  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x13e2c  stloc.0
0x13e2d  ldloca.s 0
0x13e2f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x13e34  brtrue.s loc_13E41
0x13e36  ldloca.s 1
0x13e38  initobj  [mscorlib]System.Guid
0x13e3e  ldloc.1
0x13e3f  br.s     loc_13E48
0x13e41  ldloca.s 0
0x13e43  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x13e48  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBActiveDirectoryGuid(valuetype [mscorlib]System.Guid)
0x13e4d  dup
0x13e4e  ldarg.0
0x13e4f  ldstr    aIsdisabled// "IsDisabled"
0x13e54  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13e59  isinst   valuetype [mscorlib]System.Nullable`1<bool>
0x13e5e  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x13e63  stloc.2
0x13e64  ldloca.s 2
0x13e66  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x13e6b  brtrue.s loc_13E70
0x13e6d  ldc.i4.0
0x13e6e  br.s     loc_13E77
0x13e70  ldloca.s 2
0x13e72  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x13e77  ldc.i4.0
0x13e78  ceq
0x13e7a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_IsEnabled(bool)
0x13e7f  ret
```
