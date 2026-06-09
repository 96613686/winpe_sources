# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginValidateExtensionSettings

- ea: `0x49b0`
- end: `0x49d2`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginValidateExtensionSettings`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x49b1`: `ValidateExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x49b0  ldarg.0
0x49b1  ldstr    aValidateextens// "ValidateExtensionSettings"
0x49b6  ldc.i4.3
0x49b7  newarr   [mscorlib]System.Object
0x49bc  dup
0x49bd  ldc.i4.0
0x49be  ldarg.1
0x49bf  stelem.ref
0x49c0  dup
0x49c1  ldc.i4.1
0x49c2  ldarg.2
0x49c3  stelem.ref
0x49c4  dup
0x49c5  ldc.i4.2
0x49c6  ldarg.3
0x49c7  stelem.ref
0x49c8  ldarg.s  4
0x49ca  ldarg.s  5
0x49cc  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x49d1  ret
```
