# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasksAsync_0

- ea: `0x5dd0`
- end: `0x5e07`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasksAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5dc0`

## callees

- `0x5dd0`

## string_xrefs

- `0x5deb`: `ListTasks`

## pseudocode

```c

```

## disassembly

```asm
0x5dd0  ldarg.0
0x5dd1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasksOperationCompleted
0x5dd6  brtrue.s loc_5DEA
0x5dd8  ldarg.0
0x5dd9  ldarg.0
0x5dda  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnListTasksOperationCompleted(object arg)
0x5de0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x5de5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasksOperationCompleted
0x5dea  ldarg.0
0x5deb  ldstr    aListtasks// "ListTasks"
0x5df0  ldc.i4.1
0x5df1  newarr   [mscorlib]System.Object
0x5df6  dup
0x5df7  ldc.i4.0
0x5df8  ldarg.1
0x5df9  stelem.ref
0x5dfa  ldarg.0
0x5dfb  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListTasksOperationCompleted
0x5e00  ldarg.2
0x5e01  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x5e06  ret
```
