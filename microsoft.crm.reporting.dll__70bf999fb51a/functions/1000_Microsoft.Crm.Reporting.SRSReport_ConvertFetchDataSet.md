# Microsoft.Crm.Reporting.SRSReport::ConvertFetchDataSet

- ea: `0x1000`
- end: `0x1409`
- name: `Microsoft.Crm.Reporting.SRSReport::ConvertFetchDataSet`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe90`

## callees

- `0x1000`
- `0x1410`
- `0x1440`
- `0x1460`

## string_xrefs

- `0x100b`: `CommandText`
- `0x1030`: `Command text: {0} is not a valid fetch xml. Root node "fetch" is missing.`
- `0x1045`: `/fetch/entity | /fetch//link-entity`
- `0x137c`: `<fetch version="1.0" output-format="xml-platform" mapping="logical" distinct="false"><entity name="`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldarg.1
0x1001  ldstr    aQuery// "Query"
0x1006  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x100b  ldstr    aCommandtext// "CommandText"
0x1010  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1015  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x101a  stloc.0
0x101b  ldloc.0
0x101c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1021  ldstr    aFetch// "fetch"
0x1026  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x102b  stloc.1
0x102c  ldloc.1
0x102d  ldnull
0x102e  cgt.un
0x1030  ldstr    aCommandText0Is// "Command text: {0} is not a valid fetch "...
0x1035  ldc.i4.1
0x1036  newarr   [mscorlib]System.Object
0x103b  dup
0x103c  ldc.i4.0
0x103d  ldloc.0
0x103e  stelem.ref
0x103f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x1044  ldloc.1
0x1045  ldstr    aFetchEntityFet// "/fetch/entity | /fetch//link-entity"
0x104a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x104f  stloc.2
0x1050  ldloc.2
0x1051  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1056  stloc.3
0x1057  br       loc_13DD
0x105c  ldloc.3
0x105d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1062  castclass [System.Xml]System.Xml.XmlNode
0x1067  stloc.s  4
0x1069  ldloc.s  4
0x106b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1070  ldstr    aEnableprefilte// "enableprefiltering"
0x1075  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x107a  stloc.s  5
0x107c  ldloc.s  5
0x107e  brfalse  loc_13DD
0x1083  ldloc.s  5
0x1085  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x108a  callvirt instance string [mscorlib]System.String::Trim()
0x108f  ldstr    aFalse// "false"
0x1094  ldc.i4.5
0x1095  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x109a  brtrue   loc_13DD
0x109f  ldloc.s  5
0x10a1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x10a6  callvirt instance string [mscorlib]System.String::Trim()
0x10ab  ldstr    a0// "0"
0x10b0  ldc.i4.5
0x10b1  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10b6  brtrue   loc_13DD
0x10bb  ldnull
0x10bc  stloc.s  6
0x10be  ldloc.s  4
0x10c0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x10c5  ldstr    aName_0// "name"
0x10ca  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x10cf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x10d4  stloc.s  7
0x10d6  ldloc.s  4
0x10d8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x10dd  ldstr    aPrefilterparam// "prefilterparametername"
0x10e2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x10e7  stloc.s  8
0x10e9  ldloc.s  8
0x10eb  brfalse.s loc_10FD
0x10ed  ldloc.s  8
0x10ef  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x10f4  callvirt instance string [mscorlib]System.String::Trim()
0x10f9  stloc.s  6
0x10fb  br.s     loc_110B
0x10fd  ldstr    aCrm// "CRM_"
0x1102  ldloc.s  7
0x1104  call     string [mscorlib]System.String::Concat(string, string)
0x1109  stloc.s  6
0x110b  ldnull
0x110c  stloc.s  0xA
0x110e  ldc.i4.5
0x110f  newarr   [mscorlib]System.String
0x1114  dup
0x1115  ldc.i4.0
0x1116  ldstr    aReportentityPa// "//ReportEntity[@paramname="
0x111b  stelem.ref
0x111c  dup
0x111d  ldc.i4.1
0x111e  ldloc.s  6
0x1120  dup
0x1121  brtrue.s loc_1129
0x1123  pop
0x1124  ldstr    asc_A608// ""
0x1129  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::XPathEncode(string)
0x112e  stelem.ref
0x112f  dup
0x1130  ldc.i4.2
0x1131  ldstr    aFetchEntityNam// "]/fetch[entity[@name="
0x1136  stelem.ref
0x1137  dup
0x1138  ldc.i4.3
0x1139  ldloc.s  7
0x113b  dup
0x113c  brtrue.s loc_1144
0x113e  pop
0x113f  ldstr    asc_A608// ""
0x1144  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::XPathEncode(string)
0x1149  stelem.ref
0x114a  dup
0x114b  ldc.i4.4
0x114c  ldstr    asc_A636// "]]"
0x1151  stelem.ref
0x1152  call     string [mscorlib]System.String::Concat(string[])
0x1157  stloc.s  0xB
0x1159  ldarg.s  5
0x115b  brfalse.s loc_11CE
0x115d  ldarg.s  5
0x115f  ldloc.s  0xB
0x1161  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1166  dup
0x1167  stloc.s  9
0x1169  brfalse.s loc_11CE
0x116b  ldloc.s  9
0x116d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x1172  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1177  ldstr    aDonotconvert// "donotconvert"
0x117c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1181  brfalse.s loc_11AE
0x1183  ldloc.s  9
0x1185  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x118a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x118f  ldstr    aDonotconvert// "donotconvert"
0x1194  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1199  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x119e  ldstr    a0// "0"
0x11a3  ldc.i4.5
0x11a4  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x11a9  brfalse  loc_13DD
0x11ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11b3  ldstr    aParameter0Cann// "Parameter: {0} cannot be used as a pre-"...
0x11b8  ldc.i4.1
0x11b9  newarr   [mscorlib]System.Object
0x11be  dup
0x11bf  ldc.i4.0
0x11c0  ldloc.s  6
0x11c2  stelem.ref
0x11c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x11cd  throw
0x11ce  ldarg.s  5
0x11d0  ldstr    aReportentity// "ReportEntity"
0x11d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x11da  stloc.s  0xC
0x11dc  ldloc.s  0xC
0x11de  ldstr    aParamname// "paramname"
0x11e3  ldloc.s  6
0x11e5  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x11ea  ldloc.s  0xC
0x11ec  ldstr    aDonotconvert// "donotconvert"
0x11f1  ldstr    a1// "1"
0x11f6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x11fb  ldarg.s  5
0x11fd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1202  ldloc.s  0xC
0x1204  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1209  pop
0x120a  ldarg.0
0x120b  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x1210  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x1215  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x121a  stloc.s  0xD
0x121c  ldloc.s  0xD
0x121e  ldstr    aD// "d"
0x1223  ldarg.0
0x1224  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x1229  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x122e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x1233  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1238  ldarg.0
0x1239  ldarg.0
0x123a  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x123f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1244  ldstr    aReportparamete// "ReportParameters"
0x1249  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x124e  stloc.s  0xE
0x1250  ldarg.0
0x1251  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x1256  ldstr    aDReportDReport// "/d:Report/d:ReportParameters/d:ReportPa"...
0x125b  ldloc.s  6
0x125d  dup
0x125e  brtrue.s loc_1266
0x1260  pop
0x1261  ldstr    asc_A608// ""
0x1266  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::XPathEncode(string)
0x126b  ldstr    asc_A794// "]"
0x1270  call     string [mscorlib]System.String::Concat(string, string, string)
0x1275  ldloc.s  0xD
0x1277  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x127c  stloc.s  0xF
0x127e  ldloc.s  0xF
0x1280  brtrue.s loc_12BB
0x1282  ldarg.0
0x1283  ldloc.s  0xE
0x1285  ldstr    aReportparamete_0// "ReportParameter"
0x128a  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::CreateChildNode(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x128f  stloc.s  0xF
0x1291  ldloc.s  0xF
0x1293  castclass [System.Xml]System.Xml.XmlElement
0x1298  ldstr    aName// "Name"
0x129d  ldloc.s  6
0x129f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x12a4  ldarg.0
0x12a5  ldloc.s  0xF
0x12a7  ldstr    aDatatype// "DataType"
0x12ac  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x12b1  ldstr    aString// "String"
0x12b6  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x12bb  ldarg.0
0x12bc  ldloc.s  0xF
0x12be  ldstr    aPrompt// "Prompt"
0x12c3  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x12c8  stloc.s  0x10
0x12ca  ldloc.s  0x10
0x12cc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x12d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12d6  brfalse.s loc_12E1
0x12d8  ldloc.s  0x10
0x12da  ldloc.s  6
0x12dc  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x12e1  ldarg.0
0x12e2  ldloc.s  0xF
0x12e4  ldstr    aHidden// "Hidden"
0x12e9  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x12ee  ldstr    aTrue// "true"
0x12f3  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x12f8  ldarg.0
0x12f9  ldloc.s  0xF
0x12fb  ldstr    aDefaultvalue// "DefaultValue"
0x1300  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x1305  stloc.s  0x11
0x1307  ldarg.0
0x1308  ldloc.s  0x11
0x130a  ldstr    aValues// "Values"
0x130f  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x1314  stloc.s  0x12
0x1316  ldarg.0
0x1317  ldloc.s  0x12
0x1319  ldstr    aValue// "Value"
0x131e  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x1323  stloc.s  0x13
0x1325  ldarg.2
0x1326  brfalse.s loc_133F
0x1328  ldarg.2
0x1329  ldloc.s  0xB
0x132b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1330  stloc.s  9
0x1332  ldloc.s  9
0x1334  brfalse.s loc_133F
0x1336  ldloc.s  9
0x1338  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x133d  stloc.s  0xA
0x133f  ldloc.s  0xA
0x1341  brtrue.s loc_135D
0x1343  ldarg.3
0x1344  brfalse.s loc_135D
0x1346  ldarg.3
0x1347  ldloc.s  0xB
0x1349  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x134e  stloc.s  9
0x1350  ldloc.s  9
0x1352  brfalse.s loc_135D
0x1354  ldloc.s  9
0x1356  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x135b  stloc.s  0xA
0x135d  ldloc.s  0xA
0x135f  brtrue.s loc_1378
0x1361  ldloc.s  0x13
0x1363  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1368  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x136d  brtrue.s loc_1378
0x136f  ldloc.s  0x13
0x1371  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1376  stloc.s  0xA
0x1378  ldloc.s  0xA
0x137a  brtrue.s loc_13C8
0x137c  ldstr    aFetchVersion10// "<fetch version=\"1.0\" output-format=\""...
0x1381  ldloc.s  7
0x1383  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x1388  ldstr    aAllAttributes// "\"><all-attributes/>"
0x138d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1392  stloc.s  0x14
0x1394  ldstr    aEntityFetch// "</entity></fetch>"
0x1399  stloc.s  0x15
0x139b  ldstr    aFilterTypeAndC// "<filter type=\"and\"><condition attribu"...
0x13a0  stloc.s  0x16
0x13a2  ldarg.0
0x13a3  ldloc.s  7
0x13a5  ldarg.s  4
  ... truncated ...
```
