# Microsoft.Crm.Sdk.Messages.Internal.CopyAttachmentsFromTemplateRequest::get_Template

- ea: `0x13f00`
- end: `0x13f2a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CopyAttachmentsFromTemplateRequest::get_Template`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x13f00`

## string_xrefs

- `0x13f06`: `Template`
- `0x13f18`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x13f00  ldarg.0
0x13f01  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x13f06  ldstr    aTemplate// "Template"
0x13f0b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13f10  brfalse.s loc_13F28
0x13f12  ldarg.0
0x13f13  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x13f18  ldstr    aTemplate// "Template"
0x13f1d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13f22  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x13f27  ret
0x13f28  ldnull
0x13f29  ret
```
