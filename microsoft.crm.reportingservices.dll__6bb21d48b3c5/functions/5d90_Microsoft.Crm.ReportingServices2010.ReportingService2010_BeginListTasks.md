# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListTasks

- ea: `0x5d90`
- end: `0x5da8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListTasks`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5d91`: `ListTasks`

## pseudocode

```c

```

## disassembly

```asm
0x5d90  ldarg.0
0x5d91  ldstr    aListtasks// "ListTasks"
0x5d96  ldc.i4.1
0x5d97  newarr   [mscorlib]System.Object
0x5d9c  dup
0x5d9d  ldc.i4.0
0x5d9e  ldarg.1
0x5d9f  stelem.ref
0x5da0  ldarg.2
0x5da1  ldarg.3
0x5da2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x5da7  ret
```
