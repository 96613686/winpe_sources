# Microsoft.Crm.Sdk.Messages.Internal.RetrieveMetadataChangesForRichClientResponse::get_AddedOrUpdatedLocalizedLabelMetadata

- ea: `0x11ea0`
- end: `0x11eca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveMetadataChangesForRichClientResponse::get_AddedOrUpdatedLocalizedLabelMetadata`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11ea0`

## string_xrefs

- `0x11ea6`: `AddedOrUpdatedLocalizedLabelMetadata`
- `0x11eb8`: `AddedOrUpdatedLocalizedLabelMetadata`

## pseudocode

```c

```

## disassembly

```asm
0x11ea0  ldarg.0
0x11ea1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11ea6  ldstr    aAddedorupdated// "AddedOrUpdatedLocalizedLabelMetadata"
0x11eab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11eb0  brfalse.s loc_11EC8
0x11eb2  ldarg.0
0x11eb3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11eb8  ldstr    aAddedorupdated// "AddedOrUpdatedLocalizedLabelMetadata"
0x11ebd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11ec2  castclass unsigned int8[]
0x11ec7  ret
0x11ec8  ldnull
0x11ec9  ret
```
