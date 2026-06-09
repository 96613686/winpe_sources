# Microsoft.Crm.Sdk.Messages.Internal.RetrieveDocumentTemplatesResponse::get_DocumentTemplateEntityCollection

- ea: `0x53a0`
- end: `0x53ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveDocumentTemplatesResponse::get_DocumentTemplateEntityCollection`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x53a0`

## string_xrefs

- `0x53a6`: `DocumentTemplateEntityCollection`
- `0x53b8`: `DocumentTemplateEntityCollection`

## pseudocode

```c

```

## disassembly

```asm
0x53a0  ldarg.0
0x53a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x53a6  ldstr    aDocumenttempla// "DocumentTemplateEntityCollection"
0x53ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x53b0  brfalse.s loc_53C8
0x53b2  ldarg.0
0x53b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x53b8  ldstr    aDocumenttempla// "DocumentTemplateEntityCollection"
0x53bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x53c2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0x53c7  ret
0x53c8  ldnull
0x53c9  ret
```
