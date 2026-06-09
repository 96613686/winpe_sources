# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAttributeParams

- ea: `0x2b70`
- end: `0x2b85`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAttributeParams`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x430`
- `0x3000`

## pseudocode

```c

```

## disassembly

```asm
0x2b70  ldarg.0
0x2b71  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetParentEntityPrimaryAttribute(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo)
0x2b76  stloc.0
0x2b77  ldarg.0
0x2b78  ldarg.1
0x2b79  ldloc.0
0x2b7a  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x2b7f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_PrimaryField(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo)
0x2b84  ret
```
