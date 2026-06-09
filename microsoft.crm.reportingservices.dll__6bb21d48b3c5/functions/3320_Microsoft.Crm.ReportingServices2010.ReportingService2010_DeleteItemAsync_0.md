# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemAsync_0

- ea: `0x3320`
- end: `0x3357`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3310`

## callees

- `0x3320`

## string_xrefs

- `0x333b`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x3320  ldarg.0
0x3321  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemOperationCompleted
0x3326  brtrue.s loc_333A
0x3328  ldarg.0
0x3329  ldarg.0
0x332a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnDeleteItemOperationCompleted(object arg)
0x3330  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x3335  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemOperationCompleted
0x333a  ldarg.0
0x333b  ldstr    aDeleteitem// "DeleteItem"
0x3340  ldc.i4.1
0x3341  newarr   [mscorlib]System.Object
0x3346  dup
0x3347  ldc.i4.0
0x3348  ldarg.1
0x3349  stelem.ref
0x334a  ldarg.0
0x334b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemOperationCompleted
0x3350  ldarg.2
0x3351  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x3356  ret
```
