# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::GetWebRequest

- ea: `0x13b00`
- end: `0x13b8b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::GetWebRequest`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x13b00`
- `0x13c50`
- `0x13cb0`
- `0x13cd0`
- `0x13d10`
- `0x4e480`
- `0x797b0`

## string_xrefs

- `0x13b34`: `Server-Side Synchronization: Web Connection Success`

## pseudocode

```c

```

## disassembly

```asm
0x13b00  ldarg.0
0x13b01  ldarg.1
0x13b02  call     instance class [System]System.Net.WebRequest [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::GetWebRequest(class [System]System.Uri)
0x13b07  stloc.0
0x13b08  ldloc.0
0x13b09  isinst   [System]System.Net.HttpWebRequest
0x13b0e  stloc.1
0x13b0f  ldloc.1
0x13b10  brfalse.s loc_13B58
0x13b12  ldloc.1
0x13b13  callvirt instance class [System]System.Net.ServicePoint [System]System.Net.HttpWebRequest::get_ServicePoint()
0x13b18  ldc.i4   0x7FFFFFFF
0x13b1d  callvirt instance void [System]System.Net.ServicePoint::set_ConnectionLimit(int32)
0x13b22  ldloc.1
0x13b23  ldc.i4.0
0x13b24  callvirt instance void [System]System.Net.HttpWebRequest::set_KeepAlive(bool)
0x13b29  ldloc.1
0x13b2a  ldsfld   class [mscorlib]System.Version [System]System.Net.HttpVersion::Version10
0x13b2f  callvirt instance void [System]System.Net.HttpWebRequest::set_ProtocolVersion(class [mscorlib]System.Version)
0x13b34  ldstr    aServerSideSync_3// "Server-Side Synchronization: Web Connec"...
0x13b39  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x13b3e  ldarg.0
0x13b3f  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::get_CloseConnectionGroupBeforeWebRequest()
0x13b44  brfalse.s loc_13B58
0x13b46  ldloc.1
0x13b47  callvirt instance class [System]System.Net.ServicePoint [System]System.Net.HttpWebRequest::get_ServicePoint()
0x13b4c  ldarg.0
0x13b4d  call     instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_ConnectionGroupName()
0x13b52  callvirt instance bool [System]System.Net.ServicePoint::CloseConnectionGroup(string)
0x13b57  pop
0x13b58  ldarg.0
0x13b59  ldloc.0
0x13b5a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::AddAdditionalRequestHeaders(class [System]System.Net.WebRequest request)
0x13b5f  ldarg.0
0x13b60  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::_isFirstRequest
0x13b65  brtrue.s loc_13B6E
0x13b67  ldarg.0
0x13b68  ldloc.0
0x13b69  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::AddClientStatisticsHeader(class [System]System.Net.WebRequest request)
0x13b6e  ldarg.0
0x13b6f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::get_NetworkTrafficMonitor()
0x13b74  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::get_ProtocolHeaders()
0x13b79  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Clear()
0x13b7e  ldloc.0
0x13b7f  ldarg.0
0x13b80  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::get_NetworkTrafficMonitor()
0x13b85  newobj   instance void [Microsoft.Crm]Microsoft.Crm.MonitoredWebRequest::.ctor(class [System]System.Net.WebRequest, class [Microsoft.Crm]Microsoft.Crm.ITrafficMonitor)
0x13b8a  ret
```
