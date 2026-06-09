# Microsoft.Crm.Sdk.Crm2007.CreateAttributeRequest::Process

- ea: `0xb460`
- end: `0xb485`
- name: `Microsoft.Crm.Sdk.Crm2007.CreateAttributeRequest::Process`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xb500`
- `0xb510`

## pseudocode

```c

```

## disassembly

```asm
0xb460  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb465  ldarg.0
0xb466  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata Microsoft.Crm.Sdk.Crm2007.CreateAttributeRequest::_attribute
0xb46b  ldarg.0
0xb46c  ldfld    string Microsoft.Crm.Sdk.Crm2007.CreateAttributeRequest::_entityName
0xb471  ldarg.1
0xb472  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::CreateAttribute(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb477  stloc.0
0xb478  newobj   instance void Microsoft.Crm.Sdk.Crm2007.CreateAttributeResponse::.ctor()
0xb47d  dup
0xb47e  ldloc.0
0xb47f  callvirt instance void Microsoft.Crm.Sdk.Crm2007.CreateAttributeResponse::set_AttributeId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key value)
0xb484  ret
```
