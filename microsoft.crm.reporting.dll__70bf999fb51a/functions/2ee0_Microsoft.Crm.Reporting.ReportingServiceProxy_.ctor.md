# Microsoft.Crm.Reporting.ReportingServiceProxy::.ctor

- ea: `0x2ee0`
- end: `0x2f52`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::.ctor`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4790`

## callees

- `0x2f60`

## string_xrefs

- `0x2efc`: `{0}/ReportService2010.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x2ee0  ldarg.0
0x2ee1  call     instance void [mscorlib]System.Object::.ctor()
0x2ee6  ldarg.0
0x2ee7  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::.ctor()
0x2eec  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::<ReportingService>k__BackingField
0x2ef1  ldarg.0
0x2ef2  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2ef7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2efc  ldstr    a0Reportservice// "{0}/ReportService2010.asmx"
0x2f01  ldc.i4.1
0x2f02  newarr   [mscorlib]System.Object
0x2f07  dup
0x2f08  ldc.i4.0
0x2f09  ldarg.1
0x2f0a  stelem.ref
0x2f0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f10  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x2f15  ldarg.0
0x2f16  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f1b  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetNormalTimeout()
0x2f20  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Timeout(int32)
0x2f25  ldarg.0
0x2f26  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f2b  call     class [System]System.Net.ICredentials [System]System.Net.CredentialCache::get_DefaultCredentials()
0x2f30  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Credentials(class [System]System.Net.ICredentials)
0x2f35  ldarg.0
0x2f36  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f3b  ldc.i4.1
0x2f3c  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.HttpWebClientProtocol::set_UnsafeAuthenticatedConnectionSharing(bool)
0x2f41  ldarg.0
0x2f42  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f47  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::GetConnectionGroupName()
0x2f4c  callvirt instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_ConnectionGroupName(string)
0x2f51  ret
```
