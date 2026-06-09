# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionAsync_0

- ea: `0x46c0`
- end: `0x470f`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionAsync_0`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46a0`

## callees

- `0x46c0`

## string_xrefs

- `0x46db`: `CreateSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x46c0  ldarg.0
0x46c1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionOperationCompleted
0x46c6  brtrue.s loc_46DA
0x46c8  ldarg.0
0x46c9  ldarg.0
0x46ca  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateSubscriptionOperationCompleted(object arg)
0x46d0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x46d5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionOperationCompleted
0x46da  ldarg.0
0x46db  ldstr    aCreatesubscrip// "CreateSubscription"
0x46e0  ldc.i4.6
0x46e1  newarr   [mscorlib]System.Object
0x46e6  dup
0x46e7  ldc.i4.0
0x46e8  ldarg.1
0x46e9  stelem.ref
0x46ea  dup
0x46eb  ldc.i4.1
0x46ec  ldarg.2
0x46ed  stelem.ref
0x46ee  dup
0x46ef  ldc.i4.2
0x46f0  ldarg.3
0x46f1  stelem.ref
0x46f2  dup
0x46f3  ldc.i4.3
0x46f4  ldarg.s  4
0x46f6  stelem.ref
0x46f7  dup
0x46f8  ldc.i4.4
0x46f9  ldarg.s  5
0x46fb  stelem.ref
0x46fc  dup
0x46fd  ldc.i4.5
0x46fe  ldarg.s  6
0x4700  stelem.ref
0x4701  ldarg.0
0x4702  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionOperationCompleted
0x4707  ldarg.s  7
0x4709  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x470e  ret
```
