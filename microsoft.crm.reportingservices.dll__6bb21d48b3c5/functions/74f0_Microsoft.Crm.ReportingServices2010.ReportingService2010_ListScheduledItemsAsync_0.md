# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItemsAsync_0

- ea: `0x74f0`
- end: `0x7527`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItemsAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x74e0`

## callees

- `0x74f0`

## string_xrefs

- `0x750b`: `ListScheduledItems`

## pseudocode

```c

```

## disassembly

```asm
0x74f0  ldarg.0
0x74f1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItemsOperationCompleted
0x74f6  brtrue.s loc_750A
0x74f8  ldarg.0
0x74f9  ldarg.0
0x74fa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnListScheduledItemsOperationCompleted(object arg)
0x7500  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x7505  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItemsOperationCompleted
0x750a  ldarg.0
0x750b  ldstr    aListscheduledi// "ListScheduledItems"
0x7510  ldc.i4.1
0x7511  newarr   [mscorlib]System.Object
0x7516  dup
0x7517  ldc.i4.0
0x7518  ldarg.1
0x7519  stelem.ref
0x751a  ldarg.0
0x751b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItemsOperationCompleted
0x7520  ldarg.2
0x7521  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x7526  ret
```
