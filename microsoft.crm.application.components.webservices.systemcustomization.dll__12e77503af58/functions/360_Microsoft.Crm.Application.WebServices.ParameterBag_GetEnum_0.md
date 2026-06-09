# Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum_0

- ea: `0x360`
- end: `0x36e`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum_0`
- size: `14`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`
- `0x2a00`
- `0xa0c0`
- `0xa300`
- `0xa3d0`
- `0xa7f0`
- `0xaa00`
- `0xaac0`

## callees

- `0x220`

## pseudocode

```c

```

## disassembly

```asm
0x360  ldarg.2
0x361  ldarg.0
0x362  ldarg.1
0x363  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x368  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x36d  ret
```
