# Microsoft.Crm.Sdk.Crm2007.DeleteOptionValueRequest::Process

- ea: `0xc070`
- end: `0xc094`
- name: `Microsoft.Crm.Sdk.Crm2007.DeleteOptionValueRequest::Process`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xc0a0`
- `0xc0c0`
- `0xc0e0`
- `0xc120`

## pseudocode

```c

```

## disassembly

```asm
0xc070  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xc075  ldnull
0xc076  ldarg.0
0xc077  call     instance string Microsoft.Crm.Sdk.Crm2007.DeleteOptionValueRequest::get_AttributeLogicalName()
0xc07c  ldarg.0
0xc07d  call     instance string Microsoft.Crm.Sdk.Crm2007.DeleteOptionValueRequest::get_EntityLogicalName()
0xc082  ldarg.0
0xc083  call     instance int32 Microsoft.Crm.Sdk.Crm2007.DeleteOptionValueRequest::get_Value()
0xc088  ldarg.1
0xc089  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::DeleteOptionValue(string, string, string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc08e  newobj   instance void Microsoft.Crm.Sdk.Crm2007.DeleteOptionValueResponse::.ctor()
0xc093  ret
```
