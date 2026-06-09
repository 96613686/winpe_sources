# Word2007XmlFileHandler::ProcessForMailMerge

- ea: `0xa5380`
- end: `0xa55ae`
- name: `Word2007XmlFileHandler::ProcessForMailMerge`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa5380`

## string_xrefs

- `0xa5380`: `http://schemas.microsoft.com/office/2006/xmlPackage`
- `0xa5386`: `http://schemas.openxmlformats.org/wordprocessingml/2006/main`
- `0xa538c`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`
- `0xa53d4`: `<w:mainDocumentType w:val="formLetters"/>\n					<w:linkToQuery/>\n					<w:dataType w:val="textFile"/>\n					<w:connectString/>\n					<w:query w:val=""/>\n					<w:dataSource w:val=""/>\n					<w:viewMergedData/>\n					<w:activeRecord w:val="1"/>\n					<w:odso>\n					{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}{0}\n					</w:odso>`
- `0xa5430`: `w:linkToQuery`

## pseudocode

```c

```

## disassembly

```asm
0xa5380  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/office/200"...
0xa5385  stloc.0
0xa5386  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/wordp"...
0xa538b  stloc.1
0xa538c  ldstr    aHttpSchemasOpe_0// "http://schemas.openxmlformats.org/offic"...
0xa5391  stloc.2
0xa5392  ldarg.1
0xa5393  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa5398  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa539d  stloc.3
0xa539e  ldloc.3
0xa539f  ldstr    aPkg// "pkg"
0xa53a4  ldloc.0
0xa53a5  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa53aa  ldloc.3
0xa53ab  ldstr    aW// "w"
0xa53b0  ldloc.1
0xa53b1  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa53b6  ldloc.3
0xa53b7  ldstr    aR// "r"
0xa53bc  ldloc.2
0xa53bd  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa53c2  ldarg.1
0xa53c3  ldstr    aWMailmerge// "//w:mailMerge"
0xa53c8  ldloc.3
0xa53c9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa53ce  stloc.s  4
0xa53d0  ldloc.s  4
0xa53d2  brtrue.s loc_A542E
0xa53d4  ldstr    aWMaindocumentt// "<w:mainDocumentType w:val=\"formLetters"...
0xa53d9  stloc.s  5
0xa53db  ldstr    aWFieldmapdataW// "<w:fieldMapData>\r\n\t\t\t\t\t\t\t<w:co"...
0xa53e0  stloc.s  6
0xa53e2  ldarg.1
0xa53e3  ldstr    aWMailmerge_0// "w:mailMerge"
0xa53e8  ldloc.1
0xa53e9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa53ee  stloc.s  4
0xa53f0  ldarg.1
0xa53f1  ldstr    aWSettings// "//w:settings"
0xa53f6  ldloc.3
0xa53f7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa53fc  stloc.s  7
0xa53fe  ldloc.s  7
0xa5400  ldloc.s  4
0xa5402  ldloc.s  7
0xa5404  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa5409  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa540e  pop
0xa540f  ldloc.s  4
0xa5411  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5416  ldloc.s  5
0xa5418  ldc.i4.1
0xa5419  newarr   [mscorlib]System.Object
0xa541e  dup
0xa541f  ldc.i4.0
0xa5420  ldloc.s  6
0xa5422  stelem.ref
0xa5423  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa5428  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa542d  ret
0xa542e  ldloc.s  4
0xa5430  ldstr    aWLinktoquery// "w:linkToQuery"
0xa5435  ldloc.3
0xa5436  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa543b  stloc.s  8
0xa543d  ldloc.s  8
0xa543f  brfalse.s loc_A544D
0xa5441  ldloc.s  8
0xa5443  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5448  callvirt instance void [System.Xml]System.Xml.XmlAttributeCollection::RemoveAll()
0xa544d  ldloc.s  4
0xa544f  ldstr    aWDatatype// "w:dataType"
0xa5454  ldloc.3
0xa5455  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa545a  stloc.s  9
0xa545c  ldloc.s  9
0xa545e  brfalse.s loc_A546E
0xa5460  ldloc.s  9
0xa5462  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5467  callvirt instance void [System.Xml]System.Xml.XmlAttributeCollection::RemoveAll()
0xa546c  br.s     loc_A548D
0xa546e  ldarg.1
0xa546f  ldstr    aWDatatype// "w:dataType"
0xa5474  ldloc.1
0xa5475  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa547a  stloc.s  9
0xa547c  ldloc.s  4
0xa547e  ldloc.s  9
0xa5480  ldloc.s  4
0xa5482  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa5487  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa548c  pop
0xa548d  ldarg.1
0xa548e  ldstr    aWVal// "w:val"
0xa5493  ldloc.1
0xa5494  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5499  stloc.s  0xA
0xa549b  ldloc.s  0xA
0xa549d  ldstr    aTextfile// "textFile"
0xa54a2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa54a7  ldloc.s  9
0xa54a9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa54ae  ldloc.s  0xA
0xa54b0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa54b5  pop
0xa54b6  ldloc.s  4
0xa54b8  ldstr    aWConnectstring// "w:connectString"
0xa54bd  ldloc.3
0xa54be  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa54c3  stloc.s  0xB
0xa54c5  ldloc.s  0xB
0xa54c7  brfalse.s loc_A54D5
0xa54c9  ldloc.s  0xB
0xa54cb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa54d0  callvirt instance void [System.Xml]System.Xml.XmlAttributeCollection::RemoveAll()
0xa54d5  ldloc.s  4
0xa54d7  ldstr    aWQuery// "w:query"
0xa54dc  ldloc.3
0xa54dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa54e2  stloc.s  0xC
0xa54e4  ldloc.s  0xC
0xa54e6  brfalse.s loc_A551D
0xa54e8  ldloc.s  0xC
0xa54ea  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa54ef  callvirt instance void [System.Xml]System.Xml.XmlAttributeCollection::RemoveAll()
0xa54f4  ldarg.1
0xa54f5  ldstr    aWVal// "w:val"
0xa54fa  ldloc.1
0xa54fb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5500  stloc.s  0xF
0xa5502  ldloc.s  0xF
0xa5504  ldsfld   string [mscorlib]System.String::Empty
0xa5509  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa550e  ldloc.s  0xC
0xa5510  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5515  ldloc.s  0xF
0xa5517  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa551c  pop
0xa551d  ldloc.s  4
0xa551f  ldstr    aWDatasource// "w:dataSource"
0xa5524  ldloc.3
0xa5525  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa552a  stloc.s  0xD
0xa552c  ldloc.s  0xD
0xa552e  brfalse.s loc_A5565
0xa5530  ldloc.s  0xD
0xa5532  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa5537  callvirt instance void [System.Xml]System.Xml.XmlAttributeCollection::RemoveAll()
0xa553c  ldarg.1
0xa553d  ldstr    aWVal// "w:val"
0xa5542  ldloc.1
0xa5543  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5548  stloc.s  0x10
0xa554a  ldloc.s  0x10
0xa554c  ldsfld   string [mscorlib]System.String::Empty
0xa5551  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa5556  ldloc.s  0xD
0xa5558  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa555d  ldloc.s  0x10
0xa555f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa5564  pop
0xa5565  ldloc.s  4
0xa5567  ldstr    aWActiverecord// "w:activeRecord"
0xa556c  ldloc.3
0xa556d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa5572  stloc.s  0xE
0xa5574  ldloc.s  0xE
0xa5576  brfalse.s loc_A55AD
0xa5578  ldloc.s  0xE
0xa557a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa557f  callvirt instance void [System.Xml]System.Xml.XmlAttributeCollection::RemoveAll()
0xa5584  ldarg.1
0xa5585  ldstr    aWVal// "w:val"
0xa558a  ldloc.1
0xa558b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa5590  stloc.s  0x11
0xa5592  ldloc.s  0x11
0xa5594  ldstr    a1// "1"
0xa5599  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa559e  ldloc.s  0xE
0xa55a0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa55a5  ldloc.s  0x11
0xa55a7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa55ac  pop
0xa55ad  ret
```
