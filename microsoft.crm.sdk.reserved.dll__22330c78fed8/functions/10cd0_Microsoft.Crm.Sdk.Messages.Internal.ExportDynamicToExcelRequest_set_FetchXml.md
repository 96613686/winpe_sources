# Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::set_FetchXml

- ea: `0x10cd0`
- end: `0x10ce2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10ed0`

## string_xrefs

- `0x10cd6`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x10cd0  ldarg.0
0x10cd1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10cd6  ldstr    aFetchxml// "FetchXml"
0x10cdb  ldarg.1
0x10cdc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x10ce1  ret
```
