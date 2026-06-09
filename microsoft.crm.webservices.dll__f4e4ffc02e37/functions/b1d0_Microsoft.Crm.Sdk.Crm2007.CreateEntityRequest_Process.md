# Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::Process

- ea: `0xb1d0`
- end: `0xb212`
- name: `Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::Process`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0xb220`
- `0xb240`
- `0xb260`
- `0xb280`
- `0xb2a0`
- `0xb2f0`
- `0xb310`
- `0xb320`

## pseudocode

```c

```

## disassembly

```asm
0xb1d0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb1d5  ldnull
0xb1d6  stloc.0
0xb1d7  ldarg.0
0xb1d8  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::get_Entity()
0xb1dd  ldarg.0
0xb1de  call     instance bool Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::get_HasActivities()
0xb1e3  ldarg.0
0xb1e4  call     instance bool Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::get_HasNotes()
0xb1e9  ldarg.0
0xb1ea  call     instance bool Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::get_HasFeedback()
0xb1ef  ldarg.0
0xb1f0  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata Microsoft.Crm.Sdk.Crm2007.CreateEntityRequest::get_PrimaryAttribute()
0xb1f5  ldarg.1
0xb1f6  ldloca.s 0
0xb1f8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::CreateEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata, bool, bool, bool, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key&)
0xb1fd  stloc.1
0xb1fe  newobj   instance void Microsoft.Crm.Sdk.Crm2007.CreateEntityResponse::.ctor()
0xb203  dup
0xb204  ldloc.1
0xb205  callvirt instance void Microsoft.Crm.Sdk.Crm2007.CreateEntityResponse::set_EntityId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key value)
0xb20a  dup
0xb20b  ldloc.0
0xb20c  callvirt instance void Microsoft.Crm.Sdk.Crm2007.CreateEntityResponse::set_AttributeId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key value)
0xb211  ret
```
