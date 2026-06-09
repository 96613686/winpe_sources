# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetRichClientParams

- ea: `0x2bd0`
- end: `0x2be2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetRichClientParams`
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
0x2bd0  ldarg.0
0x2bd1  ldarg.1
0x2bd2  ldstr    aOffline// "offline"
0x2bd7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2bdc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_AvailableOffline(bool)
0x2be1  ret
```
