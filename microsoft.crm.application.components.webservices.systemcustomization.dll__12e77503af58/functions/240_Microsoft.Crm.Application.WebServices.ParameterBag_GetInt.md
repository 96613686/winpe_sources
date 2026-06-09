# Microsoft.Crm.Application.WebServices.ParameterBag::GetInt

- ea: `0x240`
- end: `0x263`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetInt`
- size: `35`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf0`
- `0x1400`
- `0x14e0`
- `0x1580`
- `0x1650`
- `0x1740`
- `0x9fe0`
- `0xa0c0`

## callees

- `0x200`
- `0x240`

## pseudocode

```c

```

## disassembly

```asm
0x240  ldarg.0
0x241  ldarg.1
0x242  ldnull
0x243  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x248  stloc.0
0x249  ldloc.0
0x24a  brfalse.s loc_255
0x24c  ldloc.0
0x24d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x252  ldc.i4.0
0x253  bgt.s    loc_257
0x255  ldarg.2
0x256  ret
0x257  ldloc.0
0x258  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25d  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x262  ret
```
