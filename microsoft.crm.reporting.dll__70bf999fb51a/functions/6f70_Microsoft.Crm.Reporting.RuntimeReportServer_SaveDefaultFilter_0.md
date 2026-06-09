# Microsoft.Crm.Reporting.RuntimeReportServer::SaveDefaultFilter_0

- ea: `0x6f70`
- end: `0x709d`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::SaveDefaultFilter_0`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x5df0`

## callees

- `0x290`
- `0x2a0`
- `0x4860`
- `0x4970`
- `0x5780`
- `0x6bc0`
- `0x6f70`

## string_xrefs

- `0x6fa5`: `Calling ReportingService.GetItemParameters on: {0}.`
- `0x6fd1`: `GetItemParameters`
- `0x704e`: `Calling ReportingService.SetItemParameters on: {0}.`
- `0x7076`: `SetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x6f70  ldarg.1
0x6f71  ldstr    asc_C3C6// "/"
0x6f76  ldarg.2
0x6f77  call     string [mscorlib]System.String::Concat(string, string, string)
0x6f7c  stloc.0
0x6f7d  ldarg.0
0x6f7e  ldarg.3
0x6f7f  ldarg.s  4
0x6f81  call     instance string Microsoft.Crm.Reporting.RuntimeReportServer::BuildReportQueries(string reportFilterXml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6f86  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6f8b  ldstr    aReportfilterRe_1// "/ReportFilter/ReportEntity"
0x6f90  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6f95  stloc.1
0x6f96  ldnull
0x6f97  stloc.2
0x6f98  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x6f9d  stloc.3
0x6f9e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6fa3  ldc.i4.s 0x20
0x6fa5  ldstr    aCallingReporti_9// "Calling ReportingService.GetItemParamet"...
0x6faa  ldc.i4.1
0x6fab  newarr   [mscorlib]System.Object
0x6fb0  dup
0x6fb1  ldc.i4.0
0x6fb2  ldloc.0
0x6fb3  stelem.ref
0x6fb4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6fb9  ldarg.0
0x6fba  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6fbf  ldloc.0
0x6fc0  ldnull
0x6fc1  ldc.i4.0
0x6fc2  ldnull
0x6fc3  ldnull
0x6fc4  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Microsoft.Crm.Reporting.IReportingService::GetItemParameters(string ItemPath, string HistoryID, bool ForRendering, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Values, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] Credentials)
0x6fc9  stloc.2
0x6fca  leave.s  loc_6FEB
0x6fcc  stloc.s  4
0x6fce  ldarg.0
0x6fcf  ldloc.s  4
0x6fd1  ldstr    aGetitemparamet// "GetItemParameters"
0x6fd6  ldc.i4   0x80048323
0x6fdb  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6fe0  throw
0x6fe1  ldloc.3
0x6fe2  brfalse.s loc_6FEA
0x6fe4  ldloc.3
0x6fe5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6fea  endfinally
0x6feb  ldc.i4.0
0x6fec  stloc.s  5
0x6fee  br.s     loc_7036
0x6ff0  ldloc.1
0x6ff1  ldloc.s  5
0x6ff3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x6ff8  stloc.s  6
0x6ffa  ldloc.s  6
0x6ffc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7001  ldstr    aParamname// "paramname"
0x7006  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x700b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7010  ldloc.2
0x7011  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter Microsoft.Crm.Reporting.RuntimeReportServer::FindReportParameter(string name, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] parameters)
0x7016  dup
0x7017  ldc.i4.1
0x7018  newarr   [mscorlib]System.String
0x701d  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::set_DefaultValues(string[])
0x7022  callvirt instance string[] [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_DefaultValues()
0x7027  ldc.i4.0
0x7028  ldloc.s  6
0x702a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x702f  stelem.ref
0x7030  ldloc.s  5
0x7032  ldc.i4.1
0x7033  add
0x7034  stloc.s  5
0x7036  ldloc.s  5
0x7038  ldloc.1
0x7039  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x703e  blt.s    loc_6FF0
0x7040  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x7045  stloc.s  7
0x7047  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x704c  ldc.i4.s 0x20
0x704e  ldstr    aCallingReporti_10// "Calling ReportingService.SetItemParamet"...
0x7053  ldc.i4.1
0x7054  newarr   [mscorlib]System.Object
0x7059  dup
0x705a  ldc.i4.0
0x705b  ldloc.0
0x705c  stelem.ref
0x705d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7062  ldarg.0
0x7063  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7068  ldloc.0
0x7069  ldloc.2
0x706a  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetItemParameters(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Parameters)
0x706f  leave.s  loc_709C
0x7071  stloc.s  8
0x7073  ldarg.0
0x7074  ldloc.s  8
0x7076  ldstr    aSetitemparamet// "SetItemParameters"
0x707b  ldc.i4   0x80048324
0x7080  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x7085  throw
0x7086  ldloc.s  7
0x7088  brfalse.s loc_7091
0x708a  ldloc.s  7
0x708c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7091  endfinally
0x7092  ldloc.1
0x7093  brfalse.s loc_709B
0x7095  ldloc.1
0x7096  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x709b  endfinally
0x709c  ret
```
