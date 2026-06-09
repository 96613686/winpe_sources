# Microsoft.Crm.ReportingServices.ReportingService::FlushCache

- ea: `0x11a80`
- end: `0x11a97`
- name: `Microsoft.Crm.ReportingServices.ReportingService::FlushCache`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11a81`: `FlushCache`

## pseudocode

```c

```

## disassembly

```asm
0x11a80  ldarg.0
0x11a81  ldstr    aFlushcache// "FlushCache"
0x11a86  ldc.i4.1
0x11a87  newarr   [mscorlib]System.Object
0x11a8c  dup
0x11a8d  ldc.i4.0
0x11a8e  ldarg.1
0x11a8f  stelem.ref
0x11a90  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x11a95  pop
0x11a96  ret
```
