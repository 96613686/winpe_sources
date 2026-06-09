# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasks

- ea: `0x5d70`
- end: `0x5d8d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasks`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5d71`: `ListTasks`

## pseudocode

```c

```

## disassembly

```asm
0x5d70  ldarg.0
0x5d71  ldstr    aListtasks// "ListTasks"
0x5d76  ldc.i4.1
0x5d77  newarr   [mscorlib]System.Object
0x5d7c  dup
0x5d7d  ldc.i4.0
0x5d7e  ldarg.1
0x5d7f  stelem.ref
0x5d80  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x5d85  ldc.i4.0
0x5d86  ldelem.ref
0x5d87  castclass class Microsoft.Crm.ReportingServices2010.Task[]
0x5d8c  ret
```
