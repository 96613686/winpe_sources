# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypesAsync_0

- ea: `0x90b0`
- end: `0x90e3`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypesAsync_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x90a0`

## callees

- `0x90b0`

## string_xrefs

- `0x90cb`: `ListExtensionTypes`

## pseudocode

```c

```

## disassembly

```asm
0x90b0  ldarg.0
0x90b1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypesOperationCompleted
0x90b6  brtrue.s loc_90CA
0x90b8  ldarg.0
0x90b9  ldarg.0
0x90ba  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnListExtensionTypesOperationCompleted(object arg)
0x90c0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x90c5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypesOperationCompleted
0x90ca  ldarg.0
0x90cb  ldstr    aListextensiont// "ListExtensionTypes"
0x90d0  ldc.i4.0
0x90d1  newarr   [mscorlib]System.Object
0x90d6  ldarg.0
0x90d7  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypesOperationCompleted
0x90dc  ldarg.1
0x90dd  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x90e2  ret
```
