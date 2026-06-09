# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectAttributeCustomizations

- ea: `0x62980`
- end: `0x62cca`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectAttributeCustomizations`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x62570`

## callees

- `0x3aa00`
- `0x62980`
- `0x62cd0`
- `0x62e70`
- `0x63200`
- `0x632d0`
- `0x64f70`

## string_xrefs

- `0x62981`: `/ImportCustomizations/Attributes/CustomAttribute/CreateAttributeCustomizationXml/Attribute`
- `0x629ce`: `CustomizationXml/attribute/ShortLogicalName`
- `0x62a70`: `" and @ProcessCode="Create"]`
- `0x62a9e`: `" and @ProcessCode="Create"]/AttributeMaps/AttributeMap[TargetAttributeRef = "`
- `0x62aaf`: `" and ProcessCode ="Create"]`
- `0x62c67`: `" and ProcessCode ="Create"]`
- `0x62ae4`: `CustomizationXml[@inject="false"]`
- `0x62af9`: `CreateAttributeMapping/AttributeMap/SourceAttributeName`
- `0x62b1c`: `' and @ProcessCode='Create']/AttributeMaps/AttributeMap[ProcessCode ='Unmapped']`

## pseudocode

```c

```

## disassembly

```asm
0x62980  ldarg.1
0x62981  ldstr    aImportcustomiz_0// "/ImportCustomizations/Attributes/Custom"...
0x62986  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6298b  stloc.0
0x6298c  ldloc.0
0x6298d  brfalse  loc_62CBC
0x62992  ldloc.0
0x62993  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x62998  ldc.i4.0
0x62999  ble      loc_62CBC
0x6299e  ldloc.0
0x6299f  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x629a4  stloc.1
0x629a5  br       loc_62C9B
0x629aa  ldloc.1
0x629ab  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x629b0  castclass [System.Xml]System.Xml.XmlNode
0x629b5  stloc.2
0x629b6  ldloc.2
0x629b7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x629bc  ldstr    aId_0// "Id"
0x629c1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x629c6  stloc.3
0x629c7  ldloc.3
0x629c8  brfalse  loc_62C9B
0x629cd  ldloc.2
0x629ce  ldstr    aCustomizationx_0// "CustomizationXml/attribute/ShortLogical"...
0x629d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x629d8  stloc.s  4
0x629da  ldloc.s  4
0x629dc  brfalse  loc_62C9B
0x629e1  ldloc.s  4
0x629e3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x629e8  stloc.s  5
0x629ea  ldarg.3
0x629eb  ldloc.s  5
0x629ed  call     string [mscorlib]System.String::Concat(string, string)
0x629f2  stloc.s  6
0x629f4  ldloc.2
0x629f5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x629fa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x629ff  ldstr    aExistingentity_0// "ExistingEntityLogicalName"
0x62a04  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62a09  stloc.s  7
0x62a0b  ldsfld   string [mscorlib]System.String::Empty
0x62a10  stloc.s  8
0x62a12  ldloc.s  7
0x62a14  brfalse.s loc_62A1F
0x62a16  ldloc.s  7
0x62a18  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62a1d  stloc.s  8
0x62a1f  ldloc.2
0x62a20  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62a25  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62a2a  ldstr    aCustomentityid// "CustomEntityId"
0x62a2f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62a34  stloc.s  9
0x62a36  ldsfld   string [mscorlib]System.String::Empty
0x62a3b  stloc.s  0xA
0x62a3d  ldloc.s  9
0x62a3f  brfalse.s loc_62A4A
0x62a41  ldloc.s  9
0x62a43  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62a48  stloc.s  0xA
0x62a4a  ldarg.0
0x62a4b  ldloc.s  8
0x62a4d  ldloc.s  6
0x62a4f  ldarg.3
0x62a50  ldarg.s  6
0x62a52  call     instance bool Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::CheckIfAttributePresent(string targetEntityName, string targetAttributeName, string metadataPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x62a57  brtrue   loc_62C8F
0x62a5c  ldnull
0x62a5d  stloc.s  0xB
0x62a5f  ldloc.s  0xA
0x62a61  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62a66  brtrue.s loc_62A81
0x62a68  ldarg.2
0x62a69  ldstr    aMapEntitymapsE_18// "/Map/EntityMaps/EntityMap[@TargetEntity"...
0x62a6e  ldloc.s  0xA
0x62a70  ldstr    aAndProcesscode_1// "\" and @ProcessCode=\"Create\"]"
0x62a75  call     string [mscorlib]System.String::Concat(string, string, string)
0x62a7a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62a7f  stloc.s  0xB
0x62a81  ldloc.s  0xB
0x62a83  brfalse  loc_62C0C
0x62a88  ldarg.2
0x62a89  ldc.i4.5
0x62a8a  newarr   [mscorlib]System.String
0x62a8f  dup
0x62a90  ldc.i4.0
0x62a91  ldstr    aMapEntitymapsE_18// "/Map/EntityMaps/EntityMap[@TargetEntity"...
0x62a96  stelem.ref
0x62a97  dup
0x62a98  ldc.i4.1
0x62a99  ldloc.s  0xA
0x62a9b  stelem.ref
0x62a9c  dup
0x62a9d  ldc.i4.2
0x62a9e  ldstr    aAndProcesscode_2// "\" and @ProcessCode=\"Create\"]/Attribu"...
0x62aa3  stelem.ref
0x62aa4  dup
0x62aa5  ldc.i4.3
0x62aa6  ldloc.3
0x62aa7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62aac  stelem.ref
0x62aad  dup
0x62aae  ldc.i4.4
0x62aaf  ldstr    aAndProcesscode_3// "\" and ProcessCode =\"Create\"]"
0x62ab4  stelem.ref
0x62ab5  call     string [mscorlib]System.String::Concat(string[])
0x62aba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62abf  ldnull
0x62ac0  ceq
0x62ac2  ldarg.s  4
0x62ac4  and
0x62ac5  brfalse  loc_62C9B
0x62aca  ldarg.2
0x62acb  ldstr    aMapCustomizati_1// "/Map/Customizations/Entities/Entity[@Id"...
0x62ad0  ldloc.s  0xA
0x62ad2  ldstr    asc_D7CA0// "\"]"
0x62ad7  call     string [mscorlib]System.String::Concat(string, string, string)
0x62adc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62ae1  stloc.s  0xC
0x62ae3  ldloc.2
0x62ae4  ldstr    aCustomizationx_1// "CustomizationXml[@inject=\"false\"]"
0x62ae9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62aee  ldloc.2
0x62aef  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62af4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62af9  ldstr    aCreateattribut// "CreateAttributeMapping/AttributeMap/Sou"...
0x62afe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62b03  stloc.s  0xD
0x62b05  ldnull
0x62b06  stloc.s  0xE
0x62b08  ldloc.s  0xD
0x62b0a  brfalse.s loc_62B3F
0x62b0c  ldloc.s  0xD
0x62b0e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62b13  stloc.s  0xF
0x62b15  ldstr    aMapEntitymapsE_19// "/Map/EntityMaps/EntityMap[@TargetEntity"...
0x62b1a  ldloc.s  0xA
0x62b1c  ldstr    aAndProcesscode_4// "' and @ProcessCode='Create']/AttributeM"...
0x62b21  call     string [mscorlib]System.String::Concat(string, string, string)
0x62b26  stloc.s  0x10
0x62b28  ldarg.2
0x62b29  ldloc.s  0x10
0x62b2b  ldstr    aSourceattribut_1// "SourceAttributeName"
0x62b30  ldloc.s  0xF
0x62b32  ldc.i4.0
0x62b33  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x62b38  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Platform.XPathHelper::SelectSingleNode(class [System.Xml]System.Xml.XmlNode xmlNode, string initialXPath, string name, string value, valuetype XPathCondition condition, class [mscorlib]System.Globalization.CultureInfo culture)
0x62b3d  stloc.s  0xE
0x62b3f  brtrue.s loc_62B8C
0x62b41  ldloc.s  0xC
0x62b43  brfalse.s loc_62B8C
0x62b45  ldloc.s  0xE
0x62b47  brfalse.s loc_62B8C
0x62b49  ldloc.s  0xC
0x62b4b  ldstr    aAttributes_0// "Attributes"
0x62b50  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62b55  stloc.s  0x11
0x62b57  ldloc.s  0x11
0x62b59  brtrue.s loc_62B78
0x62b5b  ldarg.2
0x62b5c  ldc.i4.1
0x62b5d  ldstr    aAttributes_0// "Attributes"
0x62b62  ldsfld   string [mscorlib]System.String::Empty
0x62b67  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x62b6c  stloc.s  0x11
0x62b6e  ldloc.s  0xC
0x62b70  ldloc.s  0x11
0x62b72  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62b77  pop
0x62b78  ldarg.2
0x62b79  ldloc.2
0x62b7a  ldc.i4.1
0x62b7b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x62b80  stloc.s  0x12
0x62b82  ldloc.s  0x11
0x62b84  ldloc.s  0x12
0x62b86  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62b8b  pop
0x62b8c  ldloc.s  0xC
0x62b8e  brfalse  loc_62C9B
0x62b93  ldloc.s  0xE
0x62b95  brfalse  loc_62C9B
0x62b9a  ldloc.2
0x62b9b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62ba0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_NextSibling()
0x62ba5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x62baa  stloc.s  0x13
0x62bac  ldarg.2
0x62bad  ldloc.s  0x13
0x62baf  ldc.i4.1
0x62bb0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x62bb5  stloc.s  0x14
0x62bb7  ldloc.s  0xB
0x62bb9  ldstr    aAttributemaps// "AttributeMaps"
0x62bbe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62bc3  stloc.s  0x15
0x62bc5  ldloc.s  0x15
0x62bc7  brtrue.s loc_62BE6
0x62bc9  ldarg.2
0x62bca  ldc.i4.1
0x62bcb  ldstr    aAttributemaps// "AttributeMaps"
0x62bd0  ldsfld   string [mscorlib]System.String::Empty
0x62bd5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x62bda  stloc.s  0x15
0x62bdc  ldloc.s  0xB
0x62bde  ldloc.s  0x15
0x62be0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62be5  pop
0x62be6  ldloc.s  0x15
0x62be8  ldloc.s  0x14
0x62bea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62bef  pop
0x62bf0  ldarg.0
0x62bf1  ldarga.s 2
0x62bf3  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::MarkMapAsInjected(class [System.Xml]System.Xml.XmlDocument& doc)
0x62bf8  ldloc.s  0xE
0x62bfa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62bff  ldloc.s  0xE
0x62c01  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x62c06  pop
0x62c07  br       loc_62C9B
0x62c0c  ldnull
0x62c0d  stloc.s  0x16
0x62c0f  ldloc.s  8
0x62c11  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62c16  brtrue.s loc_62C31
0x62c18  ldarg.2
0x62c19  ldstr    aMapEntitymapsE_17// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x62c1e  ldloc.s  8
0x62c20  ldstr    aAndProcesscode_0// "\" and @ProcessCode=\"Process\"]"
0x62c25  call     string [mscorlib]System.String::Concat(string, string, string)
0x62c2a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62c2f  stloc.s  0x16
0x62c31  ldloc.s  0x16
0x62c33  brfalse.s loc_62C9B
0x62c35  ldarg.s  5
0x62c37  ldloc.s  8
0x62c39  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x62c3e  brtrue.s loc_62C9B
0x62c40  ldarg.2
0x62c41  ldc.i4.5
0x62c42  newarr   [mscorlib]System.String
0x62c47  dup
0x62c48  ldc.i4.0
0x62c49  ldstr    aMapEntitymapsE_17// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x62c4e  stelem.ref
0x62c4f  dup
0x62c50  ldc.i4.1
0x62c51  ldloc.s  8
0x62c53  stelem.ref
0x62c54  dup
0x62c55  ldc.i4.2
0x62c56  ldstr    aAndProcesscode_5// "\" and @ProcessCode=\"Process\"]/Attrib"...
0x62c5b  stelem.ref
0x62c5c  dup
0x62c5d  ldc.i4.3
0x62c5e  ldloc.3
0x62c5f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62c64  stelem.ref
0x62c65  dup
0x62c66  ldc.i4.4
0x62c67  ldstr    aAndProcesscode_3// "\" and ProcessCode =\"Create\"]"
0x62c6c  stelem.ref
0x62c6d  call     string [mscorlib]System.String::Concat(string[])
0x62c72  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62c77  ldnull
0x62c78  ceq
0x62c7a  ldarg.s  4
0x62c7c  and
0x62c7d  brfalse.s loc_62C9B
0x62c7f  ldarg.0
0x62c80  ldarg.2
0x62c81  ldloc.s  0x16
0x62c83  ldloc.s  0xA
0x62c85  ldloc.s  8
0x62c87  ldloc.2
0x62c88  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectCustomAttributeMapForExistingEntity(class [System.Xml]System.Xml.XmlDocument finaldoc, class [System.Xml]System.Xml.XmlNode refNode3, string customEntityIdStr, string existingEntityLogicalNameStr, class [System.Xml]System.Xml.XmlNode attribute)
0x62c8d  br.s     loc_62C9B
0x62c8f  ldarg.0
0x62c90  ldarg.2
0x62c91  ldloc.s  8
0x62c93  ldloc.s  6
0x62c95  ldloc.2
0x62c96  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectExistingAttributeMap(class [System.Xml]System.Xml.XmlDocument finaldoc, string existingEntityLogicalNameStr, string targetAttributeName, class [System.Xml]System.Xml.XmlNode attribute)
0x62c9b  ldloc.1
0x62c9c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62ca1  brtrue   loc_629AA
0x62ca6  leave.s  loc_62CC8
0x62ca8  ldloc.1
0x62ca9  isinst   [mscorlib]System.IDisposable
0x62cae  stloc.s  0x17
0x62cb0  ldloc.s  0x17
0x62cb2  brfalse.s loc_62CBB
0x62cb4  ldloc.s  0x17
0x62cb6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62cbb  endfinally
  ... truncated ...
```
