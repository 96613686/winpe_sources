# Microsoft.Crm.ReportingServices.ReportingService::BeginSetCacheOptions

- ea: `0x11980`
- end: `0x119a7`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginSetCacheOptions`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11981`: `SetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x11980  ldarg.0
0x11981  ldstr    aSetcacheoption// "SetCacheOptions"
0x11986  ldc.i4.3
0x11987  newarr   [mscorlib]System.Object
0x1198c  dup
0x1198d  ldc.i4.0
0x1198e  ldarg.1
0x1198f  stelem.ref
0x11990  dup
0x11991  ldc.i4.1
0x11992  ldarg.2
0x11993  box      [mscorlib]System.Boolean
0x11998  stelem.ref
0x11999  dup
0x1199a  ldc.i4.2
0x1199b  ldarg.3
0x1199c  stelem.ref
0x1199d  ldarg.s  4
0x1199f  ldarg.s  5
0x119a1  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x119a6  ret
```
