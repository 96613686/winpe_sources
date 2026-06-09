# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo

- ea: `0x420`
- end: `0x428`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x390`
- `0x1ed0`

## callees

- `0x430`

## pseudocode

```c

```

## disassembly

```asm
0x420  ldarg.0
0x421  ldnull
0x422  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x427  ret
```
