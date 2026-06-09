# Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::set_ColMappingIdsToDelete

- ea: `0x64e0`
- end: `0x64f2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::set_ColMappingIdsToDelete`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6500`

## string_xrefs

- `0x64e6`: `ColMappingIdsToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x64e0  ldarg.0
0x64e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x64e6  ldstr    aColmappingidst// "ColMappingIdsToDelete"
0x64eb  ldarg.1
0x64ec  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x64f1  ret
```
