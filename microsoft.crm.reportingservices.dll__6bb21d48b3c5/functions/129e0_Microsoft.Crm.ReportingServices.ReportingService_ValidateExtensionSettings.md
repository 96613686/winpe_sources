# Microsoft.Crm.ReportingServices.ReportingService::ValidateExtensionSettings

- ea: `0x129e0`
- end: `0x12a01`
- name: `Microsoft.Crm.ReportingServices.ReportingService::ValidateExtensionSettings`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x129e1`: `ValidateExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x129e0  ldarg.0
0x129e1  ldstr    aValidateextens// "ValidateExtensionSettings"
0x129e6  ldc.i4.2
0x129e7  newarr   [mscorlib]System.Object
0x129ec  dup
0x129ed  ldc.i4.0
0x129ee  ldarg.1
0x129ef  stelem.ref
0x129f0  dup
0x129f1  ldc.i4.1
0x129f2  ldarg.2
0x129f3  stelem.ref
0x129f4  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x129f9  ldc.i4.0
0x129fa  ldelem.ref
0x129fb  castclass class Microsoft.Crm.ReportingServices.ExtensionParameter[]
0x12a00  ret
```
