# Microsoft.Crm.Tools.Admin.DBImportHelper::AppendRole

- ea: `0x13e80`
- end: `0x13f2c`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::AppendRole`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x13c90`

## callees

- `0x13e80`

## string_xrefs

- `0x13e92`: `RoleTemplateId`
- `0x13ed2`: `AccessMode`

## pseudocode

```c

```

## disassembly

```asm
0x13e80  ldarg.0
0x13e81  ldstr    aRole// "Role"
0x13e86  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13e8b  isinst   [mscorlib]System.String
0x13e90  stloc.0
0x13e91  ldarg.0
0x13e92  ldstr    aRoletemplateid// "RoleTemplateId"
0x13e97  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13e9c  isinst   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x13ea1  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x13ea6  stloc.s  4
0x13ea8  ldloca.s 4
0x13eaa  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x13eaf  brtrue.s loc_13EBD
0x13eb1  ldloca.s 5
0x13eb3  initobj  [mscorlib]System.Guid
0x13eb9  ldloc.s  5
0x13ebb  br.s     loc_13EC4
0x13ebd  ldloca.s 4
0x13ebf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x13ec4  stloc.1
0x13ec5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.DBImportHelper::SysdminRole
0x13eca  ldloc.1
0x13ecb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13ed0  stloc.2
0x13ed1  ldarg.0
0x13ed2  ldstr    aAccessmode// "AccessMode"
0x13ed7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13edc  unbox.any [mscorlib]System.Int32
0x13ee1  ldc.i4.0
0x13ee2  ceq
0x13ee4  stloc.3
0x13ee5  ldarg.1
0x13ee6  dup
0x13ee7  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBIsSystemAdminRole()
0x13eec  ldloc.2
0x13eed  ldloc.3
0x13eee  and
0x13eef  brfalse.s loc_13EF9
0x13ef1  ldarg.1
0x13ef2  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_IsEnabled()
0x13ef7  br.s     loc_13EFA
0x13ef9  ldc.i4.0
0x13efa  or
0x13efb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBIsSystemAdminRole(bool)
0x13f00  ldarg.1
0x13f01  dup
0x13f02  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBRoles()
0x13f07  ldarg.1
0x13f08  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBRoles()
0x13f0d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13f12  brtrue.s loc_13F1B
0x13f14  ldstr    asc_24552// ", "
0x13f19  br.s     loc_13F20
0x13f1b  ldsfld   string [mscorlib]System.String::Empty
0x13f20  ldloc.0
0x13f21  call     string [mscorlib]System.String::Concat(string, string, string)
0x13f26  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBRoles(string)
0x13f2b  ret
```
