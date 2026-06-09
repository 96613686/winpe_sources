# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAutoCreateAccessTeamsParams

- ea: `0x2e60`
- end: `0x2e72`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAutoCreateAccessTeamsParams`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x2b0`

## string_xrefs

- `0x2e62`: `autocreateaccessteams`

## pseudocode

```c

```

## disassembly

```asm
0x2e60  ldarg.0
0x2e61  ldarg.1
0x2e62  ldstr    aAutocreateacce// "autocreateaccessteams"
0x2e67  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2e6c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_AutoCreateAccessTeams(bool)
0x2e71  ret
```
