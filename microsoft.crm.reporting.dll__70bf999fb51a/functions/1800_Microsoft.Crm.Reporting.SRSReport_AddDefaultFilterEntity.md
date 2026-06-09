# Microsoft.Crm.Reporting.SRSReport::AddDefaultFilterEntity

- ea: `0x1800`
- end: `0x19b7`
- name: `Microsoft.Crm.Reporting.SRSReport::AddDefaultFilterEntity`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbc0`
- `0x1490`

## callees

- `0x1410`
- `0x1800`
- `0x19c0`

## string_xrefs

- `0x1919`: `<fetch version="1.0" output-format="xml-platform" mapping="logical" distinct="false"><entity name="`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldnull
0x1801  stloc.0
0x1802  ldnull
0x1803  stloc.1
0x1804  ldnull
0x1805  stloc.2
0x1806  ldc.i4.5
0x1807  newarr   [mscorlib]System.String
0x180c  dup
0x180d  ldc.i4.0
0x180e  ldstr    aReportentity_0// "//ReportEntity"
0x1813  stelem.ref
0x1814  dup
0x1815  ldc.i4.1
0x1816  ldarg.s  6
0x1818  brfalse.s loc_1832
0x181a  ldstr    aNumber// "[@number="
0x181f  ldarg.s  6
0x1821  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::XPathEncode(string)
0x1826  ldstr    asc_A794// "]"
0x182b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1830  br.s     loc_1837
0x1832  ldsfld   string [mscorlib]System.String::Empty
0x1837  stelem.ref
0x1838  dup
0x1839  ldc.i4.2
0x183a  ldstr    aFetchEntityNam_0// "/fetch[entity[@name="
0x183f  stelem.ref
0x1840  dup
0x1841  ldc.i4.3
0x1842  ldarg.s  5
0x1844  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::XPathEncode(string)
0x1849  stelem.ref
0x184a  dup
0x184b  ldc.i4.4
0x184c  ldstr    asc_A636// "]]"
0x1851  stelem.ref
0x1852  call     string [mscorlib]System.String::Concat(string[])
0x1857  stloc.3
0x1858  ldarg.1
0x1859  brfalse.s loc_18D3
0x185b  ldarg.1
0x185c  ldloc.3
0x185d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1862  dup
0x1863  stloc.1
0x1864  brfalse.s loc_18D3
0x1866  ldloc.1
0x1867  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x186c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1871  ldstr    aDonotconvert// "donotconvert"
0x1876  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x187b  brfalse.s loc_18C4
0x187d  ldloc.1
0x187e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x1883  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1888  ldstr    aDonotconvert// "donotconvert"
0x188d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1892  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1897  ldstr    a1// "1"
0x189c  ldc.i4.5
0x189d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x18a2  brfalse.s loc_18C4
0x18a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18a9  ldstr    aParameter0Cann// "Parameter: {0} cannot be used as a pre-"...
0x18ae  ldc.i4.1
0x18af  newarr   [mscorlib]System.Object
0x18b4  dup
0x18b5  ldc.i4.0
0x18b6  ldarg.s  7
0x18b8  stelem.ref
0x18b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18be  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x18c3  throw
0x18c4  ldloc.1
0x18c5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x18ca  ldarg.2
0x18cb  ldarg.s  8
0x18cd  call     string Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql(string fetchXml, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x18d2  ret
0x18d3  ldarg.3
0x18d4  brfalse.s loc_18F2
0x18d6  ldarg.3
0x18d7  ldloc.3
0x18d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x18dd  stloc.1
0x18de  ldloc.1
0x18df  brfalse.s loc_18F2
0x18e1  ldloc.1
0x18e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x18e7  stloc.2
0x18e8  ldloc.2
0x18e9  ldarg.2
0x18ea  ldarg.s  8
0x18ec  call     string Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql(string fetchXml, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x18f1  stloc.0
0x18f2  ldloc.0
0x18f3  brtrue.s loc_1916
0x18f5  ldarg.s  4
0x18f7  brfalse.s loc_1916
0x18f9  ldarg.s  4
0x18fb  ldloc.3
0x18fc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1901  stloc.1
0x1902  ldloc.1
0x1903  brfalse.s loc_1916
0x1905  ldloc.1
0x1906  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x190b  stloc.2
0x190c  ldloc.2
0x190d  ldarg.2
0x190e  ldarg.s  8
0x1910  call     string Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql(string fetchXml, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1915  stloc.0
0x1916  ldloc.0
0x1917  brtrue.s loc_196D
0x1919  ldstr    aFetchVersion10// "<fetch version=\"1.0\" output-format=\""...
0x191e  ldarg.s  5
0x1920  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x1925  ldstr    aAllAttributes// "\"><all-attributes/>"
0x192a  call     string [mscorlib]System.String::Concat(string, string, string)
0x192f  stloc.s  4
0x1931  ldstr    aEntityFetch// "</entity></fetch>"
0x1936  stloc.s  5
0x1938  ldstr    aFilterTypeAndC// "<filter type=\"and\"><condition attribu"...
0x193d  stloc.s  6
0x193f  ldarg.0
0x1940  ldarg.s  5
0x1942  ldarg.s  8
0x1944  call     instance bool Microsoft.Crm.Reporting.SRSReport::IsValidForFiltering(string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1949  brfalse.s loc_1959
0x194b  ldloc.s  4
0x194d  ldloc.s  6
0x194f  ldloc.s  5
0x1951  call     string [mscorlib]System.String::Concat(string, string, string)
0x1956  stloc.2
0x1957  br.s     loc_1963
0x1959  ldloc.s  4
0x195b  ldloc.s  5
0x195d  call     string [mscorlib]System.String::Concat(string, string)
0x1962  stloc.2
0x1963  ldloc.2
0x1964  ldarg.2
0x1965  ldarg.s  8
0x1967  call     string Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql(string fetchXml, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x196c  stloc.0
0x196d  ldloc.0
0x196e  brtrue.s loc_1972
0x1970  ldnull
0x1971  ret
0x1972  ldarg.1
0x1973  ldstr    aReportentity// "ReportEntity"
0x1978  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x197d  stloc.s  7
0x197f  ldarg.s  6
0x1981  brfalse.s loc_1991
0x1983  ldloc.s  7
0x1985  ldstr    aNumber_0// "number"
0x198a  ldarg.s  6
0x198c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1991  ldloc.s  7
0x1993  ldstr    aParamname// "paramname"
0x1998  ldarg.s  7
0x199a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x199f  ldloc.s  7
0x19a1  ldloc.2
0x19a2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x19a7  ldarg.1
0x19a8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x19ad  ldloc.s  7
0x19af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x19b4  pop
0x19b5  ldloc.0
0x19b6  ret
```
