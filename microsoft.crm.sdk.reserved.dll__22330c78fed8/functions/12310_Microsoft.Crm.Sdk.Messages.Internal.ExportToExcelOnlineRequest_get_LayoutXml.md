# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::get_LayoutXml

- ea: `0x12310`
- end: `0x1233a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::get_LayoutXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12310`

## string_xrefs

- `0x12316`: `LayoutXml`
- `0x12328`: `LayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x12310  ldarg.0
0x12311  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x12316  ldstr    aLayoutxml// "LayoutXml"
0x1231b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12320  brfalse.s loc_12338
0x12322  ldarg.0
0x12323  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x12328  ldstr    aLayoutxml// "LayoutXml"
0x1232d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12332  castclass [mscorlib]System.String
0x12337  ret
0x12338  ldnull
0x12339  ret
```
