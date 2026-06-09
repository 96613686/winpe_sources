# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDocumentManagementParams

- ea: `0x2cf0`
- end: `0x2d02`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDocumentManagementParams`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x2cf0  ldarg.0
0x2cf1  ldarg.1
0x2cf2  ldstr    aDocmgmtenabled// "docmgmtenabled"
0x2cf7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2cfc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsDocumentManagementEnabled(bool)
0x2d01  ret
```
