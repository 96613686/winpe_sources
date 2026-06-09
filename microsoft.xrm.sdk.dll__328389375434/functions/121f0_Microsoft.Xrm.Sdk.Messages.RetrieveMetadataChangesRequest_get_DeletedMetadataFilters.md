# Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::get_DeletedMetadataFilters

- ea: `0x121f0`
- end: `0x1221a`
- name: `Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::get_DeletedMetadataFilters`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x36d0`
- `0x121f0`

## string_xrefs

- `0x121f6`: `DeletedMetadataFilters`
- `0x12208`: `DeletedMetadataFilters`

## pseudocode

```c

```

## disassembly

```asm
0x121f0  ldarg.0
0x121f1  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x121f6  ldstr    aDeletedmetadat// "DeletedMetadataFilters"
0x121fb  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12200  brfalse.s loc_12218
0x12202  ldarg.0
0x12203  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x12208  ldstr    aDeletedmetadat// "DeletedMetadataFilters"
0x1220d  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12212  unbox.any Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters
0x12217  ret
0x12218  ldc.i4.0
0x12219  ret
```
