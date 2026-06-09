# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetCollaborationParams

- ea: `0x2c30`
- end: `0x2c53`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetCollaborationParams`
- size: `35`
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
0x2c30  ldarg.0
0x2c31  ldarg.1
0x2c32  ldstr    aCollaboration// "collaboration"
0x2c37  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2c3c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsCollaboration(bool)
0x2c41  ldarg.0
0x2c42  ldarg.1
0x2c43  ldstr    aAutoroutetoown// "autoroutetoownerqueue"
0x2c48  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2c4d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_AutoRouteToOwnerQueue(bool)
0x2c52  ret
```
