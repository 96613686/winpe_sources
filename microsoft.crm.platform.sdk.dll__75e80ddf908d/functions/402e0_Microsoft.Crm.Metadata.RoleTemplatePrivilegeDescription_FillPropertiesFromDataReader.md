# Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::FillPropertiesFromDataReader

- ea: `0x402e0`
- end: `0x40462`
- name: `Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::FillPropertiesFromDataReader`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x402e0`
- `0x40600`
- `0x40620`
- `0x40640`
- `0x40660`
- `0x40680`
- `0x406a0`
- `0x406c0`

## string_xrefs

- `0x4034f`: `PrivilegeId`
- `0x40371`: `PrivilegeId`
- `0x402e1`: `RoleTemplatePrivilegeId`
- `0x40303`: `RoleTemplatePrivilegeId`
- `0x40318`: `RoleTemplateId`
- `0x4033a`: `RoleTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x402e0  ldarg.1
0x402e1  ldstr    aRoletemplatepr_1// "RoleTemplatePrivilegeId"
0x402e6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x402eb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x402f0  ldtoken  [mscorlib]System.DBNull
0x402f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x402fa  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x402ff  brfalse.s loc_40317
0x40301  ldarg.0
0x40302  ldarg.1
0x40303  ldstr    aRoletemplatepr_1// "RoleTemplatePrivilegeId"
0x40308  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4030d  unbox.any [mscorlib]System.Guid
0x40312  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_RoleTemplatePrivilegeId(valuetype [mscorlib]System.Guid value)
0x40317  ldarg.1
0x40318  ldstr    aRoletemplateid_0// "RoleTemplateId"
0x4031d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40322  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x40327  ldtoken  [mscorlib]System.DBNull
0x4032c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40331  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x40336  brfalse.s loc_4034E
0x40338  ldarg.0
0x40339  ldarg.1
0x4033a  ldstr    aRoletemplateid_0// "RoleTemplateId"
0x4033f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40344  unbox.any [mscorlib]System.Guid
0x40349  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_RoleTemplateId(valuetype [mscorlib]System.Guid value)
0x4034e  ldarg.1
0x4034f  ldstr    aPrivilegeid_0// "PrivilegeId"
0x40354  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40359  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4035e  ldtoken  [mscorlib]System.DBNull
0x40363  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40368  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4036d  brfalse.s loc_40385
0x4036f  ldarg.0
0x40370  ldarg.1
0x40371  ldstr    aPrivilegeid_0// "PrivilegeId"
0x40376  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4037b  unbox.any [mscorlib]System.Guid
0x40380  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0x40385  ldarg.1
0x40386  ldstr    aIsbasic// "IsBasic"
0x4038b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40390  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x40395  ldtoken  [mscorlib]System.DBNull
0x4039a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4039f  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x403a4  brfalse.s loc_403BC
0x403a6  ldarg.0
0x403a7  ldarg.1
0x403a8  ldstr    aIsbasic// "IsBasic"
0x403ad  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x403b2  unbox.any [mscorlib]System.Boolean
0x403b7  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsBasic(bool value)
0x403bc  ldarg.1
0x403bd  ldstr    aIslocal// "IsLocal"
0x403c2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x403c7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x403cc  ldtoken  [mscorlib]System.DBNull
0x403d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x403d6  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x403db  brfalse.s loc_403F3
0x403dd  ldarg.0
0x403de  ldarg.1
0x403df  ldstr    aIslocal// "IsLocal"
0x403e4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x403e9  unbox.any [mscorlib]System.Boolean
0x403ee  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsLocal(bool value)
0x403f3  ldarg.1
0x403f4  ldstr    aIsdeep// "IsDeep"
0x403f9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x403fe  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x40403  ldtoken  [mscorlib]System.DBNull
0x40408  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4040d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x40412  brfalse.s loc_4042A
0x40414  ldarg.0
0x40415  ldarg.1
0x40416  ldstr    aIsdeep// "IsDeep"
0x4041b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40420  unbox.any [mscorlib]System.Boolean
0x40425  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsDeep(bool value)
0x4042a  ldarg.1
0x4042b  ldstr    aIsglobal// "IsGlobal"
0x40430  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40435  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4043a  ldtoken  [mscorlib]System.DBNull
0x4043f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40444  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x40449  brfalse.s loc_40461
0x4044b  ldarg.0
0x4044c  ldarg.1
0x4044d  ldstr    aIsglobal// "IsGlobal"
0x40452  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40457  unbox.any [mscorlib]System.Boolean
0x4045c  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsGlobal(bool value)
0x40461  ret
```
