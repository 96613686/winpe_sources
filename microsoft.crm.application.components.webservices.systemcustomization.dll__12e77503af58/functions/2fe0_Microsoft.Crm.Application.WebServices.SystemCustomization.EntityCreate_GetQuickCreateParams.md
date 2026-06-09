# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetQuickCreateParams

- ea: `0x2fe0`
- end: `0x2ff2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetQuickCreateParams`
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

- `0x2fe2`: `isquickcreateenabled`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldarg.0
0x2fe1  ldarg.1
0x2fe2  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x2fe7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2fec  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsQuickCreateEnabled(bool)
0x2ff1  ret
```
