# Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateFromViewRequest::get_Template

- ea: `0x55b0`
- end: `0x55da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateFromViewRequest::get_Template`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x55b0`

## string_xrefs

- `0x55b6`: `Template`
- `0x55c8`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x55b0  ldarg.0
0x55b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x55b6  ldstr    aTemplate// "Template"
0x55bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x55c0  brfalse.s loc_55D8
0x55c2  ldarg.0
0x55c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x55c8  ldstr    aTemplate// "Template"
0x55cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x55d2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x55d7  ret
0x55d8  ldnull
0x55d9  ret
```
