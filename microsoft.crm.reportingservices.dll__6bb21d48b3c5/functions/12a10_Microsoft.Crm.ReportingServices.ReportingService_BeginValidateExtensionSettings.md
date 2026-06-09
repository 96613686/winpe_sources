# Microsoft.Crm.ReportingServices.ReportingService::BeginValidateExtensionSettings

- ea: `0x12a10`
- end: `0x12a2d`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginValidateExtensionSettings`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x12a11`: `ValidateExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x12a10  ldarg.0
0x12a11  ldstr    aValidateextens// "ValidateExtensionSettings"
0x12a16  ldc.i4.2
0x12a17  newarr   [mscorlib]System.Object
0x12a1c  dup
0x12a1d  ldc.i4.0
0x12a1e  ldarg.1
0x12a1f  stelem.ref
0x12a20  dup
0x12a21  ldc.i4.1
0x12a22  ldarg.2
0x12a23  stelem.ref
0x12a24  ldarg.3
0x12a25  ldarg.s  4
0x12a27  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12a2c  ret
```
