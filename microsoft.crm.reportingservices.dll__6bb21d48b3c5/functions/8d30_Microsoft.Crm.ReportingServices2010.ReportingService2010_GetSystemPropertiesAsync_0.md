# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPropertiesAsync_0

- ea: `0x8d30`
- end: `0x8d67`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPropertiesAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8d20`

## callees

- `0x8d30`

## string_xrefs

- `0x8d4b`: `GetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x8d30  ldarg.0
0x8d31  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPropertiesOperationCompleted
0x8d36  brtrue.s loc_8D4A
0x8d38  ldarg.0
0x8d39  ldarg.0
0x8d3a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetSystemPropertiesOperationCompleted(object arg)
0x8d40  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8d45  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPropertiesOperationCompleted
0x8d4a  ldarg.0
0x8d4b  ldstr    aGetsystemprope// "GetSystemProperties"
0x8d50  ldc.i4.1
0x8d51  newarr   [mscorlib]System.Object
0x8d56  dup
0x8d57  ldc.i4.0
0x8d58  ldarg.1
0x8d59  stelem.ref
0x8d5a  ldarg.0
0x8d5b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPropertiesOperationCompleted
0x8d60  ldarg.2
0x8d61  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8d66  ret
```
