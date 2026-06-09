# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelRequest::set_LayoutXml

- ea: `0x10af0`
- end: `0x10b02`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelRequest::set_LayoutXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10bb0`

## string_xrefs

- `0x10af6`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x10af0  ldarg.0
0x10af1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10af6  ldstr    aLayoutxml// "LayoutXml"
0x10afb  ldarg.1
0x10afc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x10b01  ret
```
