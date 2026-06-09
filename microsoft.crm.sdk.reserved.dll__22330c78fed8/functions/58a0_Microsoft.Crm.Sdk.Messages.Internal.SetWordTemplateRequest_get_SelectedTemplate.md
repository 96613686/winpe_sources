# Microsoft.Crm.Sdk.Messages.Internal.SetWordTemplateRequest::get_SelectedTemplate

- ea: `0x58a0`
- end: `0x58ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.SetWordTemplateRequest::get_SelectedTemplate`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x58a0`

## string_xrefs

- `0x58a6`: `SelectedTemplate`
- `0x58b8`: `SelectedTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x58a0  ldarg.0
0x58a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x58a6  ldstr    aSelectedtempla// "SelectedTemplate"
0x58ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x58b0  brfalse.s loc_58C8
0x58b2  ldarg.0
0x58b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x58b8  ldstr    aSelectedtempla// "SelectedTemplate"
0x58bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x58c2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x58c7  ret
0x58c8  ldnull
0x58c9  ret
```
