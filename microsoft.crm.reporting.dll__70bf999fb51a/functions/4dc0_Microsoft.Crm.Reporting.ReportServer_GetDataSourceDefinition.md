# Microsoft.Crm.Reporting.ReportServer::GetDataSourceDefinition

- ea: `0x4dc0`
- end: `0x4eed`
- name: `Microsoft.Crm.Reporting.ReportServer::GetDataSourceDefinition`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x4ce0`

## callees

- `0x1c0`
- `0x200`
- `0x4860`
- `0x4970`
- `0x4dc0`

## string_xrefs

- `0x4dcd`: `Calling ReportingService.GetDataSourceContents on: {0}.`
- `0x4e04`: `Calling ReportingService.GetDataSourceContents on {0} failed in trial {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4dc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x4dc5  stloc.0
0x4dc6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4dcb  ldc.i4.s 0x20
0x4dcd  ldstr    aCallingReporti_2// "Calling ReportingService.GetDataSourceC"...
0x4dd2  ldc.i4.1
0x4dd3  newarr   [mscorlib]System.Object
0x4dd8  dup
0x4dd9  ldc.i4.0
0x4dda  ldarg.1
0x4ddb  stelem.ref
0x4ddc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4de1  ldc.i4.1
0x4de2  stloc.1
0x4de3  br       loc_4ED6
0x4de8  nop
0x4de9  ldarg.0
0x4dea  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4def  ldarg.1
0x4df0  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition Microsoft.Crm.Reporting.IReportingService::GetDataSourceContents(string DataSource)
0x4df5  stloc.2
0x4df6  leave    loc_4EEB
0x4dfb  stloc.3
0x4dfc  ldloc.3
0x4dfd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4e02  ldc.i4.s 0x20
0x4e04  ldstr    aCallingReporti_3// "Calling ReportingService.GetDataSourceC"...
0x4e09  ldc.i4.2
0x4e0a  newarr   [mscorlib]System.Object
0x4e0f  dup
0x4e10  ldc.i4.0
0x4e11  ldarg.1
0x4e12  stelem.ref
0x4e13  dup
0x4e14  ldc.i4.1
0x4e15  ldloc.1
0x4e16  box      [mscorlib]System.Int32
0x4e1b  stelem.ref
0x4e1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e21  ldarg.0
0x4e22  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4e27  brfalse.s loc_4E36
0x4e29  ldarg.0
0x4e2a  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4e2f  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x4e34  brtrue.s loc_4E3D
0x4e36  ldstr    aNotfound// "[NotFound]"
0x4e3b  br.s     loc_4E48
0x4e3d  ldarg.0
0x4e3e  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4e43  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x4e48  stloc.s  4
0x4e4a  ldloc.3
0x4e4b  brfalse.s loc_4E5F
0x4e4d  ldloc.3
0x4e4e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x4e53  ldstr    aMessage// "Message"
0x4e58  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4e5d  brtrue.s loc_4E66
0x4e5f  ldstr    aNotfound// "[NotFound]"
0x4e64  br.s     loc_4E7B
0x4e66  ldloc.3
0x4e67  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x4e6c  ldstr    aMessage// "Message"
0x4e71  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4e76  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4e7b  stloc.s  5
0x4e7d  ldstr    aMscrmreporting// "MSCRMReporting"
0x4e82  ldc.i4   0xC0004E01
0x4e87  conv.u8
0x4e88  ldc.i4.3
0x4e89  newarr   [mscorlib]System.String
0x4e8e  dup
0x4e8f  ldc.i4.0
0x4e90  ldstr    aGetdatasourcec// "GetDataSourceContents"
0x4e95  stelem.ref
0x4e96  dup
0x4e97  ldc.i4.1
0x4e98  ldloc.s  4
0x4e9a  stelem.ref
0x4e9b  dup
0x4e9c  ldc.i4.2
0x4e9d  ldloc.s  5
0x4e9f  stelem.ref
0x4ea0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0x4ea5  ldloc.1
0x4ea6  ldc.i4.3
0x4ea7  bge.s    loc_4EAB
0x4ea9  leave.s  loc_4ED2
0x4eab  ldarg.0
0x4eac  ldloc.3
0x4ead  ldstr    aGetdatasourcec// "GetDataSourceContents"
0x4eb2  ldc.i4   0x8004831A
0x4eb7  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x4ebc  throw
0x4ebd  stloc.s  6
0x4ebf  ldarg.0
0x4ec0  ldloc.s  6
0x4ec2  ldstr    aGetdatasourcec// "GetDataSourceContents"
0x4ec7  ldc.i4   0x8004831A
0x4ecc  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x4ed1  throw
0x4ed2  ldloc.1
0x4ed3  ldc.i4.1
0x4ed4  add
0x4ed5  stloc.1
0x4ed6  ldloc.1
0x4ed7  ldc.i4.3
0x4ed8  ble      loc_4DE8
0x4edd  ldnull
0x4ede  stloc.2
0x4edf  leave.s  loc_4EEB
0x4ee1  ldloc.0
0x4ee2  brfalse.s loc_4EEA
0x4ee4  ldloc.0
0x4ee5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4eea  endfinally
0x4eeb  ldloc.2
0x4eec  ret
```
