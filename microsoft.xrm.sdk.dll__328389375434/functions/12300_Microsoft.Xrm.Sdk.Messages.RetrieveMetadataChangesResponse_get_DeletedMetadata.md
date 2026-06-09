# Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse::get_DeletedMetadata

- ea: `0x12300`
- end: `0x1232a`
- name: `Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse::get_DeletedMetadata`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x3790`
- `0x12300`

## string_xrefs

- `0x12306`: `DeletedMetadata`
- `0x12318`: `DeletedMetadata`

## pseudocode

```c

```

## disassembly

```asm
0x12300  ldarg.0
0x12301  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12306  ldstr    aDeletedmetadat_0// "DeletedMetadata"
0x1230b  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12310  brfalse.s loc_12328
0x12312  ldarg.0
0x12313  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12318  ldstr    aDeletedmetadat_0// "DeletedMetadata"
0x1231d  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12322  castclass Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataCollection
0x12327  ret
0x12328  ldnull
0x12329  ret
```
