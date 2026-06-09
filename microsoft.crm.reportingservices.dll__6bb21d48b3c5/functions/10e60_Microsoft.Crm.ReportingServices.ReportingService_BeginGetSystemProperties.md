# Microsoft.Crm.ReportingServices.ReportingService::BeginGetSystemProperties

- ea: `0x10e60`
- end: `0x10e78`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginGetSystemProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10e61`: `GetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x10e60  ldarg.0
0x10e61  ldstr    aGetsystemprope// "GetSystemProperties"
0x10e66  ldc.i4.1
0x10e67  newarr   [mscorlib]System.Object
0x10e6c  dup
0x10e6d  ldc.i4.0
0x10e6e  ldarg.1
0x10e6f  stelem.ref
0x10e70  ldarg.2
0x10e71  ldarg.3
0x10e72  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x10e77  ret
```
