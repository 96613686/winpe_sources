# Microsoft.Crm.Sdk.Messages.Internal.NewDocumentRequest::get_FolderPath

- ea: `0xa100`
- end: `0xa12a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.NewDocumentRequest::get_FolderPath`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa100`

## string_xrefs

- `0xa106`: `FolderPath`
- `0xa118`: `FolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xa100  ldarg.0
0xa101  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xa106  ldstr    aFolderpath// "FolderPath"
0xa10b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xa110  brfalse.s loc_A128
0xa112  ldarg.0
0xa113  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xa118  ldstr    aFolderpath// "FolderPath"
0xa11d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xa122  castclass [mscorlib]System.String
0xa127  ret
0xa128  ldnull
0xa129  ret
```
