# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettings

- ea: `0x48a0`
- end: `0x48bd`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettings`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x48a1`: `GetExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x48a0  ldarg.0
0x48a1  ldstr    aGetextensionse// "GetExtensionSettings"
0x48a6  ldc.i4.1
0x48a7  newarr   [mscorlib]System.Object
0x48ac  dup
0x48ad  ldc.i4.0
0x48ae  ldarg.1
0x48af  stelem.ref
0x48b0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x48b5  ldc.i4.0
0x48b6  ldelem.ref
0x48b7  castclass class Microsoft.Crm.ReportingServices2010.ExtensionParameter[]
0x48bc  ret
```
