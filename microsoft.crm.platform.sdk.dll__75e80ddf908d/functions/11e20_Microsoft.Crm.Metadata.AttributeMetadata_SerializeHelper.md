# Microsoft.Crm.Metadata.AttributeMetadata::SerializeHelper

- ea: `0x11e20`
- end: `0x12690`
- name: `Microsoft.Crm.Metadata.AttributeMetadata::SerializeHelper`
- size: `2160`
- prototype: ``
- caller_count: `1`
- callee_count: `73`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x11cb0`

## callees

- `0xbb70`
- `0x10c50`
- `0x10c60`
- `0x10c80`
- `0x10c90`
- `0x10ca0`
- `0x10cc0`
- `0x10cd0`
- `0x10ce0`
- `0x10cf0`
- `0x10d00`
- `0x10d20`
- `0x10d30`
- `0x10d40`
- `0x10d50`
- `0x10d60`
- `0x10d70`
- `0x10d80`
- `0x10d90`
- `0x10da0`
- `0x10dc0`
- `0x10dd0`
- `0x10eb0`
- `0x10ed0`
- `0x10ee0`
- `0x10fa0`
- `0x10fd0`
- `0x10fe0`
- `0x10ff0`
- `0x11000`
- `0x11020`
- `0x11030`
- `0x11050`
- `0x11060`
- `0x11070`
- `0x11080`
- `0x11090`
- `0x110a0`
- `0x11140`
- `0x11150`
- `0x11160`
- `0x11170`
- `0x11180`
- `0x11190`
- `0x111a0`
- `0x111b0`
- `0x111d0`
- `0x111e0`
- `0x111f0`
- `0x11200`

## string_xrefs

- `0x11f8c`: `ValidForCreateApi`
- `0x11fa4`: `ValidForUpdateApi`
- `0x11fbc`: `ValidForReadApi`
- `0x12145`: `XmlAbbreviation`
- `0x12261`: `LinkedAttributeId`
- `0x12302`: `IsIdentity`
- `0x1244f`: `CanBeSecuredForCreate`
- `0x12467`: `CanBeSecuredForRead`
- `0x1247f`: `CanBeSecuredForUpdate`
- `0x124cd`: `ManagedPropertyParentComponentType`
- `0x12541`: `IsRenameable`

## pseudocode

```c

```

## disassembly

```asm
0x11e20  ldarg.1
0x11e21  ldstr    aPhysicalname// "PhysicalName"
0x11e26  ldarg.0
0x11e27  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x11e2c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x11e31  ldarg.0
0x11e32  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11e37  ldarg.0
0x11e38  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x11e3d  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x11e42  ldc.i4.4
0x11e43  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x11e48  brfalse.s loc_11E5B
0x11e4a  ldarg.1
0x11e4b  ldstr    aName// "Name"
0x11e50  ldarg.0
0x11e51  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11e56  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11e5b  ldarg.0
0x11e5c  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x11e61  ldarg.0
0x11e62  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x11e67  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x11e6c  ldc.i4.4
0x11e6d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x11e72  brfalse.s loc_11E85
0x11e74  ldarg.1
0x11e75  ldstr    aLogicalname// "LogicalName"
0x11e7a  ldarg.0
0x11e7b  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x11e80  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11e85  ldarg.0
0x11e86  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x11e8b  brfalse.s loc_11EB2
0x11e8d  ldarg.0
0x11e8e  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x11e93  ldarg.0
0x11e94  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x11e99  ldc.i4.4
0x11e9a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x11e9f  brfalse.s loc_11EB2
0x11ea1  ldarg.1
0x11ea2  ldstr    aTablecolumnnam// "TableColumnName"
0x11ea7  ldarg.0
0x11ea8  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x11ead  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11eb2  ldarg.0
0x11eb3  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_ExternalName()
0x11eb8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11ebd  brtrue.s loc_11ED0
0x11ebf  ldarg.1
0x11ec0  ldstr    aExternalname// "ExternalName"
0x11ec5  ldarg.0
0x11ec6  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_ExternalName()
0x11ecb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11ed0  ldarg.1
0x11ed1  ldstr    aType_0// "Type"
0x11ed6  ldarg.0
0x11ed7  ldfld    class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeMetadata::type
0x11edc  callvirt instance string Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x11ee1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11ee6  ldarg.0
0x11ee7  ldfld    class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeMetadata::type
0x11eec  callvirt instance int32 Microsoft.Crm.Metadata.AttributeTypeInfo::get_Length()
0x11ef1  brtrue.s loc_11F34
0x11ef3  ldarg.0
0x11ef4  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x11ef9  brfalse.s loc_11F34
0x11efb  ldarg.0
0x11efc  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x11f01  ldc.i4.m1
0x11f02  bne.un.s loc_11F16
0x11f04  ldarg.1
0x11f05  ldstr    aLength// "Length"
0x11f0a  ldstr    aMax// "max"
0x11f0f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11f14  br.s     loc_11F34
0x11f16  ldarg.1
0x11f17  ldstr    aLength// "Length"
0x11f1c  ldarg.0
0x11f1d  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x11f22  stloc.0
0x11f23  ldloca.s 0
0x11f25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11f2a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11f2f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11f34  ldarg.0
0x11f35  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_IsNullable()
0x11f3a  brtrue.s loc_11F4C
0x11f3c  ldarg.1
0x11f3d  ldstr    aIsnullable// "IsNullable"
0x11f42  ldstr    a0_0// "0"
0x11f47  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11f4c  ldarg.0
0x11f4d  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_SqlDefaultValue()
0x11f52  brfalse.s loc_11F65
0x11f54  ldarg.1
0x11f55  ldstr    aDefaultvalue// "DefaultValue"
0x11f5a  ldarg.0
0x11f5b  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_SqlDefaultValue()
0x11f60  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11f65  ldarg.0
0x11f66  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_UpgradeDefaultValue()
0x11f6b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11f70  brtrue.s loc_11F83
0x11f72  ldarg.1
0x11f73  ldstr    aUpgradedefault// "UpgradeDefaultValue"
0x11f78  ldarg.0
0x11f79  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_UpgradeDefaultValue()
0x11f7e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11f83  ldarg.0
0x11f84  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x11f89  brfalse.s loc_11F9B
0x11f8b  ldarg.1
0x11f8c  ldstr    aValidforcreate// "ValidForCreateApi"
0x11f91  ldstr    a1_1// "1"
0x11f96  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11f9b  ldarg.0
0x11f9c  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x11fa1  brfalse.s loc_11FB3
0x11fa3  ldarg.1
0x11fa4  ldstr    aValidforupdate// "ValidForUpdateApi"
0x11fa9  ldstr    a1_1// "1"
0x11fae  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11fb3  ldarg.0
0x11fb4  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForRead()
0x11fb9  brfalse.s loc_11FCB
0x11fbb  ldarg.1
0x11fbc  ldstr    aValidforreadap// "ValidForReadApi"
0x11fc1  ldstr    a1_1// "1"
0x11fc6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11fcb  ldarg.0
0x11fcc  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_VisibleToPlatform()
0x11fd1  brtrue.s loc_11FE3
0x11fd3  ldarg.1
0x11fd4  ldstr    aVisibletoplatf// "VisibleToPlatform"
0x11fd9  ldstr    a0_0// "0"
0x11fde  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11fe3  ldarg.0
0x11fe4  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_ReferencedEntityObjectTypeCode()
0x11fe9  brfalse.s loc_12009
0x11feb  ldarg.1
0x11fec  ldstr    aReferencedenti// "ReferencedEntityObjectTypeCode"
0x11ff1  ldarg.0
0x11ff2  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_ReferencedEntityObjectTypeCode()
0x11ff7  stloc.0
0x11ff8  ldloca.s 0
0x11ffa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11fff  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12004  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12009  ldarg.0
0x1200a  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_IsPKAttribute()
0x1200f  brfalse.s loc_12021
0x12011  ldarg.1
0x12012  ldstr    aIspkattribute// "IsPKAttribute"
0x12017  ldstr    a1_1// "1"
0x1201c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12021  ldarg.1
0x12022  ldstr    aAutonumberform// "AutoNumberFormat"
0x12027  ldarg.0
0x12028  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_AutoNumberFormat()
0x1202d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12032  ldarg.0
0x12033  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_IsCustomField()
0x12038  brfalse.s loc_1204A
0x1203a  ldarg.1
0x1203b  ldstr    aIscustomfield// "IsCustomField"
0x12040  ldstr    a1_1// "1"
0x12045  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1204a  ldarg.0
0x1204b  call     instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x12050  brfalse.s loc_12062
0x12052  ldarg.1
0x12053  ldstr    aIslogical// "IsLogical"
0x12058  ldstr    a1_1// "1"
0x1205d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12062  ldarg.2
0x12063  ldc.i4.2
0x12064  and
0x12065  brfalse.s loc_120A5
0x12067  ldarg.1
0x12068  ldstr    aEntityid// "EntityId"
0x1206d  ldarg.0
0x1206e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0x12073  stloc.1
0x12074  ldloca.s 1
0x12076  constrained. [mscorlib]System.Guid
0x1207c  callvirt instance string [mscorlib]System.Object::ToString()
0x12081  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12086  ldarg.1
0x12087  ldstr    aAttributeid// "AttributeId"
0x1208c  ldarg.0
0x1208d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x12092  stloc.1
0x12093  ldloca.s 1
0x12095  constrained. [mscorlib]System.Guid
0x1209b  callvirt instance string [mscorlib]System.Object::ToString()
0x120a0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x120a5  ldarg.1
0x120a6  ldstr    aAttributetypei_0// "AttributeTypeId"
0x120ab  ldarg.0
0x120ac  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_TypeId()
0x120b1  stloc.1
0x120b2  ldloca.s 1
0x120b4  constrained. [mscorlib]System.Guid
0x120ba  callvirt instance string [mscorlib]System.Object::ToString()
0x120bf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x120c4  ldarg.2
0x120c5  ldc.i4.2
0x120c6  and
0x120c7  brfalse.s loc_120E7
0x120c9  ldarg.1
0x120ca  ldstr    aColumnnumber// "ColumnNumber"
0x120cf  ldarg.0
0x120d0  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_ColumnNumber()
0x120d5  stloc.0
0x120d6  ldloca.s 0
0x120d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x120dd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x120e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x120e7  ldarg.0
0x120e8  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x120ed  brfalse.s loc_1210F
0x120ef  ldarg.1
0x120f0  ldstr    aDisplaymask// "DisplayMask"
0x120f5  ldtoken  Microsoft.Crm.Metadata.DisplayMasks
0x120fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x120ff  ldarg.0
0x12100  call     instance int32 Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x12105  call     string Microsoft.Crm.Platform.ConvertHelper::EnumToXmlString(class [mscorlib]System.Type enumType, int32 value)
0x1210a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1210f  ldarg.0
0x12110  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x12115  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1211a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1211f  brfalse.s loc_12179
0x12121  ldarg.0
0x12122  call     instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x12127  ldarg.0
0x12128  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x1212d  callvirt instance class Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(valuetype [mscorlib]System.Guid attributeId)
0x12132  stloc.2
0x12133  ldarg.1
0x12134  ldstr    aAttributeof// "AttributeOf"
0x12139  ldloc.2
0x1213a  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x1213f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12144  ldarg.1
0x12145  ldstr    aXmlabbreviatio_0// "XmlAbbreviation"
0x1214a  ldarg.0
0x1214b  call     instance string Microsoft.Crm.Metadata.AttributeMetadata::get_XmlAbbreviation()
0x12150  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12155  ldarg.2
0x12156  ldc.i4.2
0x12157  and
0x12158  brfalse.s loc_12179
0x1215a  ldarg.1
0x1215b  ldstr    aAttributeofid// "AttributeOfId"
0x12160  ldarg.0
0x12161  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x12166  stloc.1
0x12167  ldloca.s 1
0x12169  constrained. [mscorlib]System.Guid
0x1216f  callvirt instance string [mscorlib]System.Object::ToString()
0x12174  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x12179  ldarg.0
0x1217a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_AggregateOf()
0x1217f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12184  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12189  brfalse.s loc_121D1
0x1218b  ldarg.0
0x1218c  call     instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x12191  ldarg.0
0x12192  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_AggregateOf()
0x12197  callvirt instance class Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(valuetype [mscorlib]System.Guid attributeId)
0x1219c  stloc.3
0x1219d  ldarg.1
0x1219e  ldstr    aAggregateof// "AggregateOf"
0x121a3  ldloc.3
0x121a4  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x121a9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x121ae  ldarg.2
0x121af  ldc.i4.2
0x121b0  and
0x121b1  brfalse.s loc_121D1
0x121b3  ldarg.1
0x121b4  ldstr    aAggregateofid// "AggregateOfId"
0x121b9  ldarg.0
0x121ba  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_AggregateOf()
0x121bf  stloc.1
0x121c0  ldloca.s 1
0x121c2  ldstr    aD_0// "D"
0x121c7  call     instance string [mscorlib]System.Guid::ToString(string)
0x121cc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x121d1  ldarg.0
0x121d2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::get_CalculationOf()
0x121d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x121dc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x121e1  brfalse.s loc_1222B
0x121e3  ldarg.0
  ... truncated ...
```
