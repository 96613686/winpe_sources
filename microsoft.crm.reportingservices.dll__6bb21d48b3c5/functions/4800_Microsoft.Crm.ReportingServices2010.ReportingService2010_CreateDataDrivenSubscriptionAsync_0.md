# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionAsync_0

- ea: `0x4800`
- end: `0x4854`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionAsync_0`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x47e0`

## callees

- `0x4800`

## string_xrefs

- `0x481b`: `CreateDataDrivenSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x4800  ldarg.0
0x4801  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionOperationCompleted
0x4806  brtrue.s loc_481A
0x4808  ldarg.0
0x4809  ldarg.0
0x480a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateDataDrivenSubscriptionOperationCompleted(object arg)
0x4810  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x4815  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionOperationCompleted
0x481a  ldarg.0
0x481b  ldstr    aCreatedatadriv// "CreateDataDrivenSubscription"
0x4820  ldc.i4.7
0x4821  newarr   [mscorlib]System.Object
0x4826  dup
0x4827  ldc.i4.0
0x4828  ldarg.1
0x4829  stelem.ref
0x482a  dup
0x482b  ldc.i4.1
0x482c  ldarg.2
0x482d  stelem.ref
0x482e  dup
0x482f  ldc.i4.2
0x4830  ldarg.3
0x4831  stelem.ref
0x4832  dup
0x4833  ldc.i4.3
0x4834  ldarg.s  4
0x4836  stelem.ref
0x4837  dup
0x4838  ldc.i4.4
0x4839  ldarg.s  5
0x483b  stelem.ref
0x483c  dup
0x483d  ldc.i4.5
0x483e  ldarg.s  6
0x4840  stelem.ref
0x4841  dup
0x4842  ldc.i4.6
0x4843  ldarg.s  7
0x4845  stelem.ref
0x4846  ldarg.0
0x4847  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionOperationCompleted
0x484c  ldarg.s  8
0x484e  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x4853  ret
```
