# Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::get_ColMappingIdsToDelete

- ea: `0x64b0`
- end: `0x64da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::get_ColMappingIdsToDelete`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x64b0`

## string_xrefs

- `0x64b6`: `ColMappingIdsToDelete`
- `0x64c8`: `ColMappingIdsToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x64b0  ldarg.0
0x64b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x64b6  ldstr    aColmappingidst// "ColMappingIdsToDelete"
0x64bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x64c0  brfalse.s loc_64D8
0x64c2  ldarg.0
0x64c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x64c8  ldstr    aColmappingidst// "ColMappingIdsToDelete"
0x64cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x64d2  castclass valuetype [mscorlib]System.Guid[]
0x64d7  ret
0x64d8  ldnull
0x64d9  ret
```
