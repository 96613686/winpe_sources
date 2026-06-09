# Microsoft.Crm.Reporting.SRSReport::FindDataSourceDataProviderType

- ea: `0x8d0`
- end: `0x9ac`
- name: `Microsoft.Crm.Reporting.SRSReport::FindDataSourceDataProviderType`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x810`
- `0xb00`

## callees

- `0x8d0`
- `0x8700`

## pseudocode

```c

```

## disassembly

```asm
0x8d0  ldarg.1
0x8d1  ldstr    aDatasourcerefe// "DataSourceReference"
0x8d6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x8db  stloc.0
0x8dc  ldloc.0
0x8dd  brfalse.s loc_918
0x8df  ldloc.0
0x8e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8e5  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SharedFetchDataSourceName
0x8ea  ldc.i4.5
0x8eb  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8f0  brfalse.s loc_8FA
0x8f2  ldarg.2
0x8f3  ldc.i4.1
0x8f4  callvirt instance void ResultProcessor::Invoke(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x8f9  ret
0x8fa  ldloc.0
0x8fb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x900  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SharedSqlDataSourceName
0x905  ldc.i4.5
0x906  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x90b  brfalse  loc_9AB
0x910  ldarg.2
0x911  ldc.i4.0
0x912  callvirt instance void ResultProcessor::Invoke(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x917  ret
0x918  ldarg.1
0x919  ldstr    aConnectionprop// "ConnectionProperties"
0x91e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x923  dup
0x924  ldstr    aConnprop// "connProp"
0x929  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x92e  dup
0x92f  ldstr    aDataprovider// "DataProvider"
0x934  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x939  stloc.1
0x93a  ldstr    aConnectstring// "ConnectString"
0x93f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x944  stloc.2
0x945  ldloc.1
0x946  ldstr    aDataprovider_0// "dataProvider"
0x94b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x950  ldloc.2
0x951  ldstr    aConnstring// "connString"
0x956  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x95b  ldloc.1
0x95c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x961  ldstr    aMscrmfetch// "MSCRMFETCH"
0x966  call     bool [mscorlib]System.String::op_Equality(string, string)
0x96b  brfalse.s loc_975
0x96d  ldarg.2
0x96e  ldc.i4.1
0x96f  callvirt instance void ResultProcessor::Invoke(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x974  ret
0x975  ldloc.1
0x976  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x97b  ldstr    aSql// "SQL"
0x980  call     bool [mscorlib]System.String::op_Equality(string, string)
0x985  brfalse.s loc_9AB
0x987  ldstr    aInitialCatalog// "initial catalog=.*_MSCRM"
0x98c  ldc.i4.1
0x98d  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x992  ldloc.2
0x993  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x998  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x99d  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x9a2  brfalse.s loc_9AB
0x9a4  ldarg.2
0x9a5  ldc.i4.0
0x9a6  callvirt instance void ResultProcessor::Invoke(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x9ab  ret
```
