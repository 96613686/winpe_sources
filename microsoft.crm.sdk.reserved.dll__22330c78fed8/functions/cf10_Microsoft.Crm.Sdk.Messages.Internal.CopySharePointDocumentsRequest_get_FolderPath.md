# Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::get_FolderPath

- ea: `0xcf10`
- end: `0xcf3a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::get_FolderPath`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xcf10`

## string_xrefs

- `0xcf16`: `FolderPath`
- `0xcf28`: `FolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xcf10  ldarg.0
0xcf11  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xcf16  ldstr    aFolderpath// "FolderPath"
0xcf1b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xcf20  brfalse.s loc_CF38
0xcf22  ldarg.0
0xcf23  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xcf28  ldstr    aFolderpath// "FolderPath"
0xcf2d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xcf32  castclass [mscorlib]System.String
0xcf37  ret
0xcf38  ldnull
0xcf39  ret
```
