# Microsoft.Crm.Sdk.Crm2007.DeleteEntityRequest::Process

- ea: `0xb3e0`
- end: `0xb3f7`
- name: `Microsoft.Crm.Sdk.Crm2007.DeleteEntityRequest::Process`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xb400`
- `0xb440`

## pseudocode

```c

```

## disassembly

```asm
0xb3e0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb3e5  ldarg.0
0xb3e6  call     instance string Microsoft.Crm.Sdk.Crm2007.DeleteEntityRequest::get_LogicalName()
0xb3eb  ldarg.1
0xb3ec  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::DeleteEntity(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb3f1  newobj   instance void Microsoft.Crm.Sdk.Crm2007.DeleteEntityResponse::.ctor()
0xb3f6  ret
```
