# Microsoft.Crm.ReportingServices.ReportingService::ListSystemTasks

- ea: `0x12bf0`
- end: `0x12c09`
- name: `Microsoft.Crm.ReportingServices.ReportingService::ListSystemTasks`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12bf1`: `ListSystemTasks`

## pseudocode

```c

```

## disassembly

```asm
0x12bf0  ldarg.0
0x12bf1  ldstr    aListsystemtask// "ListSystemTasks"
0x12bf6  ldc.i4.0
0x12bf7  newarr   [mscorlib]System.Object
0x12bfc  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12c01  ldc.i4.0
0x12c02  ldelem.ref
0x12c03  castclass class Microsoft.Crm.ReportingServices.Task[]
0x12c08  ret
```
