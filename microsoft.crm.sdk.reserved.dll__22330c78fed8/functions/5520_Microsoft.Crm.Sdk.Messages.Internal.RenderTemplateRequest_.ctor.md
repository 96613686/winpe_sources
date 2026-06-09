# Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::.ctor

- ea: `0x5520`
- end: `0x554e`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x5410`
- `0x5460`
- `0x54b0`
- `0x5500`

## string_xrefs

- `0x5527`: `RenderTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5520  ldarg.0
0x5521  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x5526  ldarg.0
0x5527  ldstr    aRendertemplate// "RenderTemplate"
0x552c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x5531  ldarg.0
0x5532  ldnull
0x5533  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::set_Template(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x5538  ldarg.0
0x5539  ldnull
0x553a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::set_FetchXml(string value)
0x553f  ldarg.0
0x5540  ldnull
0x5541  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::set_QueryApi(string value)
0x5546  ldarg.0
0x5547  ldnull
0x5548  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::set_QueryParameters(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection value)
0x554d  ret
```
