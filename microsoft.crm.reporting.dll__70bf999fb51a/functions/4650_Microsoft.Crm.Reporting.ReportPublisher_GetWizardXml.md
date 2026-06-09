# Microsoft.Crm.Reporting.ReportPublisher::GetWizardXml

- ea: `0x4650`
- end: `0x46fa`
- name: `Microsoft.Crm.Reporting.ReportPublisher::GetWizardXml`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4410`

## string_xrefs

- `0x4651`: `customreportxml`

## pseudocode

```c

```

## disassembly

```asm
0x4650  ldarg.1
0x4651  ldstr    aCustomreportxm// "customreportxml"
0x4656  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x465b  castclass [mscorlib]System.String
0x4660  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4665  dup
0x4666  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x466b  ldstr    aCustomreport// "//CustomReport"
0x4670  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4675  stloc.0
0x4676  dup
0x4677  ldstr    aReportname// "ReportName"
0x467c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4681  stloc.1
0x4682  ldloc.1
0x4683  ldarg.1
0x4684  ldstr    aName_0// "name"
0x4689  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x468e  castclass [mscorlib]System.String
0x4693  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x4698  dup
0x4699  ldstr    aDescription_0// "Description"
0x469e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x46a3  stloc.2
0x46a4  ldloc.2
0x46a5  ldarg.1
0x46a6  ldstr    aDescription// "description"
0x46ab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x46b0  castclass [mscorlib]System.String
0x46b5  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x46ba  dup
0x46bb  ldstr    aDefaultfilter_0// "DefaultFilter"
0x46c0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x46c5  stloc.3
0x46c6  ldloc.3
0x46c7  ldarg.1
0x46c8  ldstr    aDefaultfilter// "defaultfilter"
0x46cd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x46d2  castclass [mscorlib]System.String
0x46d7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x46dc  ldloc.0
0x46dd  ldloc.1
0x46de  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x46e3  pop
0x46e4  ldloc.0
0x46e5  ldloc.2
0x46e6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x46eb  pop
0x46ec  ldloc.0
0x46ed  ldloc.3
0x46ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x46f3  pop
0x46f4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x46f9  ret
```
