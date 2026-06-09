# Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_DeletedMetadataFilters

- ea: `0x12220`
- end: `0x12237`
- name: `Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_DeletedMetadataFilters`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x36d0`

## string_xrefs

- `0x12226`: `DeletedMetadataFilters`

## pseudocode

```c

```

## disassembly

```asm
0x12220  ldarg.0
0x12221  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x12226  ldstr    aDeletedmetadat// "DeletedMetadataFilters"
0x1222b  ldarg.1
0x1222c  box      Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters
0x12231  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x12236  ret
```
