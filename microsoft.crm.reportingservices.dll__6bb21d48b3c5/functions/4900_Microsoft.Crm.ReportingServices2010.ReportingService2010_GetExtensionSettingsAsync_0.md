# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsAsync_0

- ea: `0x4900`
- end: `0x4937`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x48f0`

## callees

- `0x4900`

## string_xrefs

- `0x491b`: `GetExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x4900  ldarg.0
0x4901  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsOperationCompleted
0x4906  brtrue.s loc_491A
0x4908  ldarg.0
0x4909  ldarg.0
0x490a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetExtensionSettingsOperationCompleted(object arg)
0x4910  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x4915  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsOperationCompleted
0x491a  ldarg.0
0x491b  ldstr    aGetextensionse// "GetExtensionSettings"
0x4920  ldc.i4.1
0x4921  newarr   [mscorlib]System.Object
0x4926  dup
0x4927  ldc.i4.0
0x4928  ldarg.1
0x4929  stelem.ref
0x492a  ldarg.0
0x492b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsOperationCompleted
0x4930  ldarg.2
0x4931  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x4936  ret
```
