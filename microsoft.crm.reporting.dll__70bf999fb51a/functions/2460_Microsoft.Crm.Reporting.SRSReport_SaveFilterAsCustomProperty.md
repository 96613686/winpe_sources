# Microsoft.Crm.Reporting.SRSReport::SaveFilterAsCustomProperty

- ea: `0x2460`
- end: `0x25a5`
- name: `Microsoft.Crm.Reporting.SRSReport::SaveFilterAsCustomProperty`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2150`

## callees

- `0x2460`
- `0x2680`

## string_xrefs

- `0x248d`: `http://schemas.microsoft.com/sqlserver/reporting/2003/10/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0x2460  ldarg.1
0x2461  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x2466  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x246b  stloc.0
0x246c  ldloc.0
0x246d  ldstr    aD// "d"
0x2472  ldarg.1
0x2473  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2478  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x247d  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x2482  ldloc.0
0x2483  ldstr    aD// "d"
0x2488  callvirt instance string [System.Xml]System.Xml.XmlNamespaceManager::LookupNamespace(string)
0x248d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x2492  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2497  brfalse.s loc_24D0
0x2499  ldarg.1
0x249a  ldarg.1
0x249b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x24a0  ldstr    aCustom// "Custom"
0x24a5  ldarg.1
0x24a6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x24ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x24b0  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x24b5  stloc.1
0x24b6  ldarg.1
0x24b7  ldloc.1
0x24b8  ldstr    aMscrm_0// "MSCRM"
0x24bd  ldstr    aMscrm// "mscrm"
0x24c2  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x24c7  stloc.1
0x24c8  ldloc.1
0x24c9  ldarg.2
0x24ca  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24cf  ret
0x24d0  ldarg.1
0x24d1  ldarg.1
0x24d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x24d7  ldstr    aCustomproperti// "CustomProperties"
0x24dc  ldarg.1
0x24dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x24e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x24e7  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x24ec  stloc.2
0x24ed  ldloc.2
0x24ee  ldstr    aDCustompropert// "d:CustomProperty[d:Name='Custom']"
0x24f3  ldloc.0
0x24f4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x24f9  stloc.3
0x24fa  ldloc.3
0x24fb  brtrue.s loc_251C
0x24fd  ldarg.1
0x24fe  ldstr    aCustomproperty// "CustomProperty"
0x2503  ldarg.1
0x2504  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2509  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x250e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x2513  stloc.3
0x2514  ldloc.2
0x2515  ldloc.3
0x2516  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x251b  pop
0x251c  ldarg.1
0x251d  ldloc.3
0x251e  ldstr    aName// "Name"
0x2523  ldarg.1
0x2524  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2529  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x252e  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x2533  ldstr    aCustom// "Custom"
0x2538  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x253d  ldarg.1
0x253e  ldloc.3
0x253f  ldstr    aValue// "Value"
0x2544  ldarg.1
0x2545  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x254a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x254f  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x2554  stloc.s  4
0x2556  ldstr    aRoot// "<root>"
0x255b  ldloc.s  4
0x255d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2562  ldstr    aRoot_0// "</root>"
0x2567  call     string [mscorlib]System.String::Concat(string, string, string)
0x256c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2571  stloc.s  5
0x2573  ldloc.s  5
0x2575  ldloc.s  5
0x2577  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x257c  ldstr    aMscrm_0// "MSCRM"
0x2581  ldstr    aMscrm// "mscrm"
0x2586  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x258b  ldarg.2
0x258c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x2591  ldloc.s  4
0x2593  ldloc.s  5
0x2595  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x259a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x259f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x25a4  ret
```
