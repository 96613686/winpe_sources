# Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty

- ea: `0x14c0`
- end: `0x14cc`
- name: `Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty`
- size: `12`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbf0`
- `0xcd0`
- `0xcf0`
- `0xd10`
- `0xda0`
- `0xf20`
- `0xfe0`
- `0x1000`
- `0x1020`
- `0x1110`
- `0x1240`

## callees

- `0x1440`
- `0x1470`

## pseudocode

```c

```

## disassembly

```asm
0x14c0  ldarg.0
0x14c1  call     instance class Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::get_EntityAttributePropertyProvider()
0x14c6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x14cb  ret
```
