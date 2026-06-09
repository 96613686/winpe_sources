# Microsoft.Crm.Sdk.Crm2007.DeleteAttributeRequest::Process

- ea: `0xb600`
- end: `0xb61d`
- name: `Microsoft.Crm.Sdk.Crm2007.DeleteAttributeRequest::Process`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xb620`
- `0xb640`
- `0xb680`

## pseudocode

```c

```

## disassembly

```asm
0xb600  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb605  ldarg.0
0xb606  call     instance string Microsoft.Crm.Sdk.Crm2007.DeleteAttributeRequest::get_LogicalName()
0xb60b  ldarg.0
0xb60c  call     instance string Microsoft.Crm.Sdk.Crm2007.DeleteAttributeRequest::get_EntityLogicalName()
0xb611  ldarg.1
0xb612  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::DeleteAttribute(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb617  newobj   instance void Microsoft.Crm.Sdk.Crm2007.DeleteAttributeResponse::.ctor()
0xb61c  ret
```
