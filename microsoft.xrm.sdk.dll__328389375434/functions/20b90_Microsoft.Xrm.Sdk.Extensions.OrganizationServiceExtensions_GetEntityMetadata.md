# Microsoft.Xrm.Sdk.Extensions.OrganizationServiceExtensions::GetEntityMetadata

- ea: `0x20b90`
- end: `0x20bb7`
- name: `Microsoft.Xrm.Sdk.Extensions.OrganizationServiceExtensions::GetEntityMetadata`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x7aa0`
- `0x10650`
- `0x106a0`
- `0x10770`
- `0x107c0`

## pseudocode

```c

```

## disassembly

```asm
0x20b90  newobj   instance void Microsoft.Xrm.Sdk.Messages.RetrieveEntityRequest::.ctor()
0x20b95  dup
0x20b96  ldc.i4.s 0xB
0x20b98  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveEntityRequest::set_EntityFilters(valuetype Microsoft.Xrm.Sdk.Metadata.EntityFilters value)
0x20b9d  dup
0x20b9e  ldarg.1
0x20b9f  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveEntityRequest::set_LogicalName(string value)
0x20ba4  stloc.0
0x20ba5  ldarg.0
0x20ba6  ldloc.0
0x20ba7  callvirt instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.IOrganizationService::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x20bac  castclass Microsoft.Xrm.Sdk.Messages.RetrieveEntityResponse
0x20bb1  callvirt instance class Microsoft.Xrm.Sdk.Metadata.EntityMetadata Microsoft.Xrm.Sdk.Messages.RetrieveEntityResponse::get_EntityMetadata()
0x20bb6  ret
```
