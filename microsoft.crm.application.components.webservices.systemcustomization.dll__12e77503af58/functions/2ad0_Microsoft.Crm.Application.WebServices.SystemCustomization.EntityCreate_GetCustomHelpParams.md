# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetCustomHelpParams

- ea: `0x2ad0`
- end: `0x2b08`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetCustomHelpParams`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x220`
- `0x2b0`
- `0x2ad0`

## pseudocode

```c

```

## disassembly

```asm
0x2ad0  ldarg.1
0x2ad1  ldstr    aEntityhelpurle// "entityhelpurlenabled"
0x2ad6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2adb  brfalse.s loc_2B07
0x2add  ldarg.0
0x2ade  ldarg.1
0x2adf  ldstr    aEntityhelpurle// "entityhelpurlenabled"
0x2ae4  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2ae9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_EntityHelpUrlEnabled(bool)
0x2aee  ldarg.0
0x2aef  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityHelpUrlEnabled()
0x2af4  brfalse.s loc_2B07
0x2af6  ldarg.0
0x2af7  ldarg.1
0x2af8  ldstr    aEntityhelpurl// "entityhelpurl"
0x2afd  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x2b02  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_EntityHelpUrl(string)
0x2b07  ret
```
