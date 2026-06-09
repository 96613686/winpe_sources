# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetSlaParams

- ea: `0x3e00`
- end: `0x3e1f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetSlaParams`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3e00`

## pseudocode

```c

```

## disassembly

```asm
0x3e00  ldarg.1
0x3e01  ldstr    aIsslaenabled// "isslaenabled"
0x3e06  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3e0b  brfalse.s loc_3E1E
0x3e0d  ldarg.0
0x3e0e  ldarg.1
0x3e0f  ldstr    aIsslaenabled// "isslaenabled"
0x3e14  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3e19  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsSLAEnabled(bool)
0x3e1e  ret
```
