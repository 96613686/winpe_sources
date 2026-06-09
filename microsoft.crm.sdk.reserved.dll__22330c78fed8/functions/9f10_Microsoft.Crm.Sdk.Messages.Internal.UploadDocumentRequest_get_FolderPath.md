# Microsoft.Crm.Sdk.Messages.Internal.UploadDocumentRequest::get_FolderPath

- ea: `0x9f10`
- end: `0x9f3a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UploadDocumentRequest::get_FolderPath`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x9f10`

## string_xrefs

- `0x9f16`: `FolderPath`
- `0x9f28`: `FolderPath`

## pseudocode

```c

```

## disassembly

```asm
0x9f10  ldarg.0
0x9f11  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x9f16  ldstr    aFolderpath// "FolderPath"
0x9f1b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x9f20  brfalse.s loc_9F38
0x9f22  ldarg.0
0x9f23  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x9f28  ldstr    aFolderpath// "FolderPath"
0x9f2d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x9f32  castclass [mscorlib]System.String
0x9f37  ret
0x9f38  ldnull
0x9f39  ret
```
