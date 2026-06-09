# Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPoliciesAsync_0

- ea: `0x6ce0`
- end: `0x6d17`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPoliciesAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6cd0`

## callees

- `0x6ce0`

## string_xrefs

- `0x6cfb`: `RemoveAllModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6ce0  ldarg.0
0x6ce1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPoliciesOperationCompleted
0x6ce6  brtrue.s loc_6CFA
0x6ce8  ldarg.0
0x6ce9  ldarg.0
0x6cea  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnRemoveAllModelItemPoliciesOperationCompleted(object arg)
0x6cf0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x6cf5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPoliciesOperationCompleted
0x6cfa  ldarg.0
0x6cfb  ldstr    aRemoveallmodel// "RemoveAllModelItemPolicies"
0x6d00  ldc.i4.1
0x6d01  newarr   [mscorlib]System.Object
0x6d06  dup
0x6d07  ldc.i4.0
0x6d08  ldarg.1
0x6d09  stelem.ref
0x6d0a  ldarg.0
0x6d0b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPoliciesOperationCompleted
0x6d10  ldarg.2
0x6d11  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x6d16  ret
```
