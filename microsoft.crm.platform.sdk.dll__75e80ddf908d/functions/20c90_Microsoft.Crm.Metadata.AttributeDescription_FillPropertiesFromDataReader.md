# Microsoft.Crm.Metadata.AttributeDescription::FillPropertiesFromDataReader

- ea: `0x20c90`
- end: `0x220ab`
- name: `Microsoft.Crm.Metadata.AttributeDescription::FillPropertiesFromDataReader`
- size: `5147`
- prototype: ``
- caller_count: `1`
- callee_count: `97`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x24ec0`

## callees

- `0xbc80`
- `0x20c90`
- `0x220b0`
- `0x23150`
- `0x23170`
- `0x23190`
- `0x231b0`
- `0x231d0`
- `0x231f0`
- `0x23210`
- `0x23230`
- `0x23250`
- `0x23270`
- `0x23290`
- `0x232b0`
- `0x232d0`
- `0x232f0`
- `0x23310`
- `0x23330`
- `0x23350`
- `0x23370`
- `0x23390`
- `0x233b0`
- `0x233d0`
- `0x233f0`
- `0x23410`
- `0x23430`
- `0x23450`
- `0x23470`
- `0x23490`
- `0x234b0`
- `0x234d0`
- `0x234f0`
- `0x23510`
- `0x23530`
- `0x23550`
- `0x23570`
- `0x23590`
- `0x235b0`
- `0x235d0`
- `0x235f0`
- `0x23610`
- `0x23630`
- `0x23650`
- `0x23670`
- `0x23690`
- `0x236b0`
- `0x236d0`
- `0x236f0`
- `0x23710`

## string_xrefs

- `0x20dd8`: `XmlAbbreviation`
- `0x20dfa`: `XmlAbbreviation`
- `0x2171a`: `LinkedAttributeId`
- `0x2173c`: `LinkedAttributeId`
- `0x211ed`: `IsIdentity`
- `0x2120f`: `IsIdentity`
- `0x21869`: `CanBeSecuredForCreate`
- `0x2188b`: `CanBeSecuredForCreate`
- `0x218a0`: `CanBeSecuredForRead`
- `0x218c2`: `CanBeSecuredForRead`
- `0x218d7`: `CanBeSecuredForUpdate`
- `0x218f9`: `CanBeSecuredForUpdate`
- `0x21b02`: `ManagedPropertyParentComponentType`
- `0x21b24`: `ManagedPropertyParentComponentType`
- `0x2197c`: `IsRenameable`
- `0x2199e`: `IsRenameable`
- `0x20eb4`: `ValidForUpdateAPI`
- `0x20ed6`: `ValidForUpdateAPI`
- `0x20f22`: `ValidForReadAPI`
- `0x20f44`: `ValidForReadAPI`
- `0x20f59`: `ValidForCreateAPI`
- `0x20f7b`: `ValidForCreateAPI`

## pseudocode

```c

```

## disassembly

```asm
0x20c90  ldarg.0
0x20c91  ldarg.1
0x20c92  ldarg.2
0x20c93  call     instance void Microsoft.Crm.Metadata.VersionedDescription::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0x20c98  ldarg.0
0x20c99  ldarg.1
0x20c9a  ldstr    aAttributeid// "AttributeId"
0x20c9f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ca4  unbox.any [mscorlib]System.Guid
0x20ca9  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x20cae  ldarg.0
0x20caf  ldarg.1
0x20cb0  ldstr    aAttributetypei_0// "AttributeTypeId"
0x20cb5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20cba  unbox.any [mscorlib]System.Guid
0x20cbf  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_AttributeTypeId(valuetype [mscorlib]System.Guid value)
0x20cc4  ldarg.1
0x20cc5  ldstr    aName// "Name"
0x20cca  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ccf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20cd4  ldtoken  [mscorlib]System.DBNull
0x20cd9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20cde  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20ce3  brfalse.s loc_20CFB
0x20ce5  ldarg.0
0x20ce6  ldarg.1
0x20ce7  ldstr    aName// "Name"
0x20cec  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20cf1  castclass [mscorlib]System.String
0x20cf6  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_Name(string value)
0x20cfb  ldarg.1
0x20cfc  ldstr    aPhysicalname// "PhysicalName"
0x20d01  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20d06  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20d0b  ldtoken  [mscorlib]System.DBNull
0x20d10  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20d15  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20d1a  brfalse.s loc_20D32
0x20d1c  ldarg.0
0x20d1d  ldarg.1
0x20d1e  ldstr    aPhysicalname// "PhysicalName"
0x20d23  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20d28  castclass [mscorlib]System.String
0x20d2d  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_PhysicalName(string value)
0x20d32  ldarg.1
0x20d33  ldstr    aTablecolumnnam// "TableColumnName"
0x20d38  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20d3d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20d42  ldtoken  [mscorlib]System.DBNull
0x20d47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20d4c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20d51  brfalse.s loc_20D69
0x20d53  ldarg.0
0x20d54  ldarg.1
0x20d55  ldstr    aTablecolumnnam// "TableColumnName"
0x20d5a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20d5f  castclass [mscorlib]System.String
0x20d64  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_TableColumnName(string value)
0x20d69  ldarg.1
0x20d6a  ldstr    aLength// "Length"
0x20d6f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20d74  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20d79  ldtoken  [mscorlib]System.DBNull
0x20d7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20d83  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20d88  brfalse.s loc_20DA0
0x20d8a  ldarg.0
0x20d8b  ldarg.1
0x20d8c  ldstr    aLength// "Length"
0x20d91  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20d96  unbox.any [mscorlib]System.Int32
0x20d9b  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32 value)
0x20da0  ldarg.1
0x20da1  ldstr    aIsnullable// "IsNullable"
0x20da6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20dab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20db0  ldtoken  [mscorlib]System.DBNull
0x20db5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20dba  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20dbf  brfalse.s loc_20DD7
0x20dc1  ldarg.0
0x20dc2  ldarg.1
0x20dc3  ldstr    aIsnullable// "IsNullable"
0x20dc8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20dcd  unbox.any [mscorlib]System.Boolean
0x20dd2  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsNullable(bool value)
0x20dd7  ldarg.1
0x20dd8  ldstr    aXmlabbreviatio_0// "XmlAbbreviation"
0x20ddd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20de2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20de7  ldtoken  [mscorlib]System.DBNull
0x20dec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20df1  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20df6  brfalse.s loc_20E0E
0x20df8  ldarg.0
0x20df9  ldarg.1
0x20dfa  ldstr    aXmlabbreviatio_0// "XmlAbbreviation"
0x20dff  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20e04  castclass [mscorlib]System.String
0x20e09  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string value)
0x20e0e  ldarg.1
0x20e0f  ldstr    aEntityid// "EntityId"
0x20e14  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20e19  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20e1e  ldtoken  [mscorlib]System.DBNull
0x20e23  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20e28  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20e2d  brfalse.s loc_20E45
0x20e2f  ldarg.0
0x20e30  ldarg.1
0x20e31  ldstr    aEntityid// "EntityId"
0x20e36  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20e3b  unbox.any [mscorlib]System.Guid
0x20e40  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_EntityId(valuetype [mscorlib]System.Guid value)
0x20e45  ldarg.1
0x20e46  ldstr    aDefaultvalue// "DefaultValue"
0x20e4b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20e50  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20e55  ldtoken  [mscorlib]System.DBNull
0x20e5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20e5f  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20e64  brfalse.s loc_20E7C
0x20e66  ldarg.0
0x20e67  ldarg.1
0x20e68  ldstr    aDefaultvalue// "DefaultValue"
0x20e6d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20e72  castclass [mscorlib]System.String
0x20e77  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_DefaultValue(string value)
0x20e7c  ldarg.1
0x20e7d  ldstr    aColumnnumber// "ColumnNumber"
0x20e82  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20e87  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20e8c  ldtoken  [mscorlib]System.DBNull
0x20e91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20e96  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20e9b  brfalse.s loc_20EB3
0x20e9d  ldarg.0
0x20e9e  ldarg.1
0x20e9f  ldstr    aColumnnumber// "ColumnNumber"
0x20ea4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ea9  unbox.any [mscorlib]System.Int32
0x20eae  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ColumnNumber(int32 value)
0x20eb3  ldarg.1
0x20eb4  ldstr    aValidforupdate_0// "ValidForUpdateAPI"
0x20eb9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ebe  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20ec3  ldtoken  [mscorlib]System.DBNull
0x20ec8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20ecd  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20ed2  brfalse.s loc_20EEA
0x20ed4  ldarg.0
0x20ed5  ldarg.1
0x20ed6  ldstr    aValidforupdate_0// "ValidForUpdateAPI"
0x20edb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ee0  unbox.any [mscorlib]System.Boolean
0x20ee5  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ValidForUpdateApi(bool value)
0x20eea  ldarg.1
0x20eeb  ldstr    aLogicalname// "LogicalName"
0x20ef0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ef5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20efa  ldtoken  [mscorlib]System.DBNull
0x20eff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20f04  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20f09  brfalse.s loc_20F21
0x20f0b  ldarg.0
0x20f0c  ldarg.1
0x20f0d  ldstr    aLogicalname// "LogicalName"
0x20f12  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20f17  castclass [mscorlib]System.String
0x20f1c  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_LogicalName(string value)
0x20f21  ldarg.1
0x20f22  ldstr    aValidforreadap_0// "ValidForReadAPI"
0x20f27  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20f2c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20f31  ldtoken  [mscorlib]System.DBNull
0x20f36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20f3b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20f40  brfalse.s loc_20F58
0x20f42  ldarg.0
0x20f43  ldarg.1
0x20f44  ldstr    aValidforreadap_0// "ValidForReadAPI"
0x20f49  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20f4e  unbox.any [mscorlib]System.Boolean
0x20f53  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ValidForReadApi(bool value)
0x20f58  ldarg.1
0x20f59  ldstr    aValidforcreate_0// "ValidForCreateAPI"
0x20f5e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20f63  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20f68  ldtoken  [mscorlib]System.DBNull
0x20f6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20f72  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20f77  brfalse.s loc_20F8F
0x20f79  ldarg.0
0x20f7a  ldarg.1
0x20f7b  ldstr    aValidforcreate_0// "ValidForCreateAPI"
0x20f80  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20f85  unbox.any [mscorlib]System.Boolean
0x20f8a  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ValidForCreateApi(bool value)
0x20f8f  ldarg.1
0x20f90  ldstr    aVisibletoplatf// "VisibleToPlatform"
0x20f95  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20f9a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20f9f  ldtoken  [mscorlib]System.DBNull
0x20fa4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20fa9  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20fae  brfalse.s loc_20FC6
0x20fb0  ldarg.0
0x20fb1  ldarg.1
0x20fb2  ldstr    aVisibletoplatf// "VisibleToPlatform"
0x20fb7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20fbc  unbox.any [mscorlib]System.Boolean
0x20fc1  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_VisibleToPlatform(bool value)
0x20fc6  ldarg.1
0x20fc7  ldstr    aIspkattribute// "IsPKAttribute"
0x20fcc  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20fd1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20fd6  ldtoken  [mscorlib]System.DBNull
0x20fdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20fe0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20fe5  brfalse.s loc_20FFD
0x20fe7  ldarg.0
0x20fe8  ldarg.1
0x20fe9  ldstr    aIspkattribute// "IsPKAttribute"
0x20fee  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x20ff3  unbox.any [mscorlib]System.Boolean
0x20ff8  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsPKAttribute(bool value)
0x20ffd  ldarg.1
0x20ffe  ldstr    aIscustomfield// "IsCustomField"
0x21003  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x21008  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2100d  ldtoken  [mscorlib]System.DBNull
0x21012  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21017  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2101c  brfalse.s loc_21034
0x2101e  ldarg.0
0x2101f  ldarg.1
0x21020  ldstr    aIscustomfield// "IsCustomField"
0x21025  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2102a  unbox.any [mscorlib]System.Boolean
0x2102f  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool value)
0x21034  ldarg.1
0x21035  ldstr    aIslogical// "IsLogical"
0x2103a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2103f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x21044  ldtoken  [mscorlib]System.DBNull
0x21049  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2104e  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x21053  brfalse.s loc_2106B
0x21055  ldarg.0
0x21056  ldarg.1
0x21057  ldstr    aIslogical// "IsLogical"
0x2105c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x21061  unbox.any [mscorlib]System.Boolean
0x21066  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool value)
0x2106b  ldarg.1
0x2106c  ldstr    aDisplaymask// "DisplayMask"
0x21071  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x21076  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2107b  ldtoken  [mscorlib]System.DBNull
0x21080  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21085  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2108a  brfalse.s loc_210A2
0x2108c  ldarg.0
0x2108d  ldarg.1
0x2108e  ldstr    aDisplaymask// "DisplayMask"
0x21093  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x21098  unbox.any [mscorlib]System.Int32
0x2109d  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32 value)
0x210a2  ldarg.1
0x210a3  ldstr    aAttributeof// "AttributeOf"
0x210a8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x210ad  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x210b2  ldtoken  [mscorlib]System.DBNull
0x210b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x210bc  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x210c1  brfalse.s loc_210D9
0x210c3  ldarg.0
0x210c4  ldarg.1
0x210c5  ldstr    aAttributeof// "AttributeOf"
0x210ca  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x210cf  unbox.any [mscorlib]System.Guid
0x210d4  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_AttributeOf(valuetype [mscorlib]System.Guid value)
0x210d9  ldarg.1
0x210da  ldstr    aReferencedenti// "ReferencedEntityObjectTypeCode"
0x210df  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x210e4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x210e9  ldtoken  [mscorlib]System.DBNull
0x210ee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x210f3  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x210f8  brfalse.s loc_21110
0x210fa  ldarg.0
0x210fb  ldarg.1
0x210fc  ldstr    aReferencedenti// "ReferencedEntityObjectTypeCode"
0x21101  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x21106  unbox.any [mscorlib]System.Int32
0x2110b  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ReferencedEntityObjectTypeCode(int32 value)
0x21110  ldarg.1
0x21111  ldstr    aAggregateof// "AggregateOf"
0x21116  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2111b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
  ... truncated ...
```
