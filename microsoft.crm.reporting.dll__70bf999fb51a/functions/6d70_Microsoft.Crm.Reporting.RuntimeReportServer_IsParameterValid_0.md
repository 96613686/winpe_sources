# Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid_0

- ea: `0x6d70`
- end: `0x6e67`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid_0`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6000`

## callees

- `0x290`
- `0x4860`
- `0x4970`
- `0x6bc0`
- `0x6bf0`
- `0x6d70`

## string_xrefs

- `0x6e14`: `Calling ReportingService.GetItemParameters on: {0}.`
- `0x6dd7`: `GetItemParameters`
- `0x6e40`: `GetItemParameters`
- `0x6d7b`: `Calling ReportingService.GetReportParameters on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6d70  ldc.i4.0
0x6d71  stloc.0
0x6d72  ldnull
0x6d73  stloc.1
0x6d74  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6d79  ldc.i4.s 0x20
0x6d7b  ldstr    aCallingReporti_16// "Calling ReportingService.GetReportParam"...
0x6d80  ldc.i4.1
0x6d81  newarr   [mscorlib]System.Object
0x6d86  dup
0x6d87  ldc.i4.0
0x6d88  ldarg.2
0x6d89  stelem.ref
0x6d8a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d8f  ldarg.0
0x6d90  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6d95  ldarg.2
0x6d96  ldnull
0x6d97  ldc.i4.1
0x6d98  ldc.i4.1
0x6d99  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue
0x6d9e  dup
0x6d9f  ldc.i4.0
0x6da0  ldarg.1
0x6da1  stelem.ref
0x6da2  ldnull
0x6da3  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Microsoft.Crm.Reporting.IReportingService::GetItemParameters(string ItemPath, string HistoryID, bool ForRendering, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Values, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] Credentials)
0x6da8  stloc.1
0x6da9  leave.s  loc_6DE9
0x6dab  stloc.3
0x6dac  ldloc.3
0x6dad  stloc.s  4
0x6daf  ldloc.s  4
0x6db1  brfalse.s loc_6DD5
0x6db3  ldloc.s  4
0x6db5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x6dba  ldstr    aErrorcode// "ErrorCode"
0x6dbf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dc4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dc9  ldstr    aRsreportparame// "rsReportParameterTypeMismatch"
0x6dce  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6dd3  brfalse.s loc_6DE7
0x6dd5  ldarg.0
0x6dd6  ldloc.3
0x6dd7  ldstr    aGetitemparamet// "GetItemParameters"
0x6ddc  ldc.i4   0x80048329
0x6de1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6de6  throw
0x6de7  leave.s  loc_6DE9
0x6de9  ldnull
0x6dea  stloc.2
0x6deb  ldloc.1
0x6dec  brfalse.s loc_6E0D
0x6dee  ldarg.1
0x6def  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Name()
0x6df4  ldloc.1
0x6df5  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter Microsoft.Crm.Reporting.RuntimeReportServer::FindReportParameter(string name, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] parameters)
0x6dfa  stloc.2
0x6dfb  ldarg.1
0x6dfc  ldloc.2
0x6dfd  call     bool Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue pv, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter rp)
0x6e02  stloc.0
0x6e03  ldarg.3
0x6e04  ldloc.2
0x6e05  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_Prompt()
0x6e0a  stind.ref
0x6e0b  br.s     loc_6E65
0x6e0d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6e12  ldc.i4.s 0x20
0x6e14  ldstr    aCallingReporti_9// "Calling ReportingService.GetItemParamet"...
0x6e19  ldc.i4.1
0x6e1a  newarr   [mscorlib]System.Object
0x6e1f  dup
0x6e20  ldc.i4.0
0x6e21  ldarg.2
0x6e22  stelem.ref
0x6e23  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e28  ldarg.0
0x6e29  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6e2e  ldarg.2
0x6e2f  ldnull
0x6e30  ldc.i4.1
0x6e31  ldnull
0x6e32  ldnull
0x6e33  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Microsoft.Crm.Reporting.IReportingService::GetItemParameters(string ItemPath, string HistoryID, bool ForRendering, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Values, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] Credentials)
0x6e38  stloc.1
0x6e39  leave.s  loc_6E50
0x6e3b  stloc.s  5
0x6e3d  ldarg.0
0x6e3e  ldloc.s  5
0x6e40  ldstr    aGetitemparamet// "GetItemParameters"
0x6e45  ldc.i4   0x80048323
0x6e4a  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6e4f  throw
0x6e50  ldarg.1
0x6e51  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Name()
0x6e56  ldloc.1
0x6e57  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter Microsoft.Crm.Reporting.RuntimeReportServer::FindReportParameter(string name, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] parameters)
0x6e5c  stloc.2
0x6e5d  ldarg.3
0x6e5e  ldloc.2
0x6e5f  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_Prompt()
0x6e64  stind.ref
0x6e65  ldloc.0
0x6e66  ret
```
