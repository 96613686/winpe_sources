# Microsoft.Crm.Application.WebServices.ParameterBag::GetInt_0

- ea: `0x270`
- end: `0x282`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetInt_0`
- size: `18`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`
- `0xbe0`
- `0x1000`
- `0x14e0`
- `0x1580`
- `0x1650`
- `0x1740`
- `0x1a10`
- `0x2220`
- `0x2f50`
- `0x3450`
- `0x9850`
- `0x9a10`
- `0x9bd0`
- `0xa3d0`
- `0xa6b0`
- `0xa7f0`
- `0xaa00`

## callees

- `0x220`

## pseudocode

```c

```

## disassembly

```asm
0x270  ldarg.0
0x271  ldarg.1
0x272  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x277  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x281  ret
```
