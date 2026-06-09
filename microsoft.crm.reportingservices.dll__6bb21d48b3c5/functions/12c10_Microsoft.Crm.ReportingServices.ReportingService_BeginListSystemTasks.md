# Microsoft.Crm.ReportingServices.ReportingService::BeginListSystemTasks

- ea: `0x12c10`
- end: `0x12c24`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginListSystemTasks`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12c11`: `ListSystemTasks`

## pseudocode

```c

```

## disassembly

```asm
0x12c10  ldarg.0
0x12c11  ldstr    aListsystemtask// "ListSystemTasks"
0x12c16  ldc.i4.0
0x12c17  newarr   [mscorlib]System.Object
0x12c1c  ldarg.1
0x12c1d  ldarg.2
0x12c1e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12c23  ret
```
