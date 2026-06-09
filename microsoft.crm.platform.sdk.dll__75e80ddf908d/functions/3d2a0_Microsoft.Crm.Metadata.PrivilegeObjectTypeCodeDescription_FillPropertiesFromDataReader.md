# Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::FillPropertiesFromDataReader

- ea: `0x3d2a0`
- end: `0x3d390`
- name: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::FillPropertiesFromDataReader`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3d7f0`

## callees

- `0xbc80`
- `0x3d2a0`
- `0x3d4a0`
- `0x3d4f0`
- `0x3d510`
- `0x3d530`
- `0x3d590`

## string_xrefs

- `0x3d2d8`: `PrivilegeId`
- `0x3d2fa`: `PrivilegeId`
- `0x3d2a1`: `PrivilegeObjectTypeCodeId`
- `0x3d2c3`: `PrivilegeObjectTypeCodeId`

## pseudocode

```c

```

## disassembly

```asm
0x3d2a0  ldarg.1
0x3d2a1  ldstr    aPrivilegeobjec_1// "PrivilegeObjectTypeCodeId"
0x3d2a6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d2ab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d2b0  ldtoken  [mscorlib]System.DBNull
0x3d2b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d2ba  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d2bf  brfalse.s loc_3D2D7
0x3d2c1  ldarg.0
0x3d2c2  ldarg.1
0x3d2c3  ldstr    aPrivilegeobjec_1// "PrivilegeObjectTypeCodeId"
0x3d2c8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d2cd  unbox.any [mscorlib]System.Guid
0x3d2d2  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_PrivilegeObjectTypeCodeId(valuetype [mscorlib]System.Guid value)
0x3d2d7  ldarg.1
0x3d2d8  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3d2dd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d2e2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d2e7  ldtoken  [mscorlib]System.DBNull
0x3d2ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d2f1  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d2f6  brfalse.s loc_3D30E
0x3d2f8  ldarg.0
0x3d2f9  ldarg.1
0x3d2fa  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3d2ff  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d304  unbox.any [mscorlib]System.Guid
0x3d309  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0x3d30e  ldarg.1
0x3d30f  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3d314  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d319  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d31e  ldtoken  [mscorlib]System.DBNull
0x3d323  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d328  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d32d  brfalse.s loc_3D345
0x3d32f  ldarg.0
0x3d330  ldarg.1
0x3d331  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3d336  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d33b  unbox.any [mscorlib]System.Int32
0x3d340  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_ObjectTypeCode(int32 value)
0x3d345  ldarg.0
0x3d346  ldarg.1
0x3d347  ldstr    aIntroducedvers// "IntroducedVersion"
0x3d34c  call     instance bool Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::HasColumn(class [System.Data]System.Data.IDataReader reader, string columnName)
0x3d351  brfalse.s loc_3D38F
0x3d353  ldarg.1
0x3d354  ldstr    aIntroducedvers// "IntroducedVersion"
0x3d359  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d35e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d363  ldtoken  [mscorlib]System.DBNull
0x3d368  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d36d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d372  brfalse.s loc_3D38F
0x3d374  ldarg.0
0x3d375  ldarg.1
0x3d376  ldstr    aIntroducedvers// "IntroducedVersion"
0x3d37b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d380  castclass [mscorlib]System.String
0x3d385  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x3d38a  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3d38f  ret
```
