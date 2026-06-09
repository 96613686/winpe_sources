# Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::set_LayoutXml

- ea: `0x10d20`
- end: `0x10d32`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::set_LayoutXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10ed0`

## string_xrefs

- `0x10d26`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x10d20  ldarg.0
0x10d21  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10d26  ldstr    aLayoutxml// "LayoutXml"
0x10d2b  ldarg.1
0x10d2c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x10d31  ret
```
