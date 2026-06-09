# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_LayoutXml

- ea: `0x10920`
- end: `0x10932`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_LayoutXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10990`

## string_xrefs

- `0x10926`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x10920  ldarg.0
0x10921  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10926  ldstr    aLayoutxml// "LayoutXml"
0x1092b  ldarg.1
0x1092c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x10931  ret
```
