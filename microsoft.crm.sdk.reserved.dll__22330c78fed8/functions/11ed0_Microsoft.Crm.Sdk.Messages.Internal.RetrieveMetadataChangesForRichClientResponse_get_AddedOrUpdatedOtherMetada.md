# Microsoft.Crm.Sdk.Messages.Internal.RetrieveMetadataChangesForRichClientResponse::get_AddedOrUpdatedOtherMetadata

- ea: `0x11ed0`
- end: `0x11efa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveMetadataChangesForRichClientResponse::get_AddedOrUpdatedOtherMetadata`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11ed0`

## string_xrefs

- `0x11ed6`: `AddedOrUpdatedOtherMetadata`
- `0x11ee8`: `AddedOrUpdatedOtherMetadata`

## pseudocode

```c

```

## disassembly

```asm
0x11ed0  ldarg.0
0x11ed1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11ed6  ldstr    aAddedorupdated_0// "AddedOrUpdatedOtherMetadata"
0x11edb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11ee0  brfalse.s loc_11EF8
0x11ee2  ldarg.0
0x11ee3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11ee8  ldstr    aAddedorupdated_0// "AddedOrUpdatedOtherMetadata"
0x11eed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11ef2  castclass unsigned int8[]
0x11ef7  ret
0x11ef8  ldnull
0x11ef9  ret
```
