# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAutoCreateAccessTeamsParams

- ea: `0x3e20`
- end: `0x3e3f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAutoCreateAccessTeamsParams`
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
- `0x3e20`

## string_xrefs

- `0x3e21`: `autocreateaccessteams`
- `0x3e2f`: `autocreateaccessteams`

## pseudocode

```c

```

## disassembly

```asm
0x3e20  ldarg.1
0x3e21  ldstr    aAutocreateacce// "autocreateaccessteams"
0x3e26  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3e2b  brfalse.s loc_3E3E
0x3e2d  ldarg.0
0x3e2e  ldarg.1
0x3e2f  ldstr    aAutocreateacce// "autocreateaccessteams"
0x3e34  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3e39  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AutoCreateAccessTeams(bool)
0x3e3e  ret
```
