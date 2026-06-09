# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::get_LayoutXml

- ea: `0x108f0`
- end: `0x1091a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::get_LayoutXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x108f0`

## string_xrefs

- `0x108f6`: `LayoutXml`
- `0x10908`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x108f0  ldarg.0
0x108f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x108f6  ldstr    aLayoutxml// "LayoutXml"
0x108fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10900  brfalse.s loc_10918
0x10902  ldarg.0
0x10903  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10908  ldstr    aLayoutxml// "LayoutXml"
0x1090d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10912  castclass [mscorlib]System.String
0x10917  ret
0x10918  ldnull
0x10919  ret
```
