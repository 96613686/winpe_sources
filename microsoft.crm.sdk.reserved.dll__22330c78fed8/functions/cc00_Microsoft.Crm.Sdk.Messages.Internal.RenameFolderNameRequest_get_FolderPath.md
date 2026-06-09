# Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::get_FolderPath

- ea: `0xcc00`
- end: `0xcc2a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::get_FolderPath`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xcc00`

## string_xrefs

- `0xcc06`: `FolderPath`
- `0xcc18`: `FolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xcc00  ldarg.0
0xcc01  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xcc06  ldstr    aFolderpath// "FolderPath"
0xcc0b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xcc10  brfalse.s loc_CC28
0xcc12  ldarg.0
0xcc13  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xcc18  ldstr    aFolderpath// "FolderPath"
0xcc1d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xcc22  castclass [mscorlib]System.String
0xcc27  ret
0xcc28  ldnull
0xcc29  ret
```
