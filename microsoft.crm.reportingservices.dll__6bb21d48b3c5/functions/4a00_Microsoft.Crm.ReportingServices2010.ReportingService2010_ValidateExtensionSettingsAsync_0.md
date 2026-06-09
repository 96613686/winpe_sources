# Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettingsAsync_0

- ea: `0x4a00`
- end: `0x4a40`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettingsAsync_0`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x49f0`

## callees

- `0x4a00`

## string_xrefs

- `0x4a1b`: `ValidateExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x4a00  ldarg.0
0x4a01  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettingsOperationCompleted
0x4a06  brtrue.s loc_4A1A
0x4a08  ldarg.0
0x4a09  ldarg.0
0x4a0a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnValidateExtensionSettingsOperationCompleted(object arg)
0x4a10  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x4a15  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettingsOperationCompleted
0x4a1a  ldarg.0
0x4a1b  ldstr    aValidateextens// "ValidateExtensionSettings"
0x4a20  ldc.i4.3
0x4a21  newarr   [mscorlib]System.Object
0x4a26  dup
0x4a27  ldc.i4.0
0x4a28  ldarg.1
0x4a29  stelem.ref
0x4a2a  dup
0x4a2b  ldc.i4.1
0x4a2c  ldarg.2
0x4a2d  stelem.ref
0x4a2e  dup
0x4a2f  ldc.i4.2
0x4a30  ldarg.3
0x4a31  stelem.ref
0x4a32  ldarg.0
0x4a33  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettingsOperationCompleted
0x4a38  ldarg.s  4
0x4a3a  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x4a3f  ret
```
