# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::set_FetchXml

- ea: `0x5170`
- end: `0x5182`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5230`

## string_xrefs

- `0x5176`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x5170  ldarg.0
0x5171  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5176  ldstr    aFetchxml// "FetchXml"
0x517b  ldarg.1
0x517c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x5181  ret
```
