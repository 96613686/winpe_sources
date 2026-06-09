# Microsoft.Crm.ReportingServices.ReportingService::GetExtensionSettings

- ea: `0x12990`
- end: `0x129ad`
- name: `Microsoft.Crm.ReportingServices.ReportingService::GetExtensionSettings`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x12991`: `GetExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x12990  ldarg.0
0x12991  ldstr    aGetextensionse// "GetExtensionSettings"
0x12996  ldc.i4.1
0x12997  newarr   [mscorlib]System.Object
0x1299c  dup
0x1299d  ldc.i4.0
0x1299e  ldarg.1
0x1299f  stelem.ref
0x129a0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x129a5  ldc.i4.0
0x129a6  ldelem.ref
0x129a7  castclass class Microsoft.Crm.ReportingServices.ExtensionParameter[]
0x129ac  ret
```
