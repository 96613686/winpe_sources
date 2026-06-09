# Word2007XmlFileHandler::ProcessForAttachedTemplate

- ea: `0xa4a80`
- end: `0xa4e7a`
- name: `Word2007XmlFileHandler::ProcessForAttachedTemplate`
- size: `1018`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x47460`
- `0xa3f40`
- `0xa4a80`

## string_xrefs

- `0xa4dfc`: `//w:attachedTemplate`
- `0xa4e0f`: `w:attachedTemplate`
- `0xa4a97`: `http://schemas.microsoft.com/office/2006/xmlPackage`
- `0xa4a9d`: `http://schemas.openxmlformats.org/wordprocessingml/2006/main`
- `0xa4aa3`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`
- `0xa4aa9`: `http://schemas.openxmlformats.org/package/2006/relationships`
- `0xa4b68`: `http://schemas.openxmlformats.org/package/2006/relationships`
- `0xa4b10`: `/pkg:package/pkg:part[@pkg:name = "/word/settings.xml"]`
- `0xa4b4b`: `pkg:xmlData`
- `0xa4c5d`: `pkg:xmlData`
- `0xa4b63`: `xmlns`
- `0xa4a80`: `_static/Tools/MailMerge/CRMTemplate.dotm`
- `0xa4aec`: `/pkg:package/pkg:part[@pkg:name = "/word/_rels/settings.xml.rels"]`
- `0xa4b96`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/attachedTemplate`
- `0xa4ca7`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/attachedTemplate`
- `0xa4d87`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/attachedTemplate`
- `0xa4c14`: `/word/_rels/settings.xml.rels`
- `0xa4c3d`: `application/vnd.openxmlformats-package.relationships+xml`

## pseudocode

```c

```

## disassembly

```asm
0xa4a80  ldstr    aStaticToolsMai_0// "_static/Tools/MailMerge/CRMTemplate.dot"...
0xa4a85  ldc.i4.0
0xa4a86  ldarg.0
0xa4a87  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext WordXmlFileHandler::get_Context()
0xa4a8c  call     class [System]System.Uri Microsoft.Crm.Application.Utility.Util::GetAbsoluteUrl(string relativePath, bool prependOrgName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xa4a91  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xa4a96  stloc.0
0xa4a97  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/office/200"...
0xa4a9c  stloc.1
0xa4a9d  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/wordp"...
0xa4aa2  stloc.2
0xa4aa3  ldstr    aHttpSchemasOpe_0// "http://schemas.openxmlformats.org/offic"...
0xa4aa8  stloc.3
0xa4aa9  ldstr    aHttpSchemasOpe_1// "http://schemas.openxmlformats.org/packa"...
0xa4aae  stloc.s  4
0xa4ab0  ldstr    aRid1// "rId1"
0xa4ab5  stloc.s  5
0xa4ab7  ldarg.1
0xa4ab8  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa4abd  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa4ac2  stloc.s  6
0xa4ac4  ldloc.s  6
0xa4ac6  ldstr    aPkg// "pkg"
0xa4acb  ldloc.1
0xa4acc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4ad1  ldloc.s  6
0xa4ad3  ldstr    aW// "w"
0xa4ad8  ldloc.2
0xa4ad9  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4ade  ldloc.s  6
0xa4ae0  ldstr    aR// "r"
0xa4ae5  ldloc.3
0xa4ae6  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4aeb  ldarg.1
0xa4aec  ldstr    aPkgPackagePkgP_2// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa4af1  ldloc.s  6
0xa4af3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4af8  stloc.s  7
0xa4afa  ldloc.s  7
0xa4afc  brtrue   loc_A4C5B
0xa4b01  ldarg.1
0xa4b02  ldstr    aPkgPart// "pkg:part"
0xa4b07  ldloc.1
0xa4b08  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4b0d  stloc.s  0xA
0xa4b0f  ldarg.1
0xa4b10  ldstr    aPkgPackagePkgP_0// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa4b15  ldloc.s  6
0xa4b17  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4b1c  stloc.s  0xB
0xa4b1e  ldloc.s  0xB
0xa4b20  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa4b25  ldloc.s  0xA
0xa4b27  ldloc.s  0xB
0xa4b29  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4b2e  pop
0xa4b2f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xa4b34  stloc.s  0xC
0xa4b36  ldloc.s  0xC
0xa4b38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4b3d  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0xa4b42  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xa4b47  stloc.s  0xF
0xa4b49  ldloc.s  0xF
0xa4b4b  ldstr    aPkgXmldata// "pkg:xmlData"
0xa4b50  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xa4b55  ldloc.s  0xF
0xa4b57  ldstr    aRelationships// "Relationships"
0xa4b5c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xa4b61  ldloc.s  0xF
0xa4b63  ldstr    aXmlns// "xmlns"
0xa4b68  ldstr    aHttpSchemasOpe_1// "http://schemas.openxmlformats.org/packa"...
0xa4b6d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa4b72  ldloc.s  0xF
0xa4b74  ldstr    aRelationship_0// "Relationship"
0xa4b79  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xa4b7e  ldloc.s  0xF
0xa4b80  ldstr    aId_0// "Id"
0xa4b85  ldstr    aRid1// "rId1"
0xa4b8a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa4b8f  ldloc.s  0xF
0xa4b91  ldstr    aType_0// "Type"
0xa4b96  ldstr    aHttpSchemasOpe_4// "http://schemas.openxmlformats.org/offic"...
0xa4b9b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa4ba0  ldloc.s  0xF
0xa4ba2  ldstr    aTarget// "Target"
0xa4ba7  ldloc.0
0xa4ba8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa4bad  ldloc.s  0xF
0xa4baf  ldstr    aTargetmode// "TargetMode"
0xa4bb4  ldstr    aExternal// "External"
0xa4bb9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa4bbe  ldloc.s  0xF
0xa4bc0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xa4bc5  ldloc.s  0xF
0xa4bc7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xa4bcc  ldloc.s  0xF
0xa4bce  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xa4bd3  ldloc.s  0xF
0xa4bd5  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xa4bda  ldloc.s  0xF
0xa4bdc  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0xa4be1  leave.s  loc_A4BEF
0xa4be3  ldloc.s  0xF
0xa4be5  brfalse.s loc_A4BEE
0xa4be7  ldloc.s  0xF
0xa4be9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4bee  endfinally
0xa4bef  ldloc.s  0xA
0xa4bf1  ldloc.s  0xC
0xa4bf3  callvirt instance string [mscorlib]System.Object::ToString()
0xa4bf8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa4bfd  ldstr    aRid1// "rId1"
0xa4c02  stloc.s  5
0xa4c04  ldarg.1
0xa4c05  ldstr    aPkgName// "pkg:name"
0xa4c0a  ldloc.1
0xa4c0b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa4c10  stloc.s  0xD
0xa4c12  ldloc.s  0xD
0xa4c14  ldstr    aWordRelsSettin// "/word/_rels/settings.xml.rels"
0xa4c19  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4c1e  ldloc.s  0xA
0xa4c20  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4c25  ldloc.s  0xD
0xa4c27  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4c2c  pop
0xa4c2d  ldarg.1
0xa4c2e  ldstr    aPkgContenttype// "pkg:contentType"
0xa4c33  ldloc.1
0xa4c34  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa4c39  stloc.s  0xE
0xa4c3b  ldloc.s  0xE
0xa4c3d  ldstr    aApplicationVnd_0// "application/vnd.openxmlformats-package."...
0xa4c42  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4c47  ldloc.s  0xA
0xa4c49  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4c4e  ldloc.s  0xE
0xa4c50  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4c55  pop
0xa4c56  br       loc_A4DFB
0xa4c5b  ldloc.s  7
0xa4c5d  ldstr    aPkgXmldata// "pkg:xmlData"
0xa4c62  ldloc.s  6
0xa4c64  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4c69  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4c6e  stloc.s  0x10
0xa4c70  ldc.i4.0
0xa4c71  stloc.s  0x11
0xa4c73  ldloc.s  0x10
0xa4c75  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa4c7a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa4c7f  stloc.s  0x12
0xa4c81  br.s     loc_A4CEE
0xa4c83  ldloc.s  0x12
0xa4c85  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa4c8a  castclass [System.Xml]System.Xml.XmlNode
0xa4c8f  stloc.s  0x13
0xa4c91  ldloc.s  0x13
0xa4c93  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4c98  ldstr    aType_0// "Type"
0xa4c9d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa4ca2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa4ca7  ldstr    aHttpSchemasOpe_4// "http://schemas.openxmlformats.org/offic"...
0xa4cac  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4cb1  brfalse.s loc_A4CEE
0xa4cb3  ldloc.s  0x13
0xa4cb5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4cba  ldstr    aTarget// "Target"
0xa4cbf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa4cc4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa4cc9  ldloc.0
0xa4cca  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4ccf  brfalse.s loc_A4CEE
0xa4cd1  ldc.i4.1
0xa4cd2  stloc.s  0x11
0xa4cd4  ldloc.s  0x13
0xa4cd6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4cdb  ldstr    aId_0// "Id"
0xa4ce0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa4ce5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa4cea  stloc.s  5
0xa4cec  leave.s  loc_A4D0E
0xa4cee  ldloc.s  0x12
0xa4cf0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa4cf5  brtrue.s loc_A4C83
0xa4cf7  leave.s  loc_A4D0E
0xa4cf9  ldloc.s  0x12
0xa4cfb  isinst   [mscorlib]System.IDisposable
0xa4d00  stloc.s  0x14
0xa4d02  ldloc.s  0x14
0xa4d04  brfalse.s loc_A4D0D
0xa4d06  ldloc.s  0x14
0xa4d08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4d0d  endfinally
0xa4d0e  ldloc.s  0x11
0xa4d10  brtrue   loc_A4DFB
0xa4d15  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4d1a  ldstr    aRid0// "rId{0}"
0xa4d1f  ldc.i4.1
0xa4d20  newarr   [mscorlib]System.Object
0xa4d25  dup
0xa4d26  ldc.i4.0
0xa4d27  ldloc.s  0x10
0xa4d29  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa4d2e  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xa4d33  ldc.i4.1
0xa4d34  add
0xa4d35  box      [mscorlib]System.Int32
0xa4d3a  stelem.ref
0xa4d3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa4d40  stloc.s  5
0xa4d42  ldarg.1
0xa4d43  ldstr    aRelationship_0// "Relationship"
0xa4d48  ldloc.s  4
0xa4d4a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4d4f  stloc.s  0x15
0xa4d51  ldloc.s  0x10
0xa4d53  ldloc.s  0x15
0xa4d55  ldloc.s  0x10
0xa4d57  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4d5c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4d61  pop
0xa4d62  ldarg.1
0xa4d63  ldstr    aId_0// "Id"
0xa4d68  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4d6d  stloc.s  0x16
0xa4d6f  ldloc.s  0x16
0xa4d71  ldloc.s  5
0xa4d73  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4d78  ldarg.1
0xa4d79  ldstr    aType_0// "Type"
0xa4d7e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4d83  stloc.s  0x17
0xa4d85  ldloc.s  0x17
0xa4d87  ldstr    aHttpSchemasOpe_4// "http://schemas.openxmlformats.org/offic"...
0xa4d8c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4d91  ldarg.1
0xa4d92  ldstr    aTarget// "Target"
0xa4d97  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4d9c  stloc.s  0x18
0xa4d9e  ldloc.s  0x18
0xa4da0  ldloc.0
0xa4da1  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4da6  ldarg.1
0xa4da7  ldstr    aTargetmode// "TargetMode"
0xa4dac  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4db1  stloc.s  0x19
0xa4db3  ldloc.s  0x19
0xa4db5  ldstr    aExternal// "External"
0xa4dba  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4dbf  ldloc.s  0x15
0xa4dc1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4dc6  ldloc.s  0x16
0xa4dc8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4dcd  pop
0xa4dce  ldloc.s  0x15
0xa4dd0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4dd5  ldloc.s  0x17
0xa4dd7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4ddc  pop
0xa4ddd  ldloc.s  0x15
0xa4ddf  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4de4  ldloc.s  0x18
0xa4de6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4deb  pop
0xa4dec  ldloc.s  0x15
0xa4dee  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4df3  ldloc.s  0x19
0xa4df5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4dfa  pop
0xa4dfb  ldarg.1
0xa4dfc  ldstr    aWAttachedtempl// "//w:attachedTemplate"
0xa4e01  ldloc.s  6
0xa4e03  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4e08  stloc.s  8
0xa4e0a  ldloc.s  8
0xa4e0c  brtrue.s loc_A4E3C
0xa4e0e  ldarg.1
0xa4e0f  ldstr    aWAttachedtempl_0// "w:attachedTemplate"
0xa4e14  ldloc.2
0xa4e15  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4e1a  stloc.s  8
0xa4e1c  ldarg.1
0xa4e1d  ldstr    aWSettings// "//w:settings"
0xa4e22  ldloc.s  6
0xa4e24  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4e29  stloc.s  0x1A
0xa4e2b  ldloc.s  0x1A
0xa4e2d  ldloc.s  8
0xa4e2f  ldloc.s  0x1A
0xa4e31  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4e36  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4e3b  pop
0xa4e3c  ldloc.s  8
0xa4e3e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4e43  ldstr    aRId// "r:id"
0xa4e48  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa4e4d  stloc.s  9
0xa4e4f  ldloc.s  9
  ... truncated ...
```
