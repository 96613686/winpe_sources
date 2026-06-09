# Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::.ctor

- ea: `0x6500`
- end: `0x6520`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x6490`
- `0x64e0`

## string_xrefs

- `0x6507`: `CreateOrUpdateImportMapFromApp`

## pseudocode

```c

```

## disassembly

```asm
0x6500  ldarg.0
0x6501  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x6506  ldarg.0
0x6507  ldstr    aCreateorupdate// "CreateOrUpdateImportMapFromApp"
0x650c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x6511  ldarg.0
0x6512  ldnull
0x6513  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::set_MapXml(string value)
0x6518  ldarg.0
0x6519  ldnull
0x651a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::set_ColMappingIdsToDelete(valuetype [mscorlib]System.Guid[] value)
0x651f  ret
```
