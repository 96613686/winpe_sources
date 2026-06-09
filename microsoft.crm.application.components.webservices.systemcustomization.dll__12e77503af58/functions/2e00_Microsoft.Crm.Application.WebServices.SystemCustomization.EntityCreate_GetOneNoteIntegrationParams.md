# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetOneNoteIntegrationParams

- ea: `0x2e00`
- end: `0x2e13`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetOneNoteIntegrationParams`
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
0x2e00  ldarg.0
0x2e01  ldarg.1
0x2e02  ldstr    aOnenoteintegra// "onenoteintegrationenabled"
0x2e07  ldc.i4.0
0x2e08  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x2e0d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsOneNoteIntegrationEnabled(bool)
0x2e12  ret
```
