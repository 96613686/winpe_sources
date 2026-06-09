# Microsoft.Crm.Application.WebServices.ParameterBag::GetString_0

- ea: `0x220`
- end: `0x230`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetString_0`
- size: `16`
- prototype: ``
- caller_count: `34`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x230`
- `0x270`
- `0x2b0`
- `0x2f0`
- `0x330`
- `0x360`
- `0x430`
- `0xaf0`
- `0xbe0`
- `0x1000`
- `0x1400`
- `0x1580`
- `0x1650`
- `0x17d0`
- `0x1a10`
- `0x1b90`
- `0x1ed0`
- `0x2a00`
- `0x2ad0`
- `0x2b10`
- `0x31b0`
- `0x3920`
- `0x4230`
- `0x9850`
- `0x9a10`
- `0x9bd0`
- `0x9e50`
- `0x9fe0`
- `0xa0c0`
- `0xa3d0`
- `0xa600`
- `0xa6b0`
- `0xa7f0`
- `0xaa00`

## callees

- `0x200`

## pseudocode

```c

```

## disassembly

```asm
0x220  ldarg.0
0x221  ldarg.1
0x222  ldnull
0x223  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x228  dup
0x229  ldarg.1
0x22a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x22f  ret
```
