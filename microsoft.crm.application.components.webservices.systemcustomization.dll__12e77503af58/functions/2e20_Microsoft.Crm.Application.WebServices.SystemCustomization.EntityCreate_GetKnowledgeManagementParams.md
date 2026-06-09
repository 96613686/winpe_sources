# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetKnowledgeManagementParams

- ea: `0x2e20`
- end: `0x2e33`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetKnowledgeManagementParams`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x2e20  ldarg.0
0x2e21  ldarg.1
0x2e22  ldstr    aKnowledgemgmte// "knowledgemgmtenabled"
0x2e27  ldc.i4.0
0x2e28  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x2e2d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsKnowledgeManagementEnabled(bool)
0x2e32  ret
```
