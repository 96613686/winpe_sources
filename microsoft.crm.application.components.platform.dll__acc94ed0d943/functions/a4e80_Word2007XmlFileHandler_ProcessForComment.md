# Word2007XmlFileHandler::ProcessForComment

- ea: `0xa4e80`
- end: `0xa5375`
- name: `Word2007XmlFileHandler::ProcessForComment`
- size: `1269`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x11760`
- `0x30260`
- `0xa4e80`

## string_xrefs

- `0xa5242`: `MailMerge_Document_Comment_CautionBoldText`
- `0xa5259`: `MailMerge_Document_Comment_CautionText`
- `0xa52bc`: `MailMerge_Document_Comment_Text2`
- `0xa530b`: `MailMerge_Document_Comment_Text`
- `0xa535a`: `MailMerge_Document_Comment_BoldText`
- `0xa4e82`: `http://schemas.microsoft.com/office/2006/xmlPackage`
- `0xa4e88`: `http://schemas.openxmlformats.org/wordprocessingml/2006/main`
- `0xa4e8e`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`
- `0xa4e94`: `http://schemas.openxmlformats.org/package/2006/relationships`
- `0xa4ed0`: `/pkg:package/pkg:part[@pkg:name = "/word/comments.xml"]`
- `0xa4ee6`: `/pkg:package/pkg:part[@pkg:name = "/word/_rels/document.xml.rels"][1]/pkg:xmlData`
- `0xa4f7a`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/comments`
- `0xa4f93`: `comments.xml`
- `0xa4fca`: `	<pkg:xmlData>\n		<w:comments xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006" xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships" xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math" xmlns:v="urn:schemas-microsoft-com:vml" xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing" xmlns:w10="urn:schemas-microsoft-com:office:word" xmlns:w="http://schemas.openx`
- `0xa4fff`: `/pkg:package/pkg:part[@pkg:name = "/word/document.xml"]`
- `0xa5037`: `/word/comments.xml`
- `0xa5060`: `application/vnd.openxmlformats-officedocument.wordprocessingml.comments+xml`
- `0xa507e`: `<w:p>\n		<w:r>\n			<w:t xml:space="preserve">{0}</w:t>\n		</w:r>\n	</w:p>`
- `0xa508b`: `comment`
- `0xa5099`: `/pkg:package/pkg:part[@pkg:name = "/word/comments.xml"][1]/pkg:xmlData/w:comments`
- `0xa51c1`: `<w:commentRangeStart w:id="{0}"/>\n			<w:r><w:t>{1}</w:t></w:r>\n			<w:commentRangeEnd w:id="{0}"/>\n			<w:r>\n				<w:commentReference w:id="{0}"/>\n			</w:r>`

## pseudocode

```c

```

## disassembly

```asm
0xa4e80  ldc.i4.0
0xa4e81  stloc.0
0xa4e82  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/office/200"...
0xa4e87  stloc.1
0xa4e88  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/wordp"...
0xa4e8d  stloc.2
0xa4e8e  ldstr    aHttpSchemasOpe_0// "http://schemas.openxmlformats.org/offic"...
0xa4e93  stloc.3
0xa4e94  ldstr    aHttpSchemasOpe_1// "http://schemas.openxmlformats.org/packa"...
0xa4e99  stloc.s  4
0xa4e9b  ldarg.1
0xa4e9c  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa4ea1  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa4ea6  stloc.s  5
0xa4ea8  ldloc.s  5
0xa4eaa  ldstr    aPkg// "pkg"
0xa4eaf  ldloc.1
0xa4eb0  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4eb5  ldloc.s  5
0xa4eb7  ldstr    aW// "w"
0xa4ebc  ldloc.2
0xa4ebd  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4ec2  ldloc.s  5
0xa4ec4  ldstr    aR// "r"
0xa4ec9  ldloc.3
0xa4eca  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4ecf  ldarg.1
0xa4ed0  ldstr    aPkgPackagePkgP_3// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa4ed5  ldloc.s  5
0xa4ed7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4edc  stloc.s  6
0xa4ede  ldloc.s  6
0xa4ee0  brtrue   loc_A507E
0xa4ee5  ldarg.1
0xa4ee6  ldstr    aPkgPackagePkgP_4// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa4eeb  ldloc.s  5
0xa4eed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4ef2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4ef7  stloc.s  0x12
0xa4ef9  ldloc.s  0x12
0xa4efb  brtrue.s loc_A4F08
0xa4efd  ldstr    aDocRelationshi// "doc relationships node not found."
0xa4f02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xa4f07  throw
0xa4f08  ldloc.s  0x12
0xa4f0a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa4f0f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xa4f14  ldc.i4.1
0xa4f15  add
0xa4f16  stloc.s  0x19
0xa4f18  ldarg.1
0xa4f19  ldstr    aRelationship_0// "Relationship"
0xa4f1e  ldloc.s  4
0xa4f20  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4f25  stloc.s  0x1A
0xa4f27  ldloc.s  0x12
0xa4f29  ldloc.s  0x1A
0xa4f2b  ldloc.s  0x12
0xa4f2d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4f32  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4f37  pop
0xa4f38  ldarg.1
0xa4f39  ldstr    aId_0// "Id"
0xa4f3e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4f43  stloc.s  0x1B
0xa4f45  ldloc.s  0x1B
0xa4f47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4f4c  ldstr    aRid0// "rId{0}"
0xa4f51  ldc.i4.1
0xa4f52  newarr   [mscorlib]System.Object
0xa4f57  dup
0xa4f58  ldc.i4.0
0xa4f59  ldloc.s  0x19
0xa4f5b  box      [mscorlib]System.Int32
0xa4f60  stelem.ref
0xa4f61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa4f66  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4f6b  ldarg.1
0xa4f6c  ldstr    aType_0// "Type"
0xa4f71  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4f76  stloc.s  0x1C
0xa4f78  ldloc.s  0x1C
0xa4f7a  ldstr    aHttpSchemasOpe_5// "http://schemas.openxmlformats.org/offic"...
0xa4f7f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4f84  ldarg.1
0xa4f85  ldstr    aTarget// "Target"
0xa4f8a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa4f8f  stloc.s  0x1D
0xa4f91  ldloc.s  0x1D
0xa4f93  ldstr    aCommentsXml// "comments.xml"
0xa4f98  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4f9d  ldloc.s  0x1A
0xa4f9f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4fa4  ldloc.s  0x1B
0xa4fa6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4fab  pop
0xa4fac  ldloc.s  0x1A
0xa4fae  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4fb3  ldloc.s  0x1C
0xa4fb5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4fba  pop
0xa4fbb  ldloc.s  0x1A
0xa4fbd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4fc2  ldloc.s  0x1D
0xa4fc4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4fc9  pop
0xa4fca  ldstr    aPkgXmldataWCom// "\t<pkg:xmlData>\r\n\t\t<w:comments xmln"...
0xa4fcf  stloc.s  0x13
0xa4fd1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4fd6  ldloc.s  0x13
0xa4fd8  ldc.i4.1
0xa4fd9  newarr   [mscorlib]System.Object
0xa4fde  dup
0xa4fdf  ldc.i4.0
0xa4fe0  ldarg.2
0xa4fe1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa4fe6  stelem.ref
0xa4fe7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa4fec  stloc.s  0x14
0xa4fee  ldc.i4.0
0xa4fef  stloc.0
0xa4ff0  ldarg.1
0xa4ff1  ldstr    aPkgPart// "pkg:part"
0xa4ff6  ldloc.1
0xa4ff7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4ffc  stloc.s  0x15
0xa4ffe  ldarg.1
0xa4fff  ldstr    aPkgPackagePkgP_5// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa5004  ldloc.s  5
0xa5006  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa500b  stloc.s  0x16
0xa500d  ldloc.s  0x16
0xa500f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa5014  ldloc.s  0x15
0xa5016  ldloc.s  0x16
0xa5018  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa501d  pop
0xa501e  ldloc.s  0x15
0xa5020  ldloc.s  0x14
0xa5022  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa5027  ldarg.1
0xa5028  ldstr    aPkgName// "pkg:name"
0xa502d  ldloc.1
0xa502e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5033  stloc.s  0x17
0xa5035  ldloc.s  0x17
0xa5037  ldstr    aWordCommentsXm// "/word/comments.xml"
0xa503c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa5041  ldloc.s  0x15
0xa5043  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5048  ldloc.s  0x17
0xa504a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa504f  pop
0xa5050  ldarg.1
0xa5051  ldstr    aPkgContenttype// "pkg:contentType"
0xa5056  ldloc.1
0xa5057  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa505c  stloc.s  0x18
0xa505e  ldloc.s  0x18
0xa5060  ldstr    aApplicationVnd_1// "application/vnd.openxmlformats-officedo"...
0xa5065  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa506a  ldloc.s  0x15
0xa506c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5071  ldloc.s  0x18
0xa5073  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa5078  pop
0xa5079  br       loc_A51B3
0xa507e  ldstr    aWPWRWTXmlSpace// "<w:p>\r\n\t\t<w:r>\r\n\t\t\t<w:t xml:sp"...
0xa5083  stloc.s  0x1E
0xa5085  ldarg.1
0xa5086  ldstr    aW// "w"
0xa508b  ldstr    aComment// "comment"
0xa5090  ldloc.2
0xa5091  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0xa5096  stloc.s  0x1F
0xa5098  ldarg.1
0xa5099  ldstr    aPkgPackagePkgP_6// "/pkg:package/pkg:part[@pkg:name = \"/wo"...
0xa509e  ldloc.s  5
0xa50a0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa50a5  stloc.s  0x20
0xa50a7  ldloc.s  0x20
0xa50a9  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa50ae  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xa50b3  stloc.0
0xa50b4  ldloc.s  0x20
0xa50b6  ldloc.s  0x1F
0xa50b8  ldloc.s  0x20
0xa50ba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa50bf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa50c4  pop
0xa50c5  ldloc.s  0x1F
0xa50c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa50cc  ldloc.s  0x1E
0xa50ce  ldc.i4.1
0xa50cf  newarr   [mscorlib]System.Object
0xa50d4  dup
0xa50d5  ldc.i4.0
0xa50d6  ldarg.2
0xa50d7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa50dc  stelem.ref
0xa50dd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa50e2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa50e7  ldarg.1
0xa50e8  ldstr    aWId// "w:id"
0xa50ed  ldloc.2
0xa50ee  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa50f3  stloc.s  0x21
0xa50f5  ldloc.s  0x21
0xa50f7  ldloca.s 0
0xa50f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa50fe  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa5103  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa5108  ldloc.s  0x1F
0xa510a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa510f  ldloc.s  0x21
0xa5111  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa5116  pop
0xa5117  ldarg.1
0xa5118  ldstr    aW// "w"
0xa511d  ldstr    aAuthor_0// "author"
0xa5122  ldloc.2
0xa5123  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string, string)
0xa5128  stloc.s  0x22
0xa512a  ldloc.s  0x22
0xa512c  ldstr    aMscrm_0// "MSCRM"
0xa5131  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa5136  ldloc.s  0x1F
0xa5138  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa513d  ldloc.s  0x22
0xa513f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa5144  pop
0xa5145  ldarg.1
0xa5146  ldstr    aWDate// "w:date"
0xa514b  ldloc.2
0xa514c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5151  stloc.s  0x23
0xa5153  ldloc.s  0x23
0xa5155  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xa515a  stloc.s  0x25
0xa515c  ldloca.s 0x25
0xa515e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xa5163  stloc.s  0x25
0xa5165  ldloca.s 0x25
0xa5167  ldstr    aO// "o"
0xa516c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5171  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xa5176  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa517b  ldloc.s  0x1F
0xa517d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5182  ldloc.s  0x23
0xa5184  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa5189  pop
0xa518a  ldarg.1
0xa518b  ldstr    aWInitials// "w:initials"
0xa5190  ldloc.2
0xa5191  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5196  stloc.s  0x24
0xa5198  ldloc.s  0x24
0xa519a  ldstr    aCrm// "CRM"
0xa519f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa51a4  ldloc.s  0x1F
0xa51a6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa51ab  ldloc.s  0x24
0xa51ad  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa51b2  pop
0xa51b3  ldstr    aWRWRprWBWRprWT_1// "<w:r>\r\n\t\t\t<w:rPr>\r\n\t\t\t\t<w:b/"...
0xa51b8  stloc.s  7
0xa51ba  ldstr    aWRWT0WTWR_0// "<w:r>\r\n\t\t\t<w:t>{0}</w:t>\r\n\t\t</"...
0xa51bf  stloc.s  8
0xa51c1  ldstr    aWCommentranges// "<w:commentRangeStart w:id=\"{0}\"/>\r\n"...
0xa51c6  stloc.s  9
0xa51c8  ldstr    aWRWRprWBWRprWT_2// "<w:r>\r\n\t\t\t<w:rPr>\r\n\t\t\t\t<w:b/"...
0xa51cd  stloc.s  0xA
0xa51cf  ldstr    aWPprWPbdrWBott_0// "<w:pPr><w:pBdr><w:bottom w:val=\"single"...
0xa51d4  stloc.s  0xB
0xa51d6  ldarg.1
0xa51d7  ldstr    aWBody// "//w:body"
0xa51dc  ldloc.s  5
0xa51de  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa51e3  stloc.s  0xC
0xa51e5  ldarg.1
0xa51e6  ldstr    aWP// "w:p"
0xa51eb  ldloc.2
0xa51ec  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa51f1  stloc.s  0xD
0xa51f3  ldloc.s  0xC
0xa51f5  ldloc.s  0xD
0xa51f7  ldloc.s  0xC
0xa51f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa51fe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa5203  pop
0xa5204  ldloc.s  0xD
0xa5206  ldloc.s  0xB
0xa5208  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa520d  ldarg.1
0xa520e  ldstr    aWP// "w:p"
0xa5213  ldloc.2
0xa5214  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa5219  stloc.s  0xE
0xa521b  ldloc.s  0xC
  ... truncated ...
```
