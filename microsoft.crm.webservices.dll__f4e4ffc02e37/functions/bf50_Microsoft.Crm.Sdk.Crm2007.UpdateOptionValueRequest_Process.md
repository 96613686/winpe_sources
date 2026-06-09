# Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::Process

- ea: `0xbf50`
- end: `0xbf81`
- name: `Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::Process`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0xbf90`
- `0xbfb0`
- `0xbfd0`
- `0xbff0`
- `0xc010`
- `0xc050`

## pseudocode

```c

```

## disassembly

```asm
0xbf50  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xbf55  ldnull
0xbf56  ldarg.0
0xbf57  call     instance string Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::get_AttributeLogicalName()
0xbf5c  ldarg.0
0xbf5d  call     instance string Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::get_EntityLogicalName()
0xbf62  ldarg.0
0xbf63  call     instance int32 Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::get_Value()
0xbf68  ldarg.0
0xbf69  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::get_Label()
0xbf6e  ldnull
0xbf6f  ldarg.0
0xbf70  call     instance bool Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueRequest::get_MergeLabels()
0xbf75  ldarg.1
0xbf76  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::UpdateOptionValue(string, string, string, int32, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbf7b  newobj   instance void Microsoft.Crm.Sdk.Crm2007.UpdateOptionValueResponse::.ctor()
0xbf80  ret
```
