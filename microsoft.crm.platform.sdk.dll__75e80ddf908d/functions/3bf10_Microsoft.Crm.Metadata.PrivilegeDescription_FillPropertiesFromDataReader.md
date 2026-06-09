# Microsoft.Crm.Metadata.PrivilegeDescription::FillPropertiesFromDataReader

- ea: `0x3bf10`
- end: `0x3c1ae`
- name: `Microsoft.Crm.Metadata.PrivilegeDescription::FillPropertiesFromDataReader`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3cb90`

## callees

- `0xbc80`
- `0x3bf10`
- `0x3c1b0`
- `0x3c680`
- `0x3c6a0`
- `0x3c6c0`
- `0x3c6e0`
- `0x3c700`
- `0x3c720`
- `0x3c740`
- `0x3c760`
- `0x3c780`
- `0x3c7e0`
- `0x3c820`

## string_xrefs

- `0x3bf11`: `PrivilegeId`
- `0x3bf33`: `PrivilegeId`
- `0x3c05b`: `AccessRight`
- `0x3c07d`: `AccessRight`

## pseudocode

```c

```

## disassembly

```asm
0x3bf10  ldarg.1
0x3bf11  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3bf16  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bf1b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3bf20  ldtoken  [mscorlib]System.DBNull
0x3bf25  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bf2a  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3bf2f  brfalse.s loc_3BF47
0x3bf31  ldarg.0
0x3bf32  ldarg.1
0x3bf33  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3bf38  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bf3d  unbox.any [mscorlib]System.Guid
0x3bf42  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0x3bf47  ldarg.1
0x3bf48  ldstr    aName// "Name"
0x3bf4d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bf52  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3bf57  ldtoken  [mscorlib]System.DBNull
0x3bf5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bf61  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3bf66  brfalse.s loc_3BF7E
0x3bf68  ldarg.0
0x3bf69  ldarg.1
0x3bf6a  ldstr    aName// "Name"
0x3bf6f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bf74  castclass [mscorlib]System.String
0x3bf79  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_Name(string value)
0x3bf7e  ldarg.1
0x3bf7f  ldstr    aCanbebasic// "CanBeBasic"
0x3bf84  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bf89  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3bf8e  ldtoken  [mscorlib]System.DBNull
0x3bf93  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bf98  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3bf9d  brfalse.s loc_3BFB5
0x3bf9f  ldarg.0
0x3bfa0  ldarg.1
0x3bfa1  ldstr    aCanbebasic// "CanBeBasic"
0x3bfa6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bfab  unbox.any [mscorlib]System.Boolean
0x3bfb0  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeBasic(bool value)
0x3bfb5  ldarg.1
0x3bfb6  ldstr    aCanbelocal// "CanBeLocal"
0x3bfbb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bfc0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3bfc5  ldtoken  [mscorlib]System.DBNull
0x3bfca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bfcf  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3bfd4  brfalse.s loc_3BFEC
0x3bfd6  ldarg.0
0x3bfd7  ldarg.1
0x3bfd8  ldstr    aCanbelocal// "CanBeLocal"
0x3bfdd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bfe2  unbox.any [mscorlib]System.Boolean
0x3bfe7  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeLocal(bool value)
0x3bfec  ldarg.1
0x3bfed  ldstr    aCanbedeep// "CanBeDeep"
0x3bff2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3bff7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3bffc  ldtoken  [mscorlib]System.DBNull
0x3c001  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c006  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c00b  brfalse.s loc_3C023
0x3c00d  ldarg.0
0x3c00e  ldarg.1
0x3c00f  ldstr    aCanbedeep// "CanBeDeep"
0x3c014  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c019  unbox.any [mscorlib]System.Boolean
0x3c01e  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeDeep(bool value)
0x3c023  ldarg.1
0x3c024  ldstr    aCanbeglobal// "CanBeGlobal"
0x3c029  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c02e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c033  ldtoken  [mscorlib]System.DBNull
0x3c038  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c03d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c042  brfalse.s loc_3C05A
0x3c044  ldarg.0
0x3c045  ldarg.1
0x3c046  ldstr    aCanbeglobal// "CanBeGlobal"
0x3c04b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c050  unbox.any [mscorlib]System.Boolean
0x3c055  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeGlobal(bool value)
0x3c05a  ldarg.1
0x3c05b  ldstr    aAccessright// "AccessRight"
0x3c060  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c065  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c06a  ldtoken  [mscorlib]System.DBNull
0x3c06f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c074  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c079  brfalse.s loc_3C091
0x3c07b  ldarg.0
0x3c07c  ldarg.1
0x3c07d  ldstr    aAccessright// "AccessRight"
0x3c082  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c087  unbox.any [mscorlib]System.Int32
0x3c08c  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_AccessRight(int32 value)
0x3c091  ldarg.0
0x3c092  ldarg.1
0x3c093  ldstr    aCanbeentityref// "CanBeEntityReference"
0x3c098  call     instance bool Microsoft.Crm.Metadata.PrivilegeDescription::HasColumn(class [System.Data]System.Data.IDataReader reader, string columnName)
0x3c09d  brfalse.s loc_3C0D6
0x3c09f  ldarg.1
0x3c0a0  ldstr    aCanbeentityref// "CanBeEntityReference"
0x3c0a5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c0aa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c0af  ldtoken  [mscorlib]System.DBNull
0x3c0b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c0b9  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c0be  brfalse.s loc_3C0D6
0x3c0c0  ldarg.0
0x3c0c1  ldarg.1
0x3c0c2  ldstr    aCanbeentityref// "CanBeEntityReference"
0x3c0c7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c0cc  unbox.any [mscorlib]System.Boolean
0x3c0d1  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeEntityReference(bool value)
0x3c0d6  ldarg.0
0x3c0d7  ldarg.1
0x3c0d8  ldstr    aCanbeparentent// "CanBeParentEntityReference"
0x3c0dd  call     instance bool Microsoft.Crm.Metadata.PrivilegeDescription::HasColumn(class [System.Data]System.Data.IDataReader reader, string columnName)
0x3c0e2  brfalse.s loc_3C11B
0x3c0e4  ldarg.1
0x3c0e5  ldstr    aCanbeparentent// "CanBeParentEntityReference"
0x3c0ea  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c0ef  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c0f4  ldtoken  [mscorlib]System.DBNull
0x3c0f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c0fe  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c103  brfalse.s loc_3C11B
0x3c105  ldarg.0
0x3c106  ldarg.1
0x3c107  ldstr    aCanbeparentent// "CanBeParentEntityReference"
0x3c10c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c111  unbox.any [mscorlib]System.Boolean
0x3c116  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeParentEntityReference(bool value)
0x3c11b  ldarg.0
0x3c11c  ldarg.1
0x3c11d  ldstr    aIntroducedvers// "IntroducedVersion"
0x3c122  call     instance bool Microsoft.Crm.Metadata.PrivilegeDescription::HasColumn(class [System.Data]System.Data.IDataReader reader, string columnName)
0x3c127  brfalse.s loc_3C165
0x3c129  ldarg.1
0x3c12a  ldstr    aIntroducedvers// "IntroducedVersion"
0x3c12f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c134  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c139  ldtoken  [mscorlib]System.DBNull
0x3c13e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c143  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c148  brfalse.s loc_3C165
0x3c14a  ldarg.0
0x3c14b  ldarg.1
0x3c14c  ldstr    aIntroducedvers// "IntroducedVersion"
0x3c151  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c156  castclass [mscorlib]System.String
0x3c15b  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x3c160  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3c165  ldarg.0
0x3c166  ldarg.1
0x3c167  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3c16c  call     instance bool Microsoft.Crm.Metadata.PrivilegeDescription::HasColumn(class [System.Data]System.Data.IDataReader reader, string columnName)
0x3c171  brfalse.s loc_3C1AD
0x3c173  ldarg.0
0x3c174  ldarg.1
0x3c175  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3c17a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c17f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c184  ldtoken  [mscorlib]System.DBNull
0x3c189  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c18e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c193  brtrue.s loc_3C1A7
0x3c195  ldarg.1
0x3c196  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3c19b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3c1a0  unbox.any [mscorlib]System.Int32
0x3c1a5  br.s     loc_3C1A8
0x3c1a7  ldc.i4.0
0x3c1a8  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_ObjectTypeCode(int32 value)
0x3c1ad  ret
```
