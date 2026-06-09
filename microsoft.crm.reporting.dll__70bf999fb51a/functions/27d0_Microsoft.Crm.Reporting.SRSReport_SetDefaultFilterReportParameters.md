# Microsoft.Crm.Reporting.SRSReport::SetDefaultFilterReportParameters

- ea: `0x27d0`
- end: `0x2950`
- name: `Microsoft.Crm.Reporting.SRSReport::SetDefaultFilterReportParameters`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x19c0`
- `0x2680`
- `0x27d0`
- `0x2ad0`

## string_xrefs

- `0x27d1`: `filterXml`

## pseudocode

```c

```

## disassembly

```asm
0x27d0  ldarg.1
0x27d1  ldstr    aFilterxml// "filterXml"
0x27d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x27db  ldarg.2
0x27dc  ldstr    aContext// "context"
0x27e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x27e6  newobj   instance void Microsoft.Crm.Reporting.ReportQueryBuilder::.ctor()
0x27eb  stloc.0
0x27ec  ldarg.0
0x27ed  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x27f2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x27f7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x27fc  stloc.1
0x27fd  ldarg.0
0x27fe  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x2803  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x2808  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x280d  stloc.2
0x280e  ldloc.2
0x280f  ldstr    aRdl// "rdl"
0x2814  ldloc.1
0x2815  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x281a  ldarg.1
0x281b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2820  ldstr    aReportfilterRe_1// "/ReportFilter/ReportEntity"
0x2825  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x282a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x282f  stloc.3
0x2830  br       loc_292E
0x2835  ldloc.3
0x2836  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x283b  castclass [System.Xml]System.Xml.XmlNode
0x2840  stloc.s  4
0x2842  ldloc.s  4
0x2844  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x2849  stloc.s  5
0x284b  ldloc.s  4
0x284d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2852  ldstr    aDonotconvert// "donotconvert"
0x2857  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x285c  brfalse.s loc_2881
0x285e  ldloc.s  4
0x2860  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2865  ldstr    aDonotconvert// "donotconvert"
0x286a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x286f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2874  ldstr    a0// "0"
0x2879  ldc.i4.5
0x287a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x287f  brfalse.s loc_288C
0x2881  ldloc.s  5
0x2883  ldloc.0
0x2884  ldarg.2
0x2885  call     string Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql(string fetchXml, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x288a  stloc.s  5
0x288c  ldloc.s  5
0x288e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2893  brtrue   loc_292E
0x2898  ldloc.s  4
0x289a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x289f  ldstr    aParamname// "paramname"
0x28a4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28a9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x28ae  stloc.s  6
0x28b0  ldarg.0
0x28b1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x28b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28bb  ldstr    aRdlReportparam// "//rdl:ReportParameter[@Name='{0}']"
0x28c0  ldc.i4.1
0x28c1  newarr   [mscorlib]System.Object
0x28c6  dup
0x28c7  ldc.i4.0
0x28c8  ldloc.s  6
0x28ca  stelem.ref
0x28cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28d0  ldloc.2
0x28d1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x28d6  stloc.s  7
0x28d8  ldloc.s  6
0x28da  brfalse.s loc_292E
0x28dc  ldarg.0
0x28dd  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x28e2  ldloc.s  7
0x28e4  ldstr    aDefaultvalue// "DefaultValue"
0x28e9  ldloc.1
0x28ea  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x28ef  stloc.s  8
0x28f1  ldarg.0
0x28f2  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x28f7  ldloc.s  8
0x28f9  ldstr    aValues// "Values"
0x28fe  ldloc.1
0x28ff  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode startingNode, string name, string ns)
0x2904  dup
0x2905  callvirt instance void [System.Xml]System.Xml.XmlNode::RemoveAll()
0x290a  ldarg.0
0x290b  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x2910  ldstr    aValue// "Value"
0x2915  ldloc.1
0x2916  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x291b  stloc.s  9
0x291d  ldloc.s  9
0x291f  ldloc.s  5
0x2921  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x2926  ldloc.s  9
0x2928  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x292d  pop
0x292e  ldloc.3
0x292f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2934  brtrue   loc_2835
0x2939  leave.s  loc_294F
0x293b  ldloc.3
0x293c  isinst   [mscorlib]System.IDisposable
0x2941  stloc.s  0xA
0x2943  ldloc.s  0xA
0x2945  brfalse.s loc_294E
0x2947  ldloc.s  0xA
0x2949  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x294e  endfinally
0x294f  ret
```
