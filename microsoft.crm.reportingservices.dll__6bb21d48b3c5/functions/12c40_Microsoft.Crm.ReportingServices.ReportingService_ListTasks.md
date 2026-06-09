# Microsoft.Crm.ReportingServices.ReportingService::ListTasks

- ea: `0x12c40`
- end: `0x12c59`
- name: `Microsoft.Crm.ReportingServices.ReportingService::ListTasks`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12c41`: `ListTasks`

## pseudocode

```c

```

## disassembly

```asm
0x12c40  ldarg.0
0x12c41  ldstr    aListtasks// "ListTasks"
0x12c46  ldc.i4.0
0x12c47  newarr   [mscorlib]System.Object
0x12c4c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12c51  ldc.i4.0
0x12c52  ldelem.ref
0x12c53  castclass class Microsoft.Crm.ReportingServices.Task[]
0x12c58  ret
```
