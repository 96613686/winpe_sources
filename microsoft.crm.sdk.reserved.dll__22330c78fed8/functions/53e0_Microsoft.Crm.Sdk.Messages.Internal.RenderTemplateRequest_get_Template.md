# Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::get_Template

- ea: `0x53e0`
- end: `0x540a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::get_Template`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x53e0`

## string_xrefs

- `0x53e6`: `Template`
- `0x53f8`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x53e0  ldarg.0
0x53e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x53e6  ldstr    aTemplate// "Template"
0x53eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x53f0  brfalse.s loc_5408
0x53f2  ldarg.0
0x53f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x53f8  ldstr    aTemplate// "Template"
0x53fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5402  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5407  ret
0x5408  ldnull
0x5409  ret
```
