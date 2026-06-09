# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::set_LayoutXml

- ea: `0x12340`
- end: `0x12352`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::set_LayoutXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x12400`

## string_xrefs

- `0x12346`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x12340  ldarg.0
0x12341  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x12346  ldstr    aLayoutxml// "LayoutXml"
0x1234b  ldarg.1
0x1234c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x12351  ret
```
