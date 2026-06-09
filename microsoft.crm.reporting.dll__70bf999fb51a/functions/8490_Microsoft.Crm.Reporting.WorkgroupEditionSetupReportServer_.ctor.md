# Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::.ctor

- ea: `0x8490`
- end: `0x850f`
- name: `Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::.ctor`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7560`

## callees

- `0x1d0`
- `0x1e0`
- `0x4860`
- `0x7550`

## string_xrefs

- `0x84ad`: `{0}/ReportService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x8490  ldarg.0
0x8491  ldarg.1
0x8492  call     instance void Microsoft.Crm.Reporting.SetupReportServer::.ctor(class [System]System.Uri reportServerUrl)
0x8497  ldarg.0
0x8498  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService::.ctor()
0x849d  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x84a2  ldarg.0
0x84a3  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x84a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84ad  ldstr    a0Reportservice_0// "{0}/ReportService.asmx"
0x84b2  ldc.i4.1
0x84b3  newarr   [mscorlib]System.Object
0x84b8  dup
0x84b9  ldc.i4.0
0x84ba  ldarg.1
0x84bb  stelem.ref
0x84bc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x84c1  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x84c6  ldarg.0
0x84c7  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x84cc  ldarg.0
0x84cd  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x84d2  callvirt instance int32 Microsoft.Crm.Reporting.IReportingService::get_Timeout()
0x84d7  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Timeout(int32)
0x84dc  ldarg.0
0x84dd  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x84e2  ldarg.0
0x84e3  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x84e8  callvirt instance class [System]System.Net.ICredentials Microsoft.Crm.Reporting.IReportingService::get_Credentials()
0x84ed  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Credentials(class [System]System.Net.ICredentials)
0x84f2  ldarg.0
0x84f3  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x84f8  ldc.i4.1
0x84f9  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.HttpWebClientProtocol::set_UnsafeAuthenticatedConnectionSharing(bool)
0x84fe  ldarg.0
0x84ff  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x8504  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::GetConnectionGroupName()
0x8509  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_ConnectionGroupName(string)
0x850e  ret
```
