# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkAsync_0

- ea: `0x7cb0`
- end: `0x7ce7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7ca0`

## callees

- `0x7cb0`

## string_xrefs

- `0x7ccb`: `GetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x7cb0  ldarg.0
0x7cb1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkOperationCompleted
0x7cb6  brtrue.s loc_7CCA
0x7cb8  ldarg.0
0x7cb9  ldarg.0
0x7cba  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemLinkOperationCompleted(object arg)
0x7cc0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x7cc5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkOperationCompleted
0x7cca  ldarg.0
0x7ccb  ldstr    aGetitemlink// "GetItemLink"
0x7cd0  ldc.i4.1
0x7cd1  newarr   [mscorlib]System.Object
0x7cd6  dup
0x7cd7  ldc.i4.0
0x7cd8  ldarg.1
0x7cd9  stelem.ref
0x7cda  ldarg.0
0x7cdb  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkOperationCompleted
0x7ce0  ldarg.2
0x7ce1  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x7ce6  ret
```
