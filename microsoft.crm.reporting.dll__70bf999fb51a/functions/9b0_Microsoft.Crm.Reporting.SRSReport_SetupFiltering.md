# Microsoft.Crm.Reporting.SRSReport::SetupFiltering

- ea: `0x9b0`
- end: `0xaf6`
- name: `Microsoft.Crm.Reporting.SRSReport::SetupFiltering`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7f0`

## callees

- `0x9b0`
- `0xb00`
- `0xbc0`
- `0xe90`
- `0x1490`
- `0x1730`
- `0x2ac0`
- `0x2ad0`

## string_xrefs

- `0xa91`: `Command text is invalid.`

## pseudocode

```c

```

## disassembly

```asm
0x9b0  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x9b5  stloc.0
0x9b6  ldarg.0
0x9b7  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x9bc  ldstr    aDataset// "DataSet"
0x9c1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x9c6  stloc.1
0x9c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9cc  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x9d1  stloc.2
0x9d2  ldloc.2
0x9d3  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter)
0x9d8  stloc.3
0x9d9  ldstr    aReportfilterRe_0// "<ReportFilter></ReportFilter>"
0x9de  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x9e3  stloc.s  4
0x9e5  ldloc.3
0x9e6  ldstr    aDatasets// "DataSets"
0x9eb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9f0  ldarg.1
0x9f1  brfalse.s loc_9FB
0x9f3  ldarg.1
0x9f4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9f9  brtrue.s loc_A02
0x9fb  ldstr    aReportfilterRe_0// "<ReportFilter></ReportFilter>"
0xa00  starg.s  1
0xa02  ldarg.1
0xa03  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xa08  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa0d  stloc.s  5
0xa0f  ldarg.0
0xa10  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::SelectDefaultFilterNode()
0xa15  stloc.s  6
0xa17  newobj   instance void Microsoft.Crm.Reporting.ReportQueryBuilder::.ctor()
0xa1c  stloc.s  7
0xa1e  ldloc.s  7
0xa20  ldc.i4.1
0xa21  callvirt instance void Microsoft.Crm.Reporting.ReportQueryBuilder::set_UseStoredProcs(bool value)
0xa26  ldc.i4.1
0xa27  stloc.s  8
0xa29  ldc.i4.0
0xa2a  stloc.s  9
0xa2c  ldc.i4.0
0xa2d  stloc.s  0xA
0xa2f  br.s     loc_AA9
0xa31  ldloc.1
0xa32  ldloc.s  0xA
0xa34  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xa39  stloc.s  0xB
0xa3b  ldloc.s  0xB
0xa3d  ldstr    aQuery// "Query"
0xa42  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa47  ldstr    aDatasourcename// "DataSourceName"
0xa4c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa51  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa56  stloc.s  0xC
0xa58  ldarg.0
0xa59  ldloc.s  0xC
0xa5b  call     instance valuetype Microsoft.Crm.Reporting.DataProviderType Microsoft.Crm.Reporting.SRSReport::GetDataSourceType(string dataSourceName)
0xa60  brtrue.s loc_A7C
0xa62  ldc.i4.1
0xa63  stloc.s  9
0xa65  ldarg.0
0xa66  ldloc.s  0xB
0xa68  ldloc.s  5
0xa6a  ldloc.s  6
0xa6c  ldloc.s  7
0xa6e  ldarg.2
0xa6f  ldloc.0
0xa70  ldloc.3
0xa71  ldloc.s  4
0xa73  ldloca.s 8
0xa75  call     instance void Microsoft.Crm.Reporting.SRSReport::ConvertSqlDataSet(class [System.Xml]System.Xml.XmlNode dataset, class [System.Xml]System.Xml.XmlNode origFilterNode, class [System.Xml]System.Xml.XmlNode storedFilterNode, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Hashtable aliasParamTable, class [System.Xml]System.Xml.XmlWriter writerOrgCommands, class [System.Xml]System.Xml.XmlDocument defaultFilterDoc, int32& idParam)
0xa7a  br.s     loc_AA3
0xa7c  nop
0xa7d  ldarg.0
0xa7e  ldloc.s  0xB
0xa80  ldloc.s  5
0xa82  ldloc.s  6
0xa84  ldarg.2
0xa85  ldloc.3
0xa86  ldloc.s  4
0xa88  call     instance void Microsoft.Crm.Reporting.SRSReport::ProcessFetchDataSet(class [System.Xml]System.Xml.XmlNode dataset, class [System.Xml]System.Xml.XmlNode origFilterNode, class [System.Xml]System.Xml.XmlNode storedFilterNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlWriter writerOrgCommands, class [System.Xml]System.Xml.XmlDocument defaultFilterDoc)
0xa8d  leave.s  loc_AA3
0xa8f  stloc.s  0xD
0xa91  ldstr    aCommandTextIsI// "Command text is invalid."
0xa96  ldloc.s  0xD
0xa98  ldc.i4   0x80040303
0xa9d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0xaa2  throw
0xaa3  ldloc.s  0xA
0xaa5  ldc.i4.1
0xaa6  add
0xaa7  stloc.s  0xA
0xaa9  ldloc.s  0xA
0xaab  ldloc.1
0xaac  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xab1  blt      loc_A31
0xab6  ldloc.s  9
0xab8  brfalse.s loc_AC9
0xaba  ldarg.0
0xabb  ldloc.s  7
0xabd  ldloc.s  5
0xabf  ldloc.s  6
0xac1  ldarg.2
0xac2  ldloc.s  4
0xac4  call     instance void Microsoft.Crm.Reporting.SRSReport::AddExplicitFilterParams(class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [System.Xml]System.Xml.XmlNode origFilterNode, class [System.Xml]System.Xml.XmlNode storedFilterNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument defaultFilterDoc)
0xac9  ldloc.3
0xaca  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xacf  ldloc.3
0xad0  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0xad5  ldarg.0
0xad6  ldloc.2
0xad7  callvirt instance string [mscorlib]System.Object::ToString()
0xadc  stfld    string Microsoft.Crm.Reporting.SRSReport::_originalSql
0xae1  ldarg.0
0xae2  ldloc.s  4
0xae4  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_defaultFilter
0xae9  leave.s  loc_AF5
0xaeb  ldloc.1
0xaec  brfalse.s loc_AF4
0xaee  ldloc.1
0xaef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf4  endfinally
0xaf5  ret
```
