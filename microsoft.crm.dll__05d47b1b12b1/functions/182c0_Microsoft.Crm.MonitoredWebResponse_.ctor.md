# Microsoft.Crm.MonitoredWebResponse::.ctor

- ea: `0x182c0`
- end: `0x18355`
- name: `Microsoft.Crm.MonitoredWebResponse::.ctor`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x17be0`
- `0x182c0`
- `0x18460`

## string_xrefs

- `0x182dd`: `maxBytesToReadFromResponse`

## pseudocode

```c

```

## disassembly

```asm
0x182c0  ldarg.0
0x182c1  call     instance void [System]System.Net.WebResponse::.ctor()
0x182c6  ldarg.1
0x182c7  ldstr    aInnerresponse// "innerResponse"
0x182cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x182d1  ldarg.2
0x182d2  ldstr    aTrafficmonitor// "trafficMonitor"
0x182d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x182dc  ldarg.3
0x182dd  ldstr    aMaxbytestoread_0// "maxBytesToReadFromResponse"
0x182e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x182e7  ldarg.0
0x182e8  ldarg.1
0x182e9  stfld    class [System]System.Net.WebResponse Microsoft.Crm.MonitoredWebResponse::_innerResponse
0x182ee  ldarg.0
0x182ef  ldarg.2
0x182f0  stfld    class Microsoft.Crm.ITrafficMonitor Microsoft.Crm.MonitoredWebResponse::_trafficMonitor
0x182f5  ldarg.0
0x182f6  ldfld    class [System]System.Net.WebResponse Microsoft.Crm.MonitoredWebResponse::_innerResponse
0x182fb  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebResponse::get_Headers()
0x18300  ldarg.2
0x18301  call     int32 Microsoft.Crm.WebHeaderCollectionExtensions::RegisterAll(class [System]System.Net.WebHeaderCollection headers, class Microsoft.Crm.ITrafficMonitor trafficMonitor)
0x18306  stloc.0
0x18307  ldarg.0
0x18308  ldfld    class Microsoft.Crm.ITrafficMonitor Microsoft.Crm.MonitoredWebResponse::_trafficMonitor
0x1830d  ldloc.0
0x1830e  callvirt instance void Microsoft.Crm.ITrafficMonitor::RegisterBytesReceived(int32 countOfBytes)
0x18313  ldarg.0
0x18314  ldarg.3
0x18315  ldloc.0
0x18316  sub
0x18317  stfld    int32 Microsoft.Crm.MonitoredWebResponse::_maxBytesToReadFromResponseStream
0x1831c  ldarg.0
0x1831d  ldfld    int32 Microsoft.Crm.MonitoredWebResponse::_maxBytesToReadFromResponseStream
0x18322  ldc.i4.0
0x18323  bge.s    loc_18354
0x18325  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1832a  ldstr    aTotalSizeOfRes// "Total size of response headers ({0} byt"...
0x1832f  ldc.i4.2
0x18330  newarr   [mscorlib]System.Object
0x18335  dup
0x18336  ldc.i4.0
0x18337  ldloc.0
0x18338  box      [mscorlib]System.Int32
0x1833d  stelem.ref
0x1833e  dup
0x1833f  ldc.i4.1
0x18340  ldarg.3
0x18341  box      [mscorlib]System.Int32
0x18346  stelem.ref
0x18347  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1834c  ldc.i4.s 0x11
0x1834e  newobj   instance void [System]System.Net.WebException::.ctor(string, valuetype [System]System.Net.WebExceptionStatus)
0x18353  throw
0x18354  ret
```
