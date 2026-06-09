# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscriptionAsync_0

- ea: `0x4590`
- end: `0x45c7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscriptionAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4580`

## callees

- `0x4590`

## string_xrefs

- `0x45ab`: `DeleteSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x4590  ldarg.0
0x4591  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscriptionOperationCompleted
0x4596  brtrue.s loc_45AA
0x4598  ldarg.0
0x4599  ldarg.0
0x459a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnDeleteSubscriptionOperationCompleted(object arg)
0x45a0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x45a5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscriptionOperationCompleted
0x45aa  ldarg.0
0x45ab  ldstr    aDeletesubscrip// "DeleteSubscription"
0x45b0  ldc.i4.1
0x45b1  newarr   [mscorlib]System.Object
0x45b6  dup
0x45b7  ldc.i4.0
0x45b8  ldarg.1
0x45b9  stelem.ref
0x45ba  ldarg.0
0x45bb  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscriptionOperationCompleted
0x45c0  ldarg.2
0x45c1  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x45c6  ret
```
