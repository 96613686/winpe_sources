# Microsoft.Crm.MonitoredWebRequest::OnBeforeSendingRequest

- ea: `0x17f80`
- end: `0x17ffa`
- name: `Microsoft.Crm.MonitoredWebRequest::OnBeforeSendingRequest`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180b0`
- `0x180d0`

## callees

- `0x17be0`
- `0x18560`
- `0x185a0`
- `0x185c0`
- `0x18610`

## string_xrefs

- `0x17f89`: `Connection already open at the time of calling OnBeforeSendingRequest.`

## pseudocode

```c

```

## disassembly

```asm
0x17f80  ldarg.0
0x17f81  ldfld    int32 Microsoft.Crm.MonitoredWebRequest::_connectionStatus
0x17f86  ldc.i4.0
0x17f87  ceq
0x17f89  ldstr    aConnectionAlre// "Connection already open at the time of "...
0x17f8e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17f93  ldarg.0
0x17f94  ldc.i4.1
0x17f95  stfld    int32 Microsoft.Crm.MonitoredWebRequest::_connectionStatus
0x17f9a  ldarg.0
0x17f9b  ldfld    class Microsoft.Crm.BufferedTrafficMonitor Microsoft.Crm.MonitoredWebRequest::_bufferedMonitor
0x17fa0  ldarg.0
0x17fa1  ldfld    class [System]System.Net.WebRequest Microsoft.Crm.MonitoredWebRequest::_innerRequest
0x17fa6  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0x17fab  callvirt instance string [System]System.Uri::get_Host()
0x17fb0  ldarg.0
0x17fb1  ldfld    class [System]System.Net.WebRequest Microsoft.Crm.MonitoredWebRequest::_innerRequest
0x17fb6  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0x17fbb  callvirt instance int32 [System]System.Uri::get_Port()
0x17fc0  callvirt instance void Microsoft.Crm.BufferedTrafficMonitor::RegisterTargetHost(string hostName, int32 port)
0x17fc5  ldarg.0
0x17fc6  ldfld    class Microsoft.Crm.BufferedTrafficMonitor Microsoft.Crm.MonitoredWebRequest::_bufferedMonitor
0x17fcb  callvirt instance void Microsoft.Crm.BufferedTrafficMonitor::RegisterConnectionOpened()
0x17fd0  ldarg.0
0x17fd1  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x17fd6  ldarg.0
0x17fd7  ldfld    class Microsoft.Crm.BufferedTrafficMonitor Microsoft.Crm.MonitoredWebRequest::_bufferedMonitor
0x17fdc  call     int32 Microsoft.Crm.WebHeaderCollectionExtensions::RegisterAll(class [System]System.Net.WebHeaderCollection headers, class Microsoft.Crm.ITrafficMonitor trafficMonitor)
0x17fe1  stloc.0
0x17fe2  ldarg.0
0x17fe3  ldfld    class Microsoft.Crm.BufferedTrafficMonitor Microsoft.Crm.MonitoredWebRequest::_bufferedMonitor
0x17fe8  ldloc.0
0x17fe9  callvirt instance void Microsoft.Crm.BufferedTrafficMonitor::RegisterBytesSent(int32 countOfBytes)
0x17fee  ldarg.0
0x17fef  ldfld    class Microsoft.Crm.BufferedTrafficMonitor Microsoft.Crm.MonitoredWebRequest::_bufferedMonitor
0x17ff4  callvirt instance void Microsoft.Crm.BufferedTrafficMonitor::Flush()
0x17ff9  ret
```
