# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParametersAsync_0

- ea: `0x75d0`
- end: `0x760b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParametersAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x75c0`

## callees

- `0x75d0`

## string_xrefs

- `0x75eb`: `SetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x75d0  ldarg.0
0x75d1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParametersOperationCompleted
0x75d6  brtrue.s loc_75EA
0x75d8  ldarg.0
0x75d9  ldarg.0
0x75da  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetItemParametersOperationCompleted(object arg)
0x75e0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x75e5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParametersOperationCompleted
0x75ea  ldarg.0
0x75eb  ldstr    aSetitemparamet// "SetItemParameters"
0x75f0  ldc.i4.2
0x75f1  newarr   [mscorlib]System.Object
0x75f6  dup
0x75f7  ldc.i4.0
0x75f8  ldarg.1
0x75f9  stelem.ref
0x75fa  dup
0x75fb  ldc.i4.1
0x75fc  ldarg.2
0x75fd  stelem.ref
0x75fe  ldarg.0
0x75ff  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParametersOperationCompleted
0x7604  ldarg.3
0x7605  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x760a  ret
```
