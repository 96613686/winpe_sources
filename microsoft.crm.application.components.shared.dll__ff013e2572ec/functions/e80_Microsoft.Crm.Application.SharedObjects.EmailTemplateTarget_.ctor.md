# Microsoft.Crm.Application.SharedObjects.EmailTemplateTarget::.ctor

- ea: `0xe80`
- end: `0xea4`
- name: `Microsoft.Crm.Application.SharedObjects.EmailTemplateTarget::.ctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xec0`
- `0xee0`
- `0xf00`
- `0xf20`

## pseudocode

```c

```

## disassembly

```asm
0xe80  ldarg.0
0xe81  call     instance void [mscorlib]System.Object::.ctor()
0xe86  ldarg.0
0xe87  ldarg.1
0xe88  call     instance void Microsoft.Crm.Application.SharedObjects.EmailTemplateTarget::set_id(string value)
0xe8d  ldarg.0
0xe8e  ldarg.2
0xe8f  call     instance void Microsoft.Crm.Application.SharedObjects.EmailTemplateTarget::set_type(int32 value)
0xe94  ldarg.0
0xe95  ldarg.3
0xe96  call     instance void Microsoft.Crm.Application.SharedObjects.EmailTemplateTarget::set_name(string value)
0xe9b  ldarg.0
0xe9c  ldarg.s  4
0xe9e  call     instance void Microsoft.Crm.Application.SharedObjects.EmailTemplateTarget::set_source(string value)
0xea3  ret
```
