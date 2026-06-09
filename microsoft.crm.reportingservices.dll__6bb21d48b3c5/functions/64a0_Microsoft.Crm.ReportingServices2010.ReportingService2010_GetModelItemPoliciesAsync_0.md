# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPoliciesAsync_0

- ea: `0x64a0`
- end: `0x64db`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPoliciesAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6490`

## callees

- `0x64a0`

## string_xrefs

- `0x64bb`: `GetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x64a0  ldarg.0
0x64a1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPoliciesOperationCompleted
0x64a6  brtrue.s loc_64BA
0x64a8  ldarg.0
0x64a9  ldarg.0
0x64aa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetModelItemPoliciesOperationCompleted(object arg)
0x64b0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x64b5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPoliciesOperationCompleted
0x64ba  ldarg.0
0x64bb  ldstr    aGetmodelitempo// "GetModelItemPolicies"
0x64c0  ldc.i4.2
0x64c1  newarr   [mscorlib]System.Object
0x64c6  dup
0x64c7  ldc.i4.0
0x64c8  ldarg.1
0x64c9  stelem.ref
0x64ca  dup
0x64cb  ldc.i4.1
0x64cc  ldarg.2
0x64cd  stelem.ref
0x64ce  ldarg.0
0x64cf  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPoliciesOperationCompleted
0x64d4  ldarg.3
0x64d5  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x64da  ret
```
