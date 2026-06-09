# Microsoft.Crm.Sdk.Crm2007.CreateManyToManyRequest::Process

- ea: `0xb9b0`
- end: `0xb9d5`
- name: `Microsoft.Crm.Sdk.Crm2007.CreateManyToManyRequest::Process`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xb9e0`
- `0xba00`
- `0xba50`
- `0xba60`

## pseudocode

```c

```

## disassembly

```asm
0xb9b0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb9b5  ldarg.0
0xb9b6  call     instance string Microsoft.Crm.Sdk.Crm2007.CreateManyToManyRequest::get_IntersectEntitySchemaName()
0xb9bb  ldarg.0
0xb9bc  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata Microsoft.Crm.Sdk.Crm2007.CreateManyToManyRequest::get_ManyToManyRelationship()
0xb9c1  ldarg.1
0xb9c2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::CreateManyToMany(string, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb9c7  stloc.0
0xb9c8  newobj   instance void Microsoft.Crm.Sdk.Crm2007.CreateManyToManyResponse::.ctor()
0xb9cd  dup
0xb9ce  ldloc.0
0xb9cf  callvirt instance void Microsoft.Crm.Sdk.Crm2007.CreateManyToManyResponse::set_ManyToManyRelationshipId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key value)
0xb9d4  ret
```
