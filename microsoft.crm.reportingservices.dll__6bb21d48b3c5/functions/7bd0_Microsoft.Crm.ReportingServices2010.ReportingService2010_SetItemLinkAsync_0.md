# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLinkAsync_0

- ea: `0x7bd0`
- end: `0x7c0b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLinkAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7bc0`

## callees

- `0x7bd0`

## string_xrefs

- `0x7beb`: `SetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x7bd0  ldarg.0
0x7bd1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLinkOperationCompleted
0x7bd6  brtrue.s loc_7BEA
0x7bd8  ldarg.0
0x7bd9  ldarg.0
0x7bda  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetItemLinkOperationCompleted(object arg)
0x7be0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x7be5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLinkOperationCompleted
0x7bea  ldarg.0
0x7beb  ldstr    aSetitemlink// "SetItemLink"
0x7bf0  ldc.i4.2
0x7bf1  newarr   [mscorlib]System.Object
0x7bf6  dup
0x7bf7  ldc.i4.0
0x7bf8  ldarg.1
0x7bf9  stelem.ref
0x7bfa  dup
0x7bfb  ldc.i4.1
0x7bfc  ldarg.2
0x7bfd  stelem.ref
0x7bfe  ldarg.0
0x7bff  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLinkOperationCompleted
0x7c04  ldarg.3
0x7c05  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x7c0a  ret
```
