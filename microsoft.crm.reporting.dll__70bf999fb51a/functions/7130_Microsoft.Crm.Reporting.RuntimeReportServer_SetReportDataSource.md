# Microsoft.Crm.Reporting.RuntimeReportServer::SetReportDataSource

- ea: `0x7130`
- end: `0x7289`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::SetReportDataSource`
- size: `345`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d40`
- `0x64c0`

## callees

- `0x1c0`
- `0x240`
- `0x4860`
- `0x4970`
- `0x6810`
- `0x7130`
- `0x74c0`

## string_xrefs

- `0x714d`: `Calling ReportingService.SetItemDataSources on: {0}.`
- `0x718c`: `Calling ReportingService.SetItemDataSources on {0} failed in trial {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7130  ldarg.0
0x7131  ldarg.1
0x7132  ldarg.2
0x7133  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] Microsoft.Crm.Reporting.RuntimeReportServer::CreateReportDataSource(class Microsoft.Crm.Reporting.SRSReport report, string path)
0x7138  stloc.0
0x7139  ldarg.2
0x713a  ldstr    asc_C3C6// "/"
0x713f  ldarg.3
0x7140  call     string [mscorlib]System.String::Concat(string, string, string)
0x7145  stloc.1
0x7146  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x714b  ldc.i4.s 0x20
0x714d  ldstr    aCallingReporti_8// "Calling ReportingService.SetItemDataSou"...
0x7152  ldc.i4.1
0x7153  newarr   [mscorlib]System.Object
0x7158  dup
0x7159  ldc.i4.0
0x715a  ldloc.1
0x715b  stelem.ref
0x715c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7161  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x7166  stloc.2
0x7167  ldc.i4.1
0x7168  stloc.3
0x7169  br       loc_7275
0x716e  nop
0x716f  ldarg.0
0x7170  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7175  ldloc.1
0x7176  ldloc.0
0x7177  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetItemDataSources(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] DataSources)
0x717c  leave    loc_7288
0x7181  stloc.s  4
0x7183  ldloc.s  4
0x7185  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x718a  ldc.i4.s 0x20
0x718c  ldstr    aCallingReporti_18// "Calling ReportingService.SetItemDataSou"...
0x7191  ldc.i4.2
0x7192  newarr   [mscorlib]System.Object
0x7197  dup
0x7198  ldc.i4.0
0x7199  ldloc.1
0x719a  stelem.ref
0x719b  dup
0x719c  ldc.i4.1
0x719d  ldloc.3
0x719e  box      [mscorlib]System.Int32
0x71a3  stelem.ref
0x71a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x71a9  ldarg.0
0x71aa  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x71af  brfalse.s loc_71BE
0x71b1  ldarg.0
0x71b2  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x71b7  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x71bc  brtrue.s loc_71C5
0x71be  ldstr    aNotfound// "[NotFound]"
0x71c3  br.s     loc_71D0
0x71c5  ldarg.0
0x71c6  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x71cb  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x71d0  stloc.s  5
0x71d2  ldloc.s  4
0x71d4  brfalse.s loc_71E9
0x71d6  ldloc.s  4
0x71d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x71dd  ldstr    aMessage// "Message"
0x71e2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x71e7  brtrue.s loc_71F0
0x71e9  ldstr    aNotfound// "[NotFound]"
0x71ee  br.s     loc_7206
0x71f0  ldloc.s  4
0x71f2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x71f7  ldstr    aMessage// "Message"
0x71fc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7201  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7206  stloc.s  6
0x7208  ldstr    aMscrmreporting// "MSCRMReporting"
0x720d  ldc.i4   0xC0004E01
0x7212  conv.u8
0x7213  ldc.i4.3
0x7214  newarr   [mscorlib]System.String
0x7219  dup
0x721a  ldc.i4.0
0x721b  ldstr    aSetitemdatasou// "SetItemDataSources"
0x7220  stelem.ref
0x7221  dup
0x7222  ldc.i4.1
0x7223  ldloc.s  5
0x7225  stelem.ref
0x7226  dup
0x7227  ldc.i4.2
0x7228  ldloc.s  6
0x722a  stelem.ref
0x722b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0x7230  ldloc.3
0x7231  ldc.i4.3
0x7232  clt
0x7234  ldarg.s  4
0x7236  or
0x7237  brfalse.s loc_723B
0x7239  leave.s  loc_7271
0x723b  ldarg.0
0x723c  ldloc.s  4
0x723e  ldstr    aSetitemdatasou// "SetItemDataSources"
0x7243  ldarg.0
0x7244  ldloc.s  4
0x7246  call     instance int32 Microsoft.Crm.Reporting.RuntimeReportServer::GetExceptionErrorCode(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception)
0x724b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x7250  throw
0x7251  stloc.s  7
0x7253  ldloc.3
0x7254  ldc.i4.3
0x7255  clt
0x7257  ldarg.s  4
0x7259  or
0x725a  brfalse.s loc_725E
0x725c  leave.s  loc_7271
0x725e  ldarg.0
0x725f  ldloc.s  7
0x7261  ldstr    aSetitemdatasou// "SetItemDataSources"
0x7266  ldc.i4   0x80048322
0x726b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x7270  throw
0x7271  ldloc.3
0x7272  ldc.i4.1
0x7273  add
0x7274  stloc.3
0x7275  ldloc.3
0x7276  ldc.i4.3
0x7277  ble      loc_716E
0x727c  leave.s  loc_7288
0x727e  ldloc.2
0x727f  brfalse.s loc_7287
0x7281  ldloc.2
0x7282  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7287  endfinally
0x7288  ret
```
