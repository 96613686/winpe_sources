# Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql

- ea: `0x19c0`
- end: `0x19e1`
- name: `Microsoft.Crm.Reporting.SRSReport::ConvertFetchToSql`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800`
- `0x27d0`
- `0x5780`

## callees

- `0x19f0`
- `0x2030`
- `0x2ae0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.0
0x19c1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x19c6  dup
0x19c7  call     void Microsoft.Crm.Reporting.SRSReport::StripFetchEmptyFields(class [System.Xml]System.Xml.XmlDocument fetchDoc)
0x19cc  dup
0x19cd  call     void Microsoft.Crm.Reporting.SRSReport::StripFetchEmptyFilters(class [System.Xml]System.Xml.XmlDocument fetchDoc)
0x19d2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x19d7  stloc.0
0x19d8  ldarg.1
0x19d9  ldloc.0
0x19da  ldarg.2
0x19db  callvirt instance string Microsoft.Crm.Reporting.ReportQueryBuilder::BuildReportQuery(string fetchXml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19e0  ret
```
