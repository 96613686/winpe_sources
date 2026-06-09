# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetConnectionsParams

- ea: `0x2ef0`
- end: `0x2f02`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetConnectionsParams`
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
0x2ef0  ldarg.0
0x2ef1  ldarg.1
0x2ef2  ldstr    aConnection// "connection"
0x2ef7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2efc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsConnectionsEnabled(bool)
0x2f01  ret
```
