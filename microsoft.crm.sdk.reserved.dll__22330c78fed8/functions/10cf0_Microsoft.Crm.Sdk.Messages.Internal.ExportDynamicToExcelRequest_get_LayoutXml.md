# Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::get_LayoutXml

- ea: `0x10cf0`
- end: `0x10d1a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::get_LayoutXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10cf0`

## string_xrefs

- `0x10cf6`: `LayoutXml`
- `0x10d08`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x10cf0  ldarg.0
0x10cf1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10cf6  ldstr    aLayoutxml// "LayoutXml"
0x10cfb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10d00  brfalse.s loc_10D18
0x10d02  ldarg.0
0x10d03  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10d08  ldstr    aLayoutxml// "LayoutXml"
0x10d0d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10d12  castclass [mscorlib]System.String
0x10d17  ret
0x10d18  ldnull
0x10d19  ret
```
