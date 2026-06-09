# Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettings

- ea: `0x4980`
- end: `0x49a5`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ValidateExtensionSettings`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x4981`: `ValidateExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x4980  ldarg.0
0x4981  ldstr    aValidateextens// "ValidateExtensionSettings"
0x4986  ldc.i4.3
0x4987  newarr   [mscorlib]System.Object
0x498c  dup
0x498d  ldc.i4.0
0x498e  ldarg.1
0x498f  stelem.ref
0x4990  dup
0x4991  ldc.i4.1
0x4992  ldarg.2
0x4993  stelem.ref
0x4994  dup
0x4995  ldc.i4.2
0x4996  ldarg.3
0x4997  stelem.ref
0x4998  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x499d  ldc.i4.0
0x499e  ldelem.ref
0x499f  castclass class Microsoft.Crm.ReportingServices2010.ExtensionParameter[]
0x49a4  ret
```
