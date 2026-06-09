# Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItemAsync_0

- ea: `0x3400`
- end: `0x343b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItemAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33f0`

## callees

- `0x3400`

## string_xrefs

- `0x341b`: `MoveItem`

## pseudocode

```c

```

## disassembly

```asm
0x3400  ldarg.0
0x3401  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItemOperationCompleted
0x3406  brtrue.s loc_341A
0x3408  ldarg.0
0x3409  ldarg.0
0x340a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnMoveItemOperationCompleted(object arg)
0x3410  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x3415  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItemOperationCompleted
0x341a  ldarg.0
0x341b  ldstr    aMoveitem// "MoveItem"
0x3420  ldc.i4.2
0x3421  newarr   [mscorlib]System.Object
0x3426  dup
0x3427  ldc.i4.0
0x3428  ldarg.1
0x3429  stelem.ref
0x342a  dup
0x342b  ldc.i4.1
0x342c  ldarg.2
0x342d  stelem.ref
0x342e  ldarg.0
0x342f  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItemOperationCompleted
0x3434  ldarg.3
0x3435  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x343a  ret
```
