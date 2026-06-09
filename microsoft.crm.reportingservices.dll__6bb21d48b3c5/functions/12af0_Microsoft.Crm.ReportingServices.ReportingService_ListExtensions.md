# Microsoft.Crm.ReportingServices.ReportingService::ListExtensions

- ea: `0x12af0`
- end: `0x12b12`
- name: `Microsoft.Crm.ReportingServices.ReportingService::ListExtensions`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x12af1`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x12af0  ldarg.0
0x12af1  ldstr    aListextensions// "ListExtensions"
0x12af6  ldc.i4.1
0x12af7  newarr   [mscorlib]System.Object
0x12afc  dup
0x12afd  ldc.i4.0
0x12afe  ldarg.1
0x12aff  box      Microsoft.Crm.ReportingServices.ExtensionTypeEnum
0x12b04  stelem.ref
0x12b05  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12b0a  ldc.i4.0
0x12b0b  ldelem.ref
0x12b0c  castclass class Microsoft.Crm.ReportingServices.Extension[]
0x12b11  ret
```
