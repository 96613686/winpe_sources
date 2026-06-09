# Microsoft.Crm.Sdk.Crm2007.CreateOneToManyRequest::Process

- ea: `0xb6a0`
- end: `0xb6d0`
- name: `Microsoft.Crm.Sdk.Crm2007.CreateOneToManyRequest::Process`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xb6d0`
- `0xb6f0`
- `0xb740`
- `0xb760`
- `0xb770`

## pseudocode

```c

```

## disassembly

```asm
0xb6a0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb6a5  ldnull
0xb6a6  stloc.0
0xb6a7  ldarg.0
0xb6a8  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata Microsoft.Crm.Sdk.Crm2007.CreateOneToManyRequest::get_Lookup()
0xb6ad  ldarg.0
0xb6ae  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata Microsoft.Crm.Sdk.Crm2007.CreateOneToManyRequest::get_OneToManyRelationship()
0xb6b3  ldarg.1
0xb6b4  ldloca.s 0
0xb6b6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::CreateOneToMany(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key&)
0xb6bb  stloc.1
0xb6bc  newobj   instance void Microsoft.Crm.Sdk.Crm2007.CreateOneToManyResponse::.ctor()
0xb6c1  dup
0xb6c2  ldloc.1
0xb6c3  callvirt instance void Microsoft.Crm.Sdk.Crm2007.CreateOneToManyResponse::set_RelationshipId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key value)
0xb6c8  dup
0xb6c9  ldloc.0
0xb6ca  callvirt instance void Microsoft.Crm.Sdk.Crm2007.CreateOneToManyResponse::set_AttributeId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key value)
0xb6cf  ret
```
