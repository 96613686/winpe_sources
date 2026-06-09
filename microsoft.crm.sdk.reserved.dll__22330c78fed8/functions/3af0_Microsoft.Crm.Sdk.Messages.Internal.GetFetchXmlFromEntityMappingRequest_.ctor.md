# Microsoft.Crm.Sdk.Messages.Internal.GetFetchXmlFromEntityMappingRequest::.ctor

- ea: `0x3af0`
- end: `0x3b17`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetFetchXmlFromEntityMappingRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3a30`
- `0x3a80`
- `0x3ad0`

## string_xrefs

- `0x3af7`: `GetFetchXmlFromEntityMapping`

## pseudocode

```c

```

## disassembly

```asm
0x3af0  ldarg.0
0x3af1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x3af6  ldarg.0
0x3af7  ldstr    aGetfetchxmlfro// "GetFetchXmlFromEntityMapping"
0x3afc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x3b01  ldarg.0
0x3b02  ldnull
0x3b03  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetFetchXmlFromEntityMappingRequest::set_Entities(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection value)
0x3b08  ldarg.0
0x3b09  ldnull
0x3b0a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetFetchXmlFromEntityMappingRequest::set_SourceEntityName(string value)
0x3b0f  ldarg.0
0x3b10  ldnull
0x3b11  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetFetchXmlFromEntityMappingRequest::set_SourceEntityConditions(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase value)
0x3b16  ret
```
