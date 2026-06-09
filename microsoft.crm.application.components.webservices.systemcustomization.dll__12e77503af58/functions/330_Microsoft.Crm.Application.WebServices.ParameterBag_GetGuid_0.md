# Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid_0

- ea: `0x330`
- end: `0x33d`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid_0`
- size: `13`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x390`
- `0xaf0`
- `0x20e0`
- `0x26f0`
- `0x2d10`
- `0x3140`
- `0x31b0`
- `0x3450`
- `0x37d0`
- `0x3880`
- `0x3cd0`
- `0x9850`
- `0x9bd0`
- `0xa600`
- `0xa6b0`
- `0xa7f0`

## callees

- `0x220`

## pseudocode

```c

```

## disassembly

```asm
0x330  ldarg.0
0x331  ldarg.1
0x332  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x337  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x33c  ret
```
