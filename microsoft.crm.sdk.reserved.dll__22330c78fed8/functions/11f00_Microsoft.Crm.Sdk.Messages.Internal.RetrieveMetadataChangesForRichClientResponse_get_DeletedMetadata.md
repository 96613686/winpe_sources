# Microsoft.Crm.Sdk.Messages.Internal.RetrieveMetadataChangesForRichClientResponse::get_DeletedMetadata

- ea: `0x11f00`
- end: `0x11f2a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveMetadataChangesForRichClientResponse::get_DeletedMetadata`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11f00`

## string_xrefs

- `0x11f06`: `DeletedMetadata`
- `0x11f18`: `DeletedMetadata`

## pseudocode

```c

```

## disassembly

```asm
0x11f00  ldarg.0
0x11f01  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11f06  ldstr    aDeletedmetadat// "DeletedMetadata"
0x11f0b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11f10  brfalse.s loc_11F28
0x11f12  ldarg.0
0x11f13  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11f18  ldstr    aDeletedmetadat// "DeletedMetadata"
0x11f1d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11f22  castclass unsigned int8[]
0x11f27  ret
0x11f28  ldnull
0x11f29  ret
```
