# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetSystemProperties

- ea: `0x8c10`
- end: `0x8c28`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetSystemProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8c11`: `SetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x8c10  ldarg.0
0x8c11  ldstr    aSetsystemprope// "SetSystemProperties"
0x8c16  ldc.i4.1
0x8c17  newarr   [mscorlib]System.Object
0x8c1c  dup
0x8c1d  ldc.i4.0
0x8c1e  ldarg.1
0x8c1f  stelem.ref
0x8c20  ldarg.2
0x8c21  ldarg.3
0x8c22  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8c27  ret
```
