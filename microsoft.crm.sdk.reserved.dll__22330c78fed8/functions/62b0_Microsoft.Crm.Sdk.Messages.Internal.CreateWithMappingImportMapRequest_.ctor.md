# Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::.ctor

- ea: `0x62b0`
- end: `0x62f3`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::.ctor`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x60b0`
- `0x6100`
- `0x6150`
- `0x61a0`
- `0x61f0`
- `0x6240`
- `0x6290`

## string_xrefs

- `0x62b7`: `CreateWithMappingImportMap`

## pseudocode

```c

```

## disassembly

```asm
0x62b0  ldarg.0
0x62b1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x62b6  ldarg.0
0x62b7  ldstr    aCreatewithmapp// "CreateWithMappingImportMap"
0x62bc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x62c1  ldarg.0
0x62c2  ldnull
0x62c3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_ImportMap(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity value)
0x62c8  ldarg.0
0x62c9  ldnull
0x62ca  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_ColumnMappings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x62cf  ldarg.0
0x62d0  ldnull
0x62d1  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_PickListMappings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x62d6  ldarg.0
0x62d7  ldnull
0x62d8  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_LookUpMappings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x62dd  ldarg.0
0x62de  ldnull
0x62df  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_OwnerMappings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x62e4  ldarg.0
0x62e5  ldnull
0x62e6  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_TransformationMappings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x62eb  ldarg.0
0x62ec  ldnull
0x62ed  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateWithMappingImportMapRequest::set_TransformationParameterMappings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x62f2  ret
```
