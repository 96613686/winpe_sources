# Microsoft.Crm.Sdk.Messages.Internal.NewDocumentResponse::get_EditLink

- ea: `0xa1a0`
- end: `0xa1ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.NewDocumentResponse::get_EditLink`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa1a0`

## string_xrefs

- `0xa1a6`: `EditLink`
- `0xa1b8`: `EditLink`

## pseudocode

```c

```

## disassembly

```asm
0xa1a0  ldarg.0
0xa1a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xa1a6  ldstr    aEditlink// "EditLink"
0xa1ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xa1b0  brfalse.s loc_A1C8
0xa1b2  ldarg.0
0xa1b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xa1b8  ldstr    aEditlink// "EditLink"
0xa1bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xa1c2  castclass [mscorlib]System.String
0xa1c7  ret
0xa1c8  ldnull
0xa1c9  ret
```
