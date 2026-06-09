# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectCustomAttributeMapForExistingEntity

- ea: `0x62cd0`
- end: `0x62e6d`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectCustomAttributeMapForExistingEntity`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x62980`

## callees

- `0x3aa00`
- `0x62cd0`
- `0x63200`
- `0x63310`
- `0x64f70`

## string_xrefs

- `0x62d22`: `CustomizationXml[@inject="false"]`
- `0x62cdc`: `CreateAttributeMapping/AttributeMap/SourceAttributeName`

## pseudocode

```c

```

## disassembly

```asm
0x62cd0  ldarg.s  5
0x62cd2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62cd7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62cdc  ldstr    aCreateattribut// "CreateAttributeMapping/AttributeMap/Sou"...
0x62ce1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62ce6  stloc.0
0x62ce7  ldloc.0
0x62ce8  brfalse  loc_62E6C
0x62ced  ldloc.0
0x62cee  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62cf3  stloc.1
0x62cf4  ldstr    aMapEntitymapsE_8// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x62cf9  ldarg.s  4
0x62cfb  ldstr    aAndProcesscode_6// "' and @ProcessCode='Process']/Attribute"...
0x62d00  call     string [mscorlib]System.String::Concat(string, string, string)
0x62d05  stloc.2
0x62d06  ldarg.1
0x62d07  ldloc.2
0x62d08  ldstr    aSourceattribut_1// "SourceAttributeName"
0x62d0d  ldloc.1
0x62d0e  ldc.i4.0
0x62d0f  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x62d14  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Platform.XPathHelper::SelectSingleNode(class [System.Xml]System.Xml.XmlNode xmlNode, string initialXPath, string name, string value, valuetype XPathCondition condition, class [mscorlib]System.Globalization.CultureInfo culture)
0x62d19  stloc.3
0x62d1a  ldloc.3
0x62d1b  brfalse  loc_62E6C
0x62d20  ldarg.s  5
0x62d22  ldstr    aCustomizationx_1// "CustomizationXml[@inject=\"false\"]"
0x62d27  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62d2c  brtrue   loc_62E02
0x62d31  ldarg.1
0x62d32  ldstr    aMapCustomizati_1// "/Map/Customizations/Entities/Entity[@Id"...
0x62d37  ldarg.3
0x62d38  ldstr    asc_D7CA0// "\"]"
0x62d3d  call     string [mscorlib]System.String::Concat(string, string, string)
0x62d42  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62d47  stloc.s  7
0x62d49  ldloc.s  7
0x62d4b  brtrue.s loc_62D66
0x62d4d  ldarg.1
0x62d4e  ldstr    aMapCustomizati_2// "/Map/Customizations/Entities/Entity[Log"...
0x62d53  ldarg.s  4
0x62d55  ldstr    asc_D7CA0// "\"]"
0x62d5a  call     string [mscorlib]System.String::Concat(string, string, string)
0x62d5f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62d64  stloc.s  7
0x62d66  ldloc.s  7
0x62d68  brtrue.s loc_62DBE
0x62d6a  ldarg.0
0x62d6b  ldarga.s 1
0x62d6d  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::CreateCustomizationSectionIfNotPresent(class [System.Xml]System.Xml.XmlDocument& doc)
0x62d72  ldarg.1
0x62d73  ldstr    aMapCustomizati_0// "/Map/Customizations/Entities"
0x62d78  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62d7d  ldarg.1
0x62d7e  ldc.i4.1
0x62d7f  ldstr    aEntity_0// "Entity"
0x62d84  ldsfld   string [mscorlib]System.String::Empty
0x62d89  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x62d8e  stloc.s  7
0x62d90  ldarg.1
0x62d91  ldc.i4.1
0x62d92  ldstr    aLogicalname_0// "LogicalName"
0x62d97  ldsfld   string [mscorlib]System.String::Empty
0x62d9c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x62da1  stloc.s  0xA
0x62da3  ldloc.s  0xA
0x62da5  ldarg.s  4
0x62da7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x62dac  ldloc.s  7
0x62dae  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62db3  pop
0x62db4  ldloc.s  7
0x62db6  ldloc.s  0xA
0x62db8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62dbd  pop
0x62dbe  ldloc.s  7
0x62dc0  ldstr    aAttributes_0// "Attributes"
0x62dc5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62dca  stloc.s  8
0x62dcc  ldloc.s  8
0x62dce  brtrue.s loc_62DED
0x62dd0  ldarg.1
0x62dd1  ldc.i4.1
0x62dd2  ldstr    aAttributes_0// "Attributes"
0x62dd7  ldsfld   string [mscorlib]System.String::Empty
0x62ddc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x62de1  stloc.s  8
0x62de3  ldloc.s  7
0x62de5  ldloc.s  8
0x62de7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62dec  pop
0x62ded  ldarg.1
0x62dee  ldarg.s  5
0x62df0  ldc.i4.1
0x62df1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x62df6  stloc.s  9
0x62df8  ldloc.s  8
0x62dfa  ldloc.s  9
0x62dfc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62e01  pop
0x62e02  ldarg.s  5
0x62e04  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62e09  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_NextSibling()
0x62e0e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x62e13  stloc.s  4
0x62e15  ldarg.1
0x62e16  ldloc.s  4
0x62e18  ldc.i4.1
0x62e19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x62e1e  stloc.s  5
0x62e20  ldarg.2
0x62e21  ldstr    aAttributemaps// "AttributeMaps"
0x62e26  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62e2b  stloc.s  6
0x62e2d  ldloc.s  6
0x62e2f  brtrue.s loc_62E4D
0x62e31  ldarg.1
0x62e32  ldc.i4.1
0x62e33  ldstr    aAttributemaps// "AttributeMaps"
0x62e38  ldsfld   string [mscorlib]System.String::Empty
0x62e3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x62e42  stloc.s  6
0x62e44  ldarg.2
0x62e45  ldloc.s  6
0x62e47  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62e4c  pop
0x62e4d  ldloc.s  6
0x62e4f  ldloc.s  5
0x62e51  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62e56  pop
0x62e57  ldarg.0
0x62e58  ldarga.s 1
0x62e5a  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::MarkMapAsInjected(class [System.Xml]System.Xml.XmlDocument& doc)
0x62e5f  ldloc.3
0x62e60  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62e65  ldloc.3
0x62e66  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x62e6b  pop
0x62e6c  ret
```
