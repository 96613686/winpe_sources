# Microsoft.Crm.Sdk.Crm2007.DeleteRelationshipRequest::Process

- ea: `0xb930`
- end: `0xb947`
- name: `Microsoft.Crm.Sdk.Crm2007.DeleteRelationshipRequest::Process`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xb950`
- `0xb990`

## pseudocode

```c

```

## disassembly

```asm
0xb930  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb935  ldarg.0
0xb936  call     instance string Microsoft.Crm.Sdk.Crm2007.DeleteRelationshipRequest::get_Name()
0xb93b  ldarg.1
0xb93c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::DeleteRelationship(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb941  newobj   instance void Microsoft.Crm.Sdk.Crm2007.DeleteRelationshipResponse::.ctor()
0xb946  ret
```
