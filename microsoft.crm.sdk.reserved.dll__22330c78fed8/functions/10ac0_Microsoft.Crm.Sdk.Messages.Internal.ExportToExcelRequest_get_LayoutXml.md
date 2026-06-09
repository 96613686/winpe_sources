# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelRequest::get_LayoutXml

- ea: `0x10ac0`
- end: `0x10aea`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelRequest::get_LayoutXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10ac0`

## string_xrefs

- `0x10ac6`: `LayoutXml`
- `0x10ad8`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x10ac0  ldarg.0
0x10ac1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10ac6  ldstr    aLayoutxml// "LayoutXml"
0x10acb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10ad0  brfalse.s loc_10AE8
0x10ad2  ldarg.0
0x10ad3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10ad8  ldstr    aLayoutxml// "LayoutXml"
0x10add  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10ae2  castclass [mscorlib]System.String
0x10ae7  ret
0x10ae8  ldnull
0x10ae9  ret
```
