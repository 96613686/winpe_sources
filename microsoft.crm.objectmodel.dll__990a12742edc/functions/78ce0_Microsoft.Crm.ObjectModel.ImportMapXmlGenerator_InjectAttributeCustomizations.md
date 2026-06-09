# Microsoft.Crm.ObjectModel.ImportMapXmlGenerator::InjectAttributeCustomizations

- ea: `0x78ce0`
- end: `0x79029`
- name: `Microsoft.Crm.ObjectModel.ImportMapXmlGenerator::InjectAttributeCustomizations`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x788e0`

## callees

- `0x78ce0`
- `0x79030`
- `0x791d0`
- `0x79560`
- `0x79630`
- `0x7b230`

## string_xrefs

- `0x78ce1`: `/ImportCustomizations/Attributes/CustomAttribute/CreateAttributeCustomizationXml/Attribute`
- `0x78d2e`: `CustomizationXml/attribute/ShortLogicalName`
- `0x78dd0`: `" and @ProcessCode="Create"]`
- `0x78dfe`: `" and @ProcessCode="Create"]/AttributeMaps/AttributeMap[TargetAttributeRef = "`
- `0x78e0f`: `" and ProcessCode ="Create"]`
- `0x78fc8`: `" and ProcessCode ="Create"]`
- `0x78e45`: `CustomizationXml[@inject="false"]`
- `0x78e5a`: `CreateAttributeMapping/AttributeMap/SourceAttributeName`
- `0x78e7d`: `' and @ProcessCode='Create']/AttributeMaps/AttributeMap[ProcessCode ='Unmapped']`

## pseudocode

```c

```

## disassembly

```asm
0x78ce0  ldarg.1
0x78ce1  ldstr    aImportcustomiz_0// "/ImportCustomizations/Attributes/Custom"...
0x78ce6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x78ceb  stloc.0
0x78cec  ldloc.0
0x78ced  brfalse  loc_7901B
0x78cf2  ldloc.0
0x78cf3  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x78cf8  ldc.i4.0
0x78cf9  ble      loc_7901B
0x78cfe  ldloc.0
0x78cff  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x78d04  stloc.1
0x78d05  br       loc_78FFA
0x78d0a  ldloc.1
0x78d0b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x78d10  castclass [System.Xml]System.Xml.XmlNode
0x78d15  stloc.2
0x78d16  ldloc.2
0x78d17  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x78d1c  ldstr    aId_0// "Id"
0x78d21  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x78d26  stloc.3
0x78d27  ldloc.3
0x78d28  brfalse  loc_78FFA
0x78d2d  ldloc.2
0x78d2e  ldstr    aCustomizationx_0// "CustomizationXml/attribute/ShortLogical"...
0x78d33  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78d38  stloc.s  4
0x78d3a  ldloc.s  4
0x78d3c  brfalse  loc_78FFA
0x78d41  ldloc.s  4
0x78d43  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x78d48  stloc.s  5
0x78d4a  ldarg.3
0x78d4b  ldloc.s  5
0x78d4d  call     string [mscorlib]System.String::Concat(string, string)
0x78d52  stloc.s  6
0x78d54  ldloc.2
0x78d55  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78d5a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78d5f  ldstr    aExistingentity_0// "ExistingEntityLogicalName"
0x78d64  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78d69  stloc.s  7
0x78d6b  ldsfld   string [mscorlib]System.String::Empty
0x78d70  stloc.s  8
0x78d72  ldloc.s  7
0x78d74  brfalse.s loc_78D7F
0x78d76  ldloc.s  7
0x78d78  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x78d7d  stloc.s  8
0x78d7f  ldloc.2
0x78d80  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78d85  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78d8a  ldstr    aCustomentityid// "CustomEntityId"
0x78d8f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78d94  stloc.s  9
0x78d96  ldsfld   string [mscorlib]System.String::Empty
0x78d9b  stloc.s  0xA
0x78d9d  ldloc.s  9
0x78d9f  brfalse.s loc_78DAA
0x78da1  ldloc.s  9
0x78da3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x78da8  stloc.s  0xA
0x78daa  ldarg.0
0x78dab  ldloc.s  8
0x78dad  ldloc.s  6
0x78daf  ldarg.3
0x78db0  ldarg.s  6
0x78db2  call     instance bool Microsoft.Crm.ObjectModel.ImportMapXmlGenerator::CheckIfAttributePresent(string targetEntityName, string targetAttributeName, string metadataPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x78db7  brtrue   loc_78FEE
0x78dbc  ldnull
0x78dbd  stloc.s  0xB
0x78dbf  ldloc.s  0xA
0x78dc1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x78dc6  brtrue.s loc_78DE1
0x78dc8  ldarg.2
0x78dc9  ldstr    aMapEntitymapsE_18// "/Map/EntityMaps/EntityMap[@TargetEntity"...
0x78dce  ldloc.s  0xA
0x78dd0  ldstr    aAndProcesscode_1// "\" and @ProcessCode=\"Create\"]"
0x78dd5  call     string [mscorlib]System.String::Concat(string, string, string)
0x78dda  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78ddf  stloc.s  0xB
0x78de1  ldloc.s  0xB
0x78de3  brfalse  loc_78F6D
0x78de8  ldarg.2
0x78de9  ldc.i4.5
0x78dea  newarr   [mscorlib]System.String
0x78def  dup
0x78df0  ldc.i4.0
0x78df1  ldstr    aMapEntitymapsE_18// "/Map/EntityMaps/EntityMap[@TargetEntity"...
0x78df6  stelem.ref
0x78df7  dup
0x78df8  ldc.i4.1
0x78df9  ldloc.s  0xA
0x78dfb  stelem.ref
0x78dfc  dup
0x78dfd  ldc.i4.2
0x78dfe  ldstr    aAndProcesscode_2// "\" and @ProcessCode=\"Create\"]/Attribu"...
0x78e03  stelem.ref
0x78e04  dup
0x78e05  ldc.i4.3
0x78e06  ldloc.3
0x78e07  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x78e0c  stelem.ref
0x78e0d  dup
0x78e0e  ldc.i4.4
0x78e0f  ldstr    aAndProcesscode_3// "\" and ProcessCode =\"Create\"]"
0x78e14  stelem.ref
0x78e15  call     string [mscorlib]System.String::Concat(string[])
0x78e1a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78e1f  brtrue   loc_78FFA
0x78e24  ldarg.s  4
0x78e26  brfalse  loc_78FFA
0x78e2b  ldarg.2
0x78e2c  ldstr    aMapCustomizati_1// "/Map/Customizations/Entities/Entity[@Id"...
0x78e31  ldloc.s  0xA
0x78e33  ldstr    asc_258D6E// "\"]"
0x78e38  call     string [mscorlib]System.String::Concat(string, string, string)
0x78e3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78e42  stloc.s  0xC
0x78e44  ldloc.2
0x78e45  ldstr    aCustomizationx_1// "CustomizationXml[@inject=\"false\"]"
0x78e4a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78e4f  ldloc.2
0x78e50  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78e55  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78e5a  ldstr    aCreateattribut// "CreateAttributeMapping/AttributeMap/Sou"...
0x78e5f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78e64  stloc.s  0xD
0x78e66  ldnull
0x78e67  stloc.s  0xE
0x78e69  ldloc.s  0xD
0x78e6b  brfalse.s loc_78EA0
0x78e6d  ldloc.s  0xD
0x78e6f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x78e74  stloc.s  0xF
0x78e76  ldstr    aMapEntitymapsE_19// "/Map/EntityMaps/EntityMap[@TargetEntity"...
0x78e7b  ldloc.s  0xA
0x78e7d  ldstr    aAndProcesscode_4// "' and @ProcessCode='Create']/AttributeM"...
0x78e82  call     string [mscorlib]System.String::Concat(string, string, string)
0x78e87  stloc.s  0x10
0x78e89  ldarg.2
0x78e8a  ldloc.s  0x10
0x78e8c  ldstr    aSourceattribut_0// "SourceAttributeName"
0x78e91  ldloc.s  0xF
0x78e93  ldc.i4.0
0x78e94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x78e99  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.ObjectModel.XPathHelper::SelectSingleNode(class [System.Xml]System.Xml.XmlNode xmlNode, string initialXPath, string name, string value, valuetype XPathCondition condition, class [mscorlib]System.Globalization.CultureInfo culture)
0x78e9e  stloc.s  0xE
0x78ea0  brtrue.s loc_78EED
0x78ea2  ldloc.s  0xC
0x78ea4  brfalse.s loc_78EED
0x78ea6  ldloc.s  0xE
0x78ea8  brfalse.s loc_78EED
0x78eaa  ldloc.s  0xC
0x78eac  ldstr    aAttributes_1// "Attributes"
0x78eb1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78eb6  stloc.s  0x11
0x78eb8  ldloc.s  0x11
0x78eba  brtrue.s loc_78ED9
0x78ebc  ldarg.2
0x78ebd  ldc.i4.1
0x78ebe  ldstr    aAttributes_1// "Attributes"
0x78ec3  ldsfld   string [mscorlib]System.String::Empty
0x78ec8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x78ecd  stloc.s  0x11
0x78ecf  ldloc.s  0xC
0x78ed1  ldloc.s  0x11
0x78ed3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78ed8  pop
0x78ed9  ldarg.2
0x78eda  ldloc.2
0x78edb  ldc.i4.1
0x78edc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x78ee1  stloc.s  0x12
0x78ee3  ldloc.s  0x11
0x78ee5  ldloc.s  0x12
0x78ee7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78eec  pop
0x78eed  ldloc.s  0xC
0x78eef  brfalse  loc_78FFA
0x78ef4  ldloc.s  0xE
0x78ef6  brfalse  loc_78FFA
0x78efb  ldloc.2
0x78efc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78f01  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_NextSibling()
0x78f06  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x78f0b  stloc.s  0x13
0x78f0d  ldarg.2
0x78f0e  ldloc.s  0x13
0x78f10  ldc.i4.1
0x78f11  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x78f16  stloc.s  0x14
0x78f18  ldloc.s  0xB
0x78f1a  ldstr    aAttributemaps// "AttributeMaps"
0x78f1f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78f24  stloc.s  0x15
0x78f26  ldloc.s  0x15
0x78f28  brtrue.s loc_78F47
0x78f2a  ldarg.2
0x78f2b  ldc.i4.1
0x78f2c  ldstr    aAttributemaps// "AttributeMaps"
0x78f31  ldsfld   string [mscorlib]System.String::Empty
0x78f36  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x78f3b  stloc.s  0x15
0x78f3d  ldloc.s  0xB
0x78f3f  ldloc.s  0x15
0x78f41  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78f46  pop
0x78f47  ldloc.s  0x15
0x78f49  ldloc.s  0x14
0x78f4b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78f50  pop
0x78f51  ldarg.0
0x78f52  ldarga.s 2
0x78f54  call     instance void Microsoft.Crm.ObjectModel.ImportMapXmlGenerator::MarkMapAsInjected(class [System.Xml]System.Xml.XmlDocument& doc)
0x78f59  ldloc.s  0xE
0x78f5b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x78f60  ldloc.s  0xE
0x78f62  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x78f67  pop
0x78f68  br       loc_78FFA
0x78f6d  ldnull
0x78f6e  stloc.s  0x16
0x78f70  ldloc.s  8
0x78f72  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x78f77  brtrue.s loc_78F92
0x78f79  ldarg.2
0x78f7a  ldstr    aMapEntitymapsE_17// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x78f7f  ldloc.s  8
0x78f81  ldstr    aAndProcesscode_0// "\" and @ProcessCode=\"Process\"]"
0x78f86  call     string [mscorlib]System.String::Concat(string, string, string)
0x78f8b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78f90  stloc.s  0x16
0x78f92  ldloc.s  0x16
0x78f94  brfalse.s loc_78FFA
0x78f96  ldarg.s  5
0x78f98  ldloc.s  8
0x78f9a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x78f9f  brtrue.s loc_78FFA
0x78fa1  ldarg.2
0x78fa2  ldc.i4.5
0x78fa3  newarr   [mscorlib]System.String
0x78fa8  dup
0x78fa9  ldc.i4.0
0x78faa  ldstr    aMapEntitymapsE_17// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x78faf  stelem.ref
0x78fb0  dup
0x78fb1  ldc.i4.1
0x78fb2  ldloc.s  8
0x78fb4  stelem.ref
0x78fb5  dup
0x78fb6  ldc.i4.2
0x78fb7  ldstr    aAndProcesscode_5// "\" and @ProcessCode=\"Process\"]/Attrib"...
0x78fbc  stelem.ref
0x78fbd  dup
0x78fbe  ldc.i4.3
0x78fbf  ldloc.3
0x78fc0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x78fc5  stelem.ref
0x78fc6  dup
0x78fc7  ldc.i4.4
0x78fc8  ldstr    aAndProcesscode_3// "\" and ProcessCode =\"Create\"]"
0x78fcd  stelem.ref
0x78fce  call     string [mscorlib]System.String::Concat(string[])
0x78fd3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x78fd8  brtrue.s loc_78FFA
0x78fda  ldarg.s  4
0x78fdc  brfalse.s loc_78FFA
0x78fde  ldarg.0
0x78fdf  ldarg.2
0x78fe0  ldloc.s  0x16
0x78fe2  ldloc.s  0xA
0x78fe4  ldloc.s  8
0x78fe6  ldloc.2
0x78fe7  call     instance void Microsoft.Crm.ObjectModel.ImportMapXmlGenerator::InjectCustomAttributeMapForExistingEntity(class [System.Xml]System.Xml.XmlDocument finaldoc, class [System.Xml]System.Xml.XmlNode refNode3, string customEntityIdStr, string existingEntityLogicalNameStr, class [System.Xml]System.Xml.XmlNode attribute)
0x78fec  br.s     loc_78FFA
0x78fee  ldarg.0
0x78fef  ldarg.2
0x78ff0  ldloc.s  8
0x78ff2  ldloc.s  6
0x78ff4  ldloc.2
0x78ff5  call     instance void Microsoft.Crm.ObjectModel.ImportMapXmlGenerator::InjectExistingAttributeMap(class [System.Xml]System.Xml.XmlDocument finaldoc, string existingEntityLogicalNameStr, string targetAttributeName, class [System.Xml]System.Xml.XmlNode attribute)
0x78ffa  ldloc.1
0x78ffb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x79000  brtrue   loc_78D0A
0x79005  leave.s  loc_79027
0x79007  ldloc.1
0x79008  isinst   [mscorlib]System.IDisposable
0x7900d  stloc.s  0x17
0x7900f  ldloc.s  0x17
0x79011  brfalse.s loc_7901A
0x79013  ldloc.s  0x17
0x79015  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7901a  endfinally
0x7901b  leave.s  loc_79027
0x7901d  ldloc.0
0x7901e  brfalse.s loc_79026
0x79020  ldloc.0
  ... truncated ...
```
