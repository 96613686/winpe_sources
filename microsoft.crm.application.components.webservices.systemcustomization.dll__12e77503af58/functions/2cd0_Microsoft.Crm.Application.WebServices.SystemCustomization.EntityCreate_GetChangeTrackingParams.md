# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetChangeTrackingParams

- ea: `0x2cd0`
- end: `0x2ce3`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetChangeTrackingParams`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x2cd0  ldarg.0
0x2cd1  ldarg.1
0x2cd2  ldstr    aChangetracking// "changetrackingenabled"
0x2cd7  ldc.i4.0
0x2cd8  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x2cdd  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_ChangeTrackingEnabled(bool)
0x2ce2  ret
```
