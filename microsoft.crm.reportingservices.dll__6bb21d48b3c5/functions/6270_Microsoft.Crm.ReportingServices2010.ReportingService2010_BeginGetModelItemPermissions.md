# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetModelItemPermissions

- ea: `0x6270`
- end: `0x628d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetModelItemPermissions`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6271`: `GetModelItemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x6270  ldarg.0
0x6271  ldstr    aGetmodelitempe// "GetModelItemPermissions"
0x6276  ldc.i4.2
0x6277  newarr   [mscorlib]System.Object
0x627c  dup
0x627d  ldc.i4.0
0x627e  ldarg.1
0x627f  stelem.ref
0x6280  dup
0x6281  ldc.i4.1
0x6282  ldarg.2
0x6283  stelem.ref
0x6284  ldarg.3
0x6285  ldarg.s  4
0x6287  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x628c  ret
```
