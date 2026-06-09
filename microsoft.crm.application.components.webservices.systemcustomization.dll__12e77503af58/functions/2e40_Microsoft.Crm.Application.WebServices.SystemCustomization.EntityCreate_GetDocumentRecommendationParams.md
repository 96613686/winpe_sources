# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDocumentRecommendationParams

- ea: `0x2e40`
- end: `0x2e53`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDocumentRecommendationParams`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x290`

## string_xrefs

- `0x2e42`: `documentrecommendationsenabled`

## pseudocode

```c

```

## disassembly

```asm
0x2e40  ldarg.0
0x2e41  ldarg.1
0x2e42  ldstr    aDocumentrecomm// "documentrecommendationsenabled"
0x2e47  ldc.i4.0
0x2e48  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x2e4d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsDocumentRecommendationsEnabled(bool)
0x2e52  ret
```
