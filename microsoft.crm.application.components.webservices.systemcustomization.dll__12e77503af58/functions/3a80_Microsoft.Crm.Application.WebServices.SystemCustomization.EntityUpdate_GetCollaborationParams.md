# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetCollaborationParams

- ea: `0x3a80`
- end: `0x3abd`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetCollaborationParams`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3a80`

## pseudocode

```c

```

## disassembly

```asm
0x3a80  ldarg.1
0x3a81  ldstr    aCollaboration// "collaboration"
0x3a86  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3a8b  brfalse.s loc_3A9E
0x3a8d  ldarg.0
0x3a8e  ldarg.1
0x3a8f  ldstr    aCollaboration// "collaboration"
0x3a94  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3a99  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsCollaboration(bool)
0x3a9e  ldarg.1
0x3a9f  ldstr    aAutoroutetoown// "autoroutetoownerqueue"
0x3aa4  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3aa9  brfalse.s loc_3ABC
0x3aab  ldarg.0
0x3aac  ldarg.1
0x3aad  ldstr    aAutoroutetoown// "autoroutetoownerqueue"
0x3ab2  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3ab7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AutoRouteToOwnerQueue(bool)
0x3abc  ret
```
