# Word2003XmlFileHandler::ProcessForMergeType

- ea: `0xa4020`
- end: `0xa4146`
- name: `Word2003XmlFileHandler::ProcessForMergeType`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa4020`

## string_xrefs

- `0xa4020`: `http://schemas.microsoft.com/office/word/2003/wordml`
- `0xa4026`: `http://schemas.microsoft.com/office/word/2003/auxHint`
- `0xa402c`: `urn:schemas-microsoft-com:office:office`

## pseudocode

```c

```

## disassembly

```asm
0xa4020  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/office/wor"...
0xa4025  stloc.0
0xa4026  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/office/wor"...
0xa402b  stloc.1
0xa402c  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:office:office"
0xa4031  stloc.2
0xa4032  ldstr    aUuidC2f4101065// "uuid:C2F41010-65B3-11d1-A29F-00AA00C148"...
0xa4037  stloc.3
0xa4038  ldarg.1
0xa4039  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa403e  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa4043  stloc.s  4
0xa4045  ldloc.s  4
0xa4047  ldstr    aW// "w"
0xa404c  ldloc.0
0xa404d  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4052  ldloc.s  4
0xa4054  ldstr    aWx// "wx"
0xa4059  ldloc.1
0xa405a  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa405f  ldloc.s  4
0xa4061  ldstr    aO// "o"
0xa4066  ldloc.2
0xa4067  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa406c  ldloc.s  4
0xa406e  ldstr    aDt// "dt"
0xa4073  ldloc.3
0xa4074  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4079  ldarg.1
0xa407a  ldstr    aOCustomdocumen// "//o:CustomDocumentProperties"
0xa407f  ldloc.s  4
0xa4081  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4086  stloc.s  5
0xa4088  ldloc.s  5
0xa408a  brtrue.s loc_A40C0
0xa408c  ldarg.1
0xa408d  ldstr    aOCustomdocumen_0// "o:CustomDocumentProperties"
0xa4092  ldloc.2
0xa4093  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4098  stloc.s  5
0xa409a  ldarg.1
0xa409b  ldstr    aWWorddocument_0// "//w:wordDocument"
0xa40a0  ldloc.s  4
0xa40a2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa40a7  ldarg.1
0xa40a8  ldstr    aODocumentprope// "//o:DocumentProperties"
0xa40ad  ldloc.s  4
0xa40af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa40b4  stloc.s  8
0xa40b6  ldloc.s  5
0xa40b8  ldloc.s  8
0xa40ba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertAfter(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa40bf  pop
0xa40c0  ldarg.1
0xa40c1  ldstr    aOMscrmMergeTyp// "//o:MSCRM_Merge_Type"
0xa40c6  ldloc.s  4
0xa40c8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa40cd  stloc.s  6
0xa40cf  ldloc.s  6
0xa40d1  brtrue.s loc_A40F2
0xa40d3  ldarg.1
0xa40d4  ldstr    aOMscrmMergeTyp_0// "o:MSCRM_Merge_Type"
0xa40d9  ldloc.2
0xa40da  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa40df  stloc.s  6
0xa40e1  ldloc.s  5
0xa40e3  ldloc.s  6
0xa40e5  ldloc.s  5
0xa40e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa40ec  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa40f1  pop
0xa40f2  ldloc.s  6
0xa40f4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa40f9  ldstr    aDtDt// "dt:dt"
0xa40fe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa4103  stloc.s  7
0xa4105  ldloc.s  7
0xa4107  brtrue.s loc_A4126
0xa4109  ldarg.1
0xa410a  ldstr    aDtDt// "dt:dt"
0xa410f  ldloc.3
0xa4110  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa4115  stloc.s  7
0xa4117  ldloc.s  6
0xa4119  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa411e  ldloc.s  7
0xa4120  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4125  pop
0xa4126  ldloc.s  7
0xa4128  ldstr    aFloat// "float"
0xa412d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4132  ldloc.s  6
0xa4134  ldarga.s 2
0xa4136  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa413b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa4140  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0xa4145  ret
```
