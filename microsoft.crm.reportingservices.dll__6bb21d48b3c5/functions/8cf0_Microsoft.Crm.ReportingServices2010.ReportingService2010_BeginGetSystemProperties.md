# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetSystemProperties

- ea: `0x8cf0`
- end: `0x8d08`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetSystemProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8cf1`: `GetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x8cf0  ldarg.0
0x8cf1  ldstr    aGetsystemprope// "GetSystemProperties"
0x8cf6  ldc.i4.1
0x8cf7  newarr   [mscorlib]System.Object
0x8cfc  dup
0x8cfd  ldc.i4.0
0x8cfe  ldarg.1
0x8cff  stelem.ref
0x8d00  ldarg.2
0x8d01  ldarg.3
0x8d02  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8d07  ret
```
