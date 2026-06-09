# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::get_Template

- ea: `0x50f0`
- end: `0x511a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::get_Template`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x50f0`

## string_xrefs

- `0x50f6`: `Template`
- `0x5108`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x50f0  ldarg.0
0x50f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x50f6  ldstr    aTemplate// "Template"
0x50fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5100  brfalse.s loc_5118
0x5102  ldarg.0
0x5103  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5108  ldstr    aTemplate// "Template"
0x510d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5112  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5117  ret
0x5118  ldnull
0x5119  ret
```
