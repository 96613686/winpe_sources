# Microsoft.Crm.ReportingServices.ReportingService::BeginSetSystemProperties

- ea: `0x10eb0`
- end: `0x10ec8`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginSetSystemProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10eb1`: `SetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x10eb0  ldarg.0
0x10eb1  ldstr    aSetsystemprope// "SetSystemProperties"
0x10eb6  ldc.i4.1
0x10eb7  newarr   [mscorlib]System.Object
0x10ebc  dup
0x10ebd  ldc.i4.0
0x10ebe  ldarg.1
0x10ebf  stelem.ref
0x10ec0  ldarg.2
0x10ec1  ldarg.3
0x10ec2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x10ec7  ret
```
