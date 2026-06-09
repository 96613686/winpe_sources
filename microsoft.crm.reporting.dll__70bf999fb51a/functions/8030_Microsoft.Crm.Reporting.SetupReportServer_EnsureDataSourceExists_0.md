# Microsoft.Crm.Reporting.SetupReportServer::EnsureDataSourceExists_0

- ea: `0x8030`
- end: `0x8105`
- name: `Microsoft.Crm.Reporting.SetupReportServer::EnsureDataSourceExists_0`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7fd0`
- `0x8000`

## callees

- `0x1f0`
- `0x210`
- `0x4860`
- `0x4960`
- `0x4ef0`
- `0x7a30`
- `0x7fa0`
- `0x8030`

## string_xrefs

- `0x8065`: `Calling ReportingService.CreateDataSource on: {0}.`
- `0x80af`: `rsItemAlreadyExists`
- `0x80bd`: `CreateDataSource`
- `0x80d1`: `Calling ReportingService.SetDataSourceContents on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x8030  ldarg.0
0x8031  ldarg.3
0x8032  call     instance string Microsoft.Crm.Reporting.ReportServer::GetSharedDataSourceName(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x8037  stloc.0
0x8038  ldc.i4.1
0x8039  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x803e  dup
0x803f  ldc.i4.0
0x8040  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property Microsoft.Crm.Reporting.SetupReportServer::CreateHiddenProperty()
0x8045  stelem.ref
0x8046  stloc.1
0x8047  ldarg.1
0x8048  ldstr    asc_C3C6// "/"
0x804d  ldloc.0
0x804e  call     string [mscorlib]System.String::Concat(string, string, string)
0x8053  stloc.2
0x8054  ldarg.0
0x8055  ldarg.1
0x8056  ldloc.0
0x8057  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::DataSourceExists(string path, string dataSourceName)
0x805c  brtrue.s loc_80CA
0x805e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8063  ldc.i4.s 0x20
0x8065  ldstr    aCallingReporti_24// "Calling ReportingService.CreateDataSour"...
0x806a  ldc.i4.1
0x806b  newarr   [mscorlib]System.Object
0x8070  dup
0x8071  ldc.i4.0
0x8072  ldloc.2
0x8073  stelem.ref
0x8074  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8079  ldarg.0
0x807a  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x807f  ldloc.0
0x8080  ldarg.1
0x8081  ldc.i4.0
0x8082  ldarg.2
0x8083  ldloc.1
0x8084  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem Microsoft.Crm.Reporting.IReportingService::CreateDataSource(string DataSource, string Parent, bool Overwrite, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition Definition, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] Properties)
0x8089  pop
0x808a  leave.s  loc_8104
0x808c  stloc.3
0x808d  ldloc.3
0x808e  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x8093  stloc.s  4
0x8095  ldloc.s  4
0x8097  brfalse.s loc_80BB
0x8099  ldloc.s  4
0x809b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x80a0  ldstr    aErrorcode// "ErrorCode"
0x80a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x80aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x80af  ldstr    aRsitemalreadye// "rsItemAlreadyExists"
0x80b4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x80b9  brfalse.s loc_80C8
0x80bb  ldarg.0
0x80bc  ldloc.3
0x80bd  ldstr    aCreatedatasour// "CreateDataSource"
0x80c2  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x80c7  throw
0x80c8  leave.s  loc_8104
0x80ca  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x80cf  ldc.i4.s 0x20
0x80d1  ldstr    aCallingReporti_25// "Calling ReportingService.SetDataSourceC"...
0x80d6  ldc.i4.1
0x80d7  newarr   [mscorlib]System.Object
0x80dc  dup
0x80dd  ldc.i4.0
0x80de  ldloc.2
0x80df  stelem.ref
0x80e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x80e5  ldarg.0
0x80e6  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x80eb  ldloc.2
0x80ec  ldarg.2
0x80ed  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetDataSourceContents(string DataSource, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition Definition)
0x80f2  leave.s  loc_8104
0x80f4  stloc.s  5
0x80f6  ldarg.0
0x80f7  ldloc.s  5
0x80f9  ldstr    aSetdatasourcec// "SetDataSourceContents"
0x80fe  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x8103  throw
0x8104  ret
```
