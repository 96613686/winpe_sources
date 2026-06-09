# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPoliciesAsync_0

- ea: `0x63a0`
- end: `0x63e0`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPoliciesAsync_0`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6390`

## callees

- `0x63a0`

## string_xrefs

- `0x63bb`: `SetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x63a0  ldarg.0
0x63a1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPoliciesOperationCompleted
0x63a6  brtrue.s loc_63BA
0x63a8  ldarg.0
0x63a9  ldarg.0
0x63aa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetModelItemPoliciesOperationCompleted(object arg)
0x63b0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x63b5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPoliciesOperationCompleted
0x63ba  ldarg.0
0x63bb  ldstr    aSetmodelitempo// "SetModelItemPolicies"
0x63c0  ldc.i4.3
0x63c1  newarr   [mscorlib]System.Object
0x63c6  dup
0x63c7  ldc.i4.0
0x63c8  ldarg.1
0x63c9  stelem.ref
0x63ca  dup
0x63cb  ldc.i4.1
0x63cc  ldarg.2
0x63cd  stelem.ref
0x63ce  dup
0x63cf  ldc.i4.2
0x63d0  ldarg.3
0x63d1  stelem.ref
0x63d2  ldarg.0
0x63d3  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPoliciesOperationCompleted
0x63d8  ldarg.s  4
0x63da  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x63df  ret
```
