# Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble

- ea: `0x2c0`
- end: `0x2e3`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e0`
- `0x1580`
- `0x1650`

## callees

- `0x200`
- `0x2c0`

## pseudocode

```c

```

## disassembly

```asm
0x2c0  ldarg.0
0x2c1  ldarg.1
0x2c2  ldnull
0x2c3  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x2c8  stloc.0
0x2c9  ldloc.0
0x2ca  brfalse.s loc_2D5
0x2cc  ldloc.0
0x2cd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d2  ldc.i4.0
0x2d3  bgt.s    loc_2D7
0x2d5  ldarg.2
0x2d6  ret
0x2d7  ldloc.0
0x2d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2dd  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x2e2  ret
```
