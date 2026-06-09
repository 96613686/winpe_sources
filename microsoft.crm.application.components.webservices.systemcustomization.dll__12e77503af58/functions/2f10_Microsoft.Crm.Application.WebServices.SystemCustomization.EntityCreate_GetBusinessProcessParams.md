# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetBusinessProcessParams

- ea: `0x2f10`
- end: `0x2f22`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetBusinessProcessParams`
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
0x2f10  ldarg.0
0x2f11  ldarg.1
0x2f12  ldstr    aBusinessproces// "businessprocessenabled"
0x2f17  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2f1c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsBusinessProcessEnabled(bool)
0x2f21  ret
```
