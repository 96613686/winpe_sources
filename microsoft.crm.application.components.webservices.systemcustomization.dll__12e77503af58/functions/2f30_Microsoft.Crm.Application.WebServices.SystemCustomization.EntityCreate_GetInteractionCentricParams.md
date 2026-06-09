# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetInteractionCentricParams

- ea: `0x2f30`
- end: `0x2f4f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetInteractionCentricParams`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x2b0`
- `0x2f30`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldarg.1
0x2f31  ldstr    aInteractioncen// "interactioncentricenabled"
0x2f36  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2f3b  brfalse.s loc_2F4E
0x2f3d  ldarg.0
0x2f3e  ldarg.1
0x2f3f  ldstr    aInteractioncen// "interactioncentricenabled"
0x2f44  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2f49  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsInteractionCentricEnabled(bool)
0x2f4e  ret
```
