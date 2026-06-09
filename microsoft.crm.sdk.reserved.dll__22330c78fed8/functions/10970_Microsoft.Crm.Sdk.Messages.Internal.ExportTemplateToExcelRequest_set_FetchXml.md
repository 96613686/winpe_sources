# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_FetchXml

- ea: `0x10970`
- end: `0x10982`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10990`

## string_xrefs

- `0x10976`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x10970  ldarg.0
0x10971  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10976  ldstr    aFetchxml// "FetchXml"
0x1097b  ldarg.1
0x1097c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x10981  ret
```
