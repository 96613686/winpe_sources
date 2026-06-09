# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetMailMergeParams

- ea: `0x2bf0`
- end: `0x2c02`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetMailMergeParams`
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
0x2bf0  ldarg.0
0x2bf1  ldarg.1
0x2bf2  ldstr    aMailmergecheck// "mailmergecheck"
0x2bf7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2bfc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsMailMergeEnabled(bool)
0x2c01  ret
```
