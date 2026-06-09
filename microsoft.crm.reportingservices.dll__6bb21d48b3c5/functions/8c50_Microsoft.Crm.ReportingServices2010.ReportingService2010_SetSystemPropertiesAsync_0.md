# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPropertiesAsync_0

- ea: `0x8c50`
- end: `0x8c87`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPropertiesAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8c40`

## callees

- `0x8c50`

## string_xrefs

- `0x8c6b`: `SetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x8c50  ldarg.0
0x8c51  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPropertiesOperationCompleted
0x8c56  brtrue.s loc_8C6A
0x8c58  ldarg.0
0x8c59  ldarg.0
0x8c5a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetSystemPropertiesOperationCompleted(object arg)
0x8c60  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8c65  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPropertiesOperationCompleted
0x8c6a  ldarg.0
0x8c6b  ldstr    aSetsystemprope// "SetSystemProperties"
0x8c70  ldc.i4.1
0x8c71  newarr   [mscorlib]System.Object
0x8c76  dup
0x8c77  ldc.i4.0
0x8c78  ldarg.1
0x8c79  stelem.ref
0x8c7a  ldarg.0
0x8c7b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPropertiesOperationCompleted
0x8c80  ldarg.2
0x8c81  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8c86  ret
```
