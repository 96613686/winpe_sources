# Microsoft.Crm.MonitoredStream::.ctor

- ea: `0x17c40`
- end: `0x17c7d`
- name: `Microsoft.Crm.MonitoredStream::.ctor`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18020`
- `0x18060`
- `0x18360`

## string_xrefs

- `0x17c5d`: `maxBytesToReadInOneResponse`

## pseudocode

```c

```

## disassembly

```asm
0x17c40  ldarg.0
0x17c41  call     instance void [mscorlib]System.IO.Stream::.ctor()
0x17c46  ldarg.1
0x17c47  ldstr    aInnerstream// "innerStream"
0x17c4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x17c51  ldarg.2
0x17c52  ldstr    aTrafficmonitor// "trafficMonitor"
0x17c57  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x17c5c  ldarg.3
0x17c5d  ldstr    aMaxbytestoread// "maxBytesToReadInOneResponse"
0x17c62  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x17c67  ldarg.0
0x17c68  ldarg.1
0x17c69  stfld    class [mscorlib]System.IO.Stream Microsoft.Crm.MonitoredStream::_innerStream
0x17c6e  ldarg.0
0x17c6f  ldarg.2
0x17c70  stfld    class Microsoft.Crm.ITrafficMonitor Microsoft.Crm.MonitoredStream::_trafficMonitor
0x17c75  ldarg.0
0x17c76  ldarg.3
0x17c77  stfld    int32 Microsoft.Crm.MonitoredStream::_maxBytesToReadInOneResponse
0x17c7c  ret
```
