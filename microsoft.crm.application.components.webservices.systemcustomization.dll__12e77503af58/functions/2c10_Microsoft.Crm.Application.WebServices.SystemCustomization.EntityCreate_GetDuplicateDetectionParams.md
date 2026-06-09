# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDuplicateDetectionParams

- ea: `0x2c10`
- end: `0x2c22`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDuplicateDetectionParams`
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
0x2c10  ldarg.0
0x2c11  ldarg.1
0x2c12  ldstr    aDuplicatecheck// "duplicatecheck"
0x2c17  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2c1c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsDuplicateCheckSupported(bool)
0x2c21  ret
```
