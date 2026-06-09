# Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::LoadAttributeDescription

- ea: `0x76f90`
- end: `0x77160`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::LoadAttributeDescription`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x76f50`

## callees

- `0x71970`
- `0x76f90`
- `0x771e0`
- `0x77200`
- `0x77220`
- `0x77230`

## string_xrefs

- `0x76fd7`: `ValidForUpdate`
- `0x7704f`: `IsValidForInheritanceCopying`
- `0x770f3`: `FilterTypeForBackCompatSupport`

## pseudocode

```c

```

## disassembly

```asm
0x76f90  ldarg.0
0x76f91  brfalse.s loc_76F9B
0x76f93  ldarg.0
0x76f94  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x76f99  brtrue.s loc_76F9D
0x76f9b  ldnull
0x76f9c  ret
0x76f9d  ldarg.0
0x76f9e  ldstr    aName// "Name"
0x76fa3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76fa8  stloc.0
0x76fa9  ldloc.0
0x76faa  call     string Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetStringFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76faf  stloc.1
0x76fb0  ldarg.0
0x76fb1  ldstr    aPhysicalname// "PhysicalName"
0x76fb6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76fbb  stloc.0
0x76fbc  ldloc.0
0x76fbd  call     string Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetStringFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76fc2  stloc.2
0x76fc3  ldarg.0
0x76fc4  ldstr    aExternalname// "ExternalName"
0x76fc9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76fce  stloc.0
0x76fcf  ldloc.0
0x76fd0  call     string Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetStringFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76fd5  stloc.3
0x76fd6  ldarg.0
0x76fd7  ldstr    aValidforupdate_2// "ValidForUpdate"
0x76fdc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76fe1  stloc.0
0x76fe2  ldloc.0
0x76fe3  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76fe8  stloc.s  4
0x76fea  ldarg.0
0x76feb  ldstr    aIsnullable// "IsNullable"
0x76ff0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76ff5  stloc.0
0x76ff6  ldloc.0
0x76ff7  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76ffc  stloc.s  5
0x76ffe  ldarg.0
0x76fff  ldstr    aIsprimaryidfie// "IsPrimaryIdField"
0x77004  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x77009  stloc.0
0x7700a  ldloc.0
0x7700b  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x77010  stloc.s  6
0x77012  ldarg.0
0x77013  ldstr    aIsprimarykeyfi// "IsPrimaryKeyField"
0x77018  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7701d  stloc.0
0x7701e  ldloc.0
0x7701f  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x77024  stloc.s  7
0x77026  ldarg.0
0x77027  ldstr    aIslogicalident// "IsLogicalIdentityField"
0x7702c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x77031  stloc.0
0x77032  ldloc.0
0x77033  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x77038  stloc.s  8
0x7703a  ldarg.0
0x7703b  ldstr    aIsrowidfield// "IsRowIdField"
0x77040  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x77045  stloc.0
0x77046  ldloc.0
0x77047  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x7704c  stloc.s  9
0x7704e  ldarg.0
0x7704f  ldstr    aIsvalidforinhe// "IsValidForInheritanceCopying"
0x77054  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x77059  stloc.0
0x7705a  ldloc.0
0x7705b  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x77060  stloc.s  0xA
0x77062  ldarg.0
0x77063  ldstr    aAttributetype// "AttributeType"
0x77068  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7706d  stloc.0
0x7706e  ldloc.0
0x7706f  brtrue.s loc_77074
0x77071  ldc.i4.0
0x77072  br.s     loc_7708E
0x77074  ldtoken  Microsoft.Crm.Metadata.MetadataAttributeType
0x77079  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7707e  ldloc.0
0x7707f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x77084  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x77089  unbox.any Microsoft.Crm.Metadata.MetadataAttributeType
0x7708e  stloc.s  0xB
0x77090  ldarg.0
0x77091  ldstr    aIsunmanagedatt// "IsUnmanagedAttribute"
0x77096  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7709b  stloc.0
0x7709c  ldloc.0
0x7709d  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x770a2  stloc.s  0xC
0x770a4  ldarg.0
0x770a5  ldstr    aIsonewayboolea// "IsOneWayBooleanAttribute"
0x770aa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x770af  stloc.0
0x770b0  ldloc.0
0x770b1  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x770b6  stloc.s  0xD
0x770b8  ldarg.0
0x770b9  ldstr    aIssolutionrela// "IsSolutionRelatedAttribute"
0x770be  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x770c3  stloc.0
0x770c4  ldloc.0
0x770c5  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x770ca  stloc.s  0xE
0x770cc  ldarg.0
0x770cd  ldstr    aColumnnumber// "ColumnNumber"
0x770d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x770d7  stloc.0
0x770d8  ldloc.0
0x770d9  call     int32 Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetInt32FromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x770de  ldarg.0
0x770df  ldstr    aValidforinsert// "ValidForInsert"
0x770e4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x770e9  stloc.0
0x770ea  ldloc.0
0x770eb  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x770f0  stloc.s  0xF
0x770f2  ldarg.0
0x770f3  ldstr    aFiltertypeforb// "FilterTypeForBackCompatSupport"
0x770f8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x770fd  stloc.0
0x770fe  ldloc.0
0x770ff  brtrue.s loc_77104
0x77101  ldnull
0x77102  br.s     loc_7710F
0x77104  ldloc.0
0x77105  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7710a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x7710f  stloc.s  0x10
0x77111  ldarg.0
0x77112  ldstr    aDonotserialize// "DoNotSerializeToOutlook"
0x77117  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7711c  stloc.0
0x7711d  ldloc.0
0x7711e  call     bool Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x77123  stloc.s  0x11
0x77125  ldarg.0
0x77126  ldstr    aIntroducedvers// "IntroducedVersion"
0x7712b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x77130  stloc.0
0x77131  ldloc.0
0x77132  call     class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetVersionFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x77137  stloc.s  0x12
0x77139  ldloc.2
0x7713a  ldloc.1
0x7713b  ldloc.s  4
0x7713d  ldloc.s  5
0x7713f  ldloc.s  6
0x77141  ldloc.s  7
0x77143  ldloc.s  8
0x77145  ldloc.s  0xA
0x77147  ldloc.s  9
0x77149  ldloc.s  0xB
0x7714b  ldloc.s  0x12
0x7714d  ldloc.s  0xC
0x7714f  ldloc.s  0xD
0x77151  ldloc.s  0xE
0x77153  ldloc.s  0xF
0x77155  ldloc.s  0x10
0x77157  ldloc.s  0x11
0x77159  ldloc.3
0x7715a  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7715f  ret
```
