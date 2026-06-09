# Word2007XmlFileHandler::ProcessForMergeType

- ea: `0xa4590`
- end: `0xa4a79`
- name: `Word2007XmlFileHandler::ProcessForMergeType`
- size: `1257`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa4590`

## string_xrefs

- `0xa4590`: `http://schemas.microsoft.com/office/2006/xmlPackage`
- `0xa4596`: `http://schemas.openxmlformats.org/wordprocessingml/2006/main`
- `0xa459c`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`
- `0xa45a2`: `http://schemas.openxmlformats.org/package/2006/relationships`
- `0xa45a8`: `http://schemas.openxmlformats.org/officeDocument/2006/docPropsVTypes`
- `0xa4683`: `http://schemas.openxmlformats.org/officeDocument/2006/docPropsVTypes`
- `0xa45af`: `http://schemas.openxmlformats.org/officeDocument/2006/custom-properties`
- `0xa45f9`: `/pkg:package/pkg:part[@pkg:name = "/docProps/custom.xml"]`
- `0xa461d`: `/pkg:package/pkg:part[@pkg:name = "/word/settings.xml"]`
- `0xa4658`: `pkg:xmlData`
- `0xa47ab`: `pkg:xmlData`
- `0xa4886`: `pkg:xmlData`
- `0xa4670`: `xmlns`
- `0xa467e`: `xmlns:vt`
- `0xa4733`: `/docProps/custom.xml`
- `0xa475c`: `application/vnd.openxmlformats-officedocument.custom-properties+xml`
- `0xa4845`: `docProps/custom.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa4590  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/office/200"...
0xa4595  stloc.0
0xa4596  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/wordp"...
0xa459b  stloc.1
0xa459c  ldstr    aHttpSchemasOpe_0// "http://schemas.openxmlformats.org/offic"...
0xa45a1  stloc.2
0xa45a2  ldstr    aHttpSchemasOpe_1// "http://schemas.openxmlformats.org/packa"...
0xa45a7  stloc.3
0xa45a8  ldstr    aHttpSchemasOpe_2// "http://schemas.openxmlformats.org/offic"...
0xa45ad  stloc.s  4
0xa45af  ldstr    aHttpSchemasOpe_3// "http://schemas.openxmlformats.org/offic"...
0xa45b4  stloc.s  5
0xa45b6  ldarg.1
0xa45b7  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa45bc  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa45c1  stloc.s  6
0xa45c3  ldloc.s  6
0xa45c5  ldstr    aPkg// "pkg"
0xa45ca  ldloc.0
0xa45cb  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa45d0  ldloc.s  6
0xa45d2  ldstr    aW// "w"
0xa45d7  ldloc.1
0xa45d8  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa45dd  ldloc.s  6
0xa45df  ldstr    aR// "r"
0xa45e4  ldloc.2
0xa45e5  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa45ea  ldloc.s  6
0xa45ec  ldstr    aVt// "vt"
0xa45f1  ldloc.s  4
0xa45f3  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa45f8  ldarg.1
0xa45f9  ldstr    aPkgPackagePkgP// "/pkg:package/pkg:part[@pkg:name = \"/do"...
0xa45fe  ldloc.s  6
0xa4600  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4605  stloc.s  7
0xa4607  ldloc.s  7
0xa4609  brtrue   loc_A487D
0xa460e  ldarg.1
0xa460f  ldstr    aPkgPart// "pkg:part"
0xa4614  ldloc.0
0xa4615  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa461a  stloc.s  8
0xa461c  ldarg.1
0xa461d  ldstr    aPkgPackagePkgP_0// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa4622  ldloc.s  6
0xa4624  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4629  stloc.s  9
0xa462b  ldloc.s  9
0xa462d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa4632  ldloc.s  8
0xa4634  ldloc.s  9
0xa4636  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa463b  pop
0xa463c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xa4641  stloc.s  0xA
0xa4643  ldloc.s  0xA
0xa4645  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa464a  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0xa464f  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xa4654  stloc.s  0x14
0xa4656  ldloc.s  0x14
0xa4658  ldstr    aPkgXmldata// "pkg:xmlData"
0xa465d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xa4662  ldloc.s  0x14
0xa4664  ldstr    aProperties// "Properties"
0xa4669  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xa466e  ldloc.s  0x14
0xa4670  ldstr    aXmlns// "xmlns"
0xa4675  ldloc.s  5
0xa4677  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa467c  ldloc.s  0x14
0xa467e  ldstr    aXmlnsVt// "xmlns:vt"
0xa4683  ldstr    aHttpSchemasOpe_2// "http://schemas.openxmlformats.org/offic"...
0xa4688  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa468d  ldloc.s  0x14
0xa468f  ldstr    aProperty// "property"
0xa4694  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xa4699  ldloc.s  0x14
0xa469b  ldstr    aFmtid// "fmtid"
0xa46a0  ldstr    aD5cdd5052e9c10// "{D5CDD505-2E9C-101B-9397-08002B2CF9AE}"
0xa46a5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa46aa  ldloc.s  0x14
0xa46ac  ldstr    aPid// "pid"
0xa46b1  ldstr    a2// "2"
0xa46b6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa46bb  ldloc.s  0x14
0xa46bd  ldstr    aName// "name"
0xa46c2  ldstr    aMscrmMergeType// "MSCRM_Merge_Type"
0xa46c7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa46cc  ldloc.s  0x14
0xa46ce  ldstr    aVtI4// "vt:i4"
0xa46d3  ldarga.s 2
0xa46d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa46da  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa46df  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xa46e4  ldloc.s  0x14
0xa46e6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xa46eb  ldloc.s  0x14
0xa46ed  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xa46f2  ldloc.s  0x14
0xa46f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xa46f9  ldloc.s  0x14
0xa46fb  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xa4700  ldloc.s  0x14
0xa4702  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0xa4707  leave.s  loc_A4715
0xa4709  ldloc.s  0x14
0xa470b  brfalse.s loc_A4714
0xa470d  ldloc.s  0x14
0xa470f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4714  endfinally
0xa4715  ldloc.s  8
0xa4717  ldloc.s  0xA
0xa4719  callvirt instance string [mscorlib]System.Object::ToString()
0xa471e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa4723  ldarg.1
0xa4724  ldstr    aPkgName// "pkg:name"
0xa4729  ldloc.0
0xa472a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa472f  stloc.s  0xB
0xa4731  ldloc.s  0xB
0xa4733  ldstr    aDocpropsCustom// "/docProps/custom.xml"
0xa4738  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa473d  ldloc.s  8
0xa473f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4744  ldloc.s  0xB
0xa4746  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa474b  pop
0xa474c  ldarg.1
0xa474d  ldstr    aPkgContenttype// "pkg:contentType"
0xa4752  ldloc.0
0xa4753  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa4758  stloc.s  0xC
0xa475a  ldloc.s  0xC
0xa475c  ldstr    aApplicationVnd// "application/vnd.openxmlformats-officedo"...
0xa4761  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4766  ldloc.s  8
0xa4768  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa476d  ldloc.s  0xC
0xa476f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4774  pop
0xa4775  ldarg.1
0xa4776  ldstr    aPkgPadding// "pkg:padding"
0xa477b  ldloc.0
0xa477c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa4781  stloc.s  0xD
0xa4783  ldloc.s  0xD
0xa4785  ldstr    a256// "256"
0xa478a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa478f  ldloc.s  8
0xa4791  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4796  ldloc.s  0xD
0xa4798  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa479d  pop
0xa479e  ldarg.1
0xa479f  ldstr    aPkgPackagePkgP_1// "/pkg:package/pkg:part[@pkg:name = \"/_r"...
0xa47a4  ldloc.s  6
0xa47a6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa47ab  ldstr    aPkgXmldata// "pkg:xmlData"
0xa47b0  ldloc.s  6
0xa47b2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa47b7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa47bc  stloc.s  0xE
0xa47be  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa47c3  ldstr    aRid0// "rId{0}"
0xa47c8  ldc.i4.1
0xa47c9  newarr   [mscorlib]System.Object
0xa47ce  dup
0xa47cf  ldc.i4.0
0xa47d0  ldloc.s  0xE
0xa47d2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa47d7  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xa47dc  ldc.i4.1
0xa47dd  add
0xa47de  box      [mscorlib]System.Int32
0xa47e3  stelem.ref
0xa47e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa47e9  stloc.s  0xF
0xa47eb  ldarg.1
0xa47ec  ldstr    aRelationship_0// "Relationship"
0xa47f1  ldloc.3
0xa47f2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa47f7  stloc.s  0x10
0xa47f9  ldloc.s  0xE
0xa47fb  ldloc.s  0x10
0xa47fd  ldloc.s  0xE
0xa47ff  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4804  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4809  pop
0xa480a  ldarg.1
0xa480b  ldstr    aId_0// "Id"
0xa4810  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4815  stloc.s  0x11
0xa4817  ldloc.s  0x11
0xa4819  ldloc.s  0xF
0xa481b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4820  ldarg.1
0xa4821  ldstr    aType_0// "Type"
0xa4826  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa482b  stloc.s  0x12
0xa482d  ldloc.s  0x12
0xa482f  ldloc.s  5
0xa4831  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4836  ldarg.1
0xa4837  ldstr    aTarget// "Target"
0xa483c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4841  stloc.s  0x13
0xa4843  ldloc.s  0x13
0xa4845  ldstr    aDocpropsCustom_0// "docProps/custom.xml"
0xa484a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa484f  ldloc.s  0x10
0xa4851  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4856  ldloc.s  0x11
0xa4858  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa485d  pop
0xa485e  ldloc.s  0x10
0xa4860  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4865  ldloc.s  0x12
0xa4867  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa486c  pop
0xa486d  ldloc.s  0x10
0xa486f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4874  ldloc.s  0x13
0xa4876  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa487b  pop
0xa487c  ret
0xa487d  ldstr    a2// "2"
0xa4882  stloc.s  0x15
0xa4884  ldloc.s  7
0xa4886  ldstr    aPkgXmldata// "pkg:xmlData"
0xa488b  ldloc.s  6
0xa488d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4892  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4897  stloc.s  0x16
0xa4899  ldnull
0xa489a  stloc.s  0x17
0xa489c  ldloc.s  0x16
0xa489e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa48a3  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa48a8  stloc.s  0x1C
0xa48aa  br       loc_A4943
0xa48af  ldloc.s  0x1C
0xa48b1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa48b6  castclass [System.Xml]System.Xml.XmlNode
0xa48bb  stloc.s  0x1D
0xa48bd  ldloc.s  0x1D
0xa48bf  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa48c4  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0xa48c9  stloc.s  0x1E
0xa48cb  br.s     loc_A4923
0xa48cd  ldloc.s  0x1E
0xa48cf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa48d4  castclass [System.Xml]System.Xml.XmlAttribute
0xa48d9  stloc.s  0x1F
0xa48db  ldloc.s  0x1F
0xa48dd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xa48e2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa48e7  brtrue.s loc_A4923
0xa48e9  ldloc.s  0x1F
0xa48eb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa48f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa48f5  brtrue.s loc_A4923
0xa48f7  ldloc.s  0x1F
0xa48f9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xa48fe  ldstr    aName// "name"
0xa4903  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4908  brfalse.s loc_A4923
0xa490a  ldloc.s  0x1F
0xa490c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa4911  ldstr    aMscrmMergeType// "MSCRM_Merge_Type"
0xa4916  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa491b  brfalse.s loc_A4923
0xa491d  ldloc.s  0x1D
0xa491f  stloc.s  0x17
0xa4921  leave.s  loc_A4943
0xa4923  ldloc.s  0x1E
0xa4925  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa492a  brtrue.s loc_A48CD
0xa492c  leave.s  loc_A4943
0xa492e  ldloc.s  0x1E
0xa4930  isinst   [mscorlib]System.IDisposable
0xa4935  stloc.s  0x20
0xa4937  ldloc.s  0x20
0xa4939  brfalse.s loc_A4942
0xa493b  ldloc.s  0x20
0xa493d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4942  endfinally
0xa4943  ldloc.s  0x1C
0xa4945  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa494a  brtrue   loc_A48AF
0xa494f  leave.s  loc_A4966
0xa4951  ldloc.s  0x1C
0xa4953  isinst   [mscorlib]System.IDisposable
0xa4958  stloc.s  0x20
0xa495a  ldloc.s  0x20
0xa495c  brfalse.s loc_A4965
0xa495e  ldloc.s  0x20
0xa4960  callvirt instance void [mscorlib]System.IDisposable::Dispose()
  ... truncated ...
```
