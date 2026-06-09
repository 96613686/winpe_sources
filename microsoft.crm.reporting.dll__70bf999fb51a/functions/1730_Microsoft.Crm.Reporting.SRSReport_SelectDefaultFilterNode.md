# Microsoft.Crm.Reporting.SRSReport::SelectDefaultFilterNode

- ea: `0x1730`
- end: `0x17f3`
- name: `Microsoft.Crm.Reporting.SRSReport::SelectDefaultFilterNode`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9b0`

## callees

- `0x1730`

## string_xrefs

- `0x177b`: `http://schemas.microsoft.com/sqlserver/reporting/2003/10/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0x1730  ldnull
0x1731  stloc.0
0x1732  ldarg.0
0x1733  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x1738  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x173d  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x1742  stloc.1
0x1743  ldloc.1
0x1744  ldstr    aD// "d"
0x1749  ldarg.0
0x174a  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x174f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1754  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x1759  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x175e  ldloc.1
0x175f  ldstr    aM// "m"
0x1764  ldstr    aMscrm// "mscrm"
0x1769  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x176e  ldnull
0x176f  stloc.2
0x1770  ldloc.1
0x1771  ldstr    aD// "d"
0x1776  callvirt instance string [System.Xml]System.Xml.XmlNamespaceManager::LookupNamespace(string)
0x177b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x1780  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1785  brfalse.s loc_179B
0x1787  ldarg.0
0x1788  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x178d  ldstr    aDReportDCustom// "/d:Report/d:Custom/m:MSCRM"
0x1792  ldloc.1
0x1793  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x1798  stloc.2
0x1799  br.s     loc_17D6
0x179b  ldarg.0
0x179c  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x17a1  ldstr    aDReportDCustom_0// "/d:Report/d:CustomProperties/d:CustomPr"...
0x17a6  ldloc.1
0x17a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x17ac  stloc.3
0x17ad  ldloc.3
0x17ae  brfalse.s loc_17D6
0x17b0  ldstr    aRoot// "<root>"
0x17b5  ldloc.3
0x17b6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x17bb  ldstr    aRoot_0// "</root>"
0x17c0  call     string [mscorlib]System.String::Concat(string, string, string)
0x17c5  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x17ca  ldstr    aRootMMscrm// "/root/m:MSCRM"
0x17cf  ldloc.1
0x17d0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x17d5  stloc.2
0x17d6  ldloc.2
0x17d7  brtrue.s loc_17DB
0x17d9  ldnull
0x17da  ret
0x17db  ldloc.2
0x17dc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x17e1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x17e6  stloc.0
0x17e7  ldloc.0
0x17e8  ldstr    aReportfilter// "/ReportFilter"
0x17ed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17f2  ret
```
