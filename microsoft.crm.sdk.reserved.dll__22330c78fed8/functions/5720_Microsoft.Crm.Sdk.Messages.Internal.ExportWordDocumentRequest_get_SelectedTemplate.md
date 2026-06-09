# Microsoft.Crm.Sdk.Messages.Internal.ExportWordDocumentRequest::get_SelectedTemplate

- ea: `0x5720`
- end: `0x574a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportWordDocumentRequest::get_SelectedTemplate`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5720`

## string_xrefs

- `0x5726`: `SelectedTemplate`
- `0x5738`: `SelectedTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5720  ldarg.0
0x5721  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5726  ldstr    aSelectedtempla// "SelectedTemplate"
0x572b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5730  brfalse.s loc_5748
0x5732  ldarg.0
0x5733  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5738  ldstr    aSelectedtempla// "SelectedTemplate"
0x573d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5742  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5747  ret
0x5748  ldnull
0x5749  ret
```
