# Microsoft.Crm.Sdk.Messages.Internal.UploadSharePointDocumentResponse::get_EditLink

- ea: `0xb730`
- end: `0xb75a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UploadSharePointDocumentResponse::get_EditLink`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb730`

## string_xrefs

- `0xb736`: `EditLink`
- `0xb748`: `EditLink`

## pseudocode

```c

```

## disassembly

```asm
0xb730  ldarg.0
0xb731  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xb736  ldstr    aEditlink// "EditLink"
0xb73b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xb740  brfalse.s loc_B758
0xb742  ldarg.0
0xb743  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xb748  ldstr    aEditlink// "EditLink"
0xb74d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb752  castclass [mscorlib]System.String
0xb757  ret
0xb758  ldnull
0xb759  ret
```
