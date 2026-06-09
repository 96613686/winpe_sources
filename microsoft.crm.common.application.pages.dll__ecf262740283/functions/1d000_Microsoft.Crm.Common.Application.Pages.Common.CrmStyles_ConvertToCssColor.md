# Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssColor

- ea: `0x1d000`
- end: `0x1d043`
- name: `Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssColor`
- size: `67`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1cdd0`
- `0x1cf20`
- `0x1cf80`
- `0x1d120`

## pseudocode

```c

```

## disassembly

```asm
0x1d000  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d005  ldstr    a0X21X22X2// "#{0:X2}{1:X2}{2:X2}"
0x1d00a  ldc.i4.3
0x1d00b  newarr   [mscorlib]System.Object
0x1d010  dup
0x1d011  ldc.i4.0
0x1d012  ldarga.s 1
0x1d014  call     instance unsigned int8 [System.Drawing]System.Drawing.Color::get_R()
0x1d019  box      [mscorlib]System.Byte
0x1d01e  stelem.ref
0x1d01f  dup
0x1d020  ldc.i4.1
0x1d021  ldarga.s 1
0x1d023  call     instance unsigned int8 [System.Drawing]System.Drawing.Color::get_G()
0x1d028  box      [mscorlib]System.Byte
0x1d02d  stelem.ref
0x1d02e  dup
0x1d02f  ldc.i4.2
0x1d030  ldarga.s 1
0x1d032  call     instance unsigned int8 [System.Drawing]System.Drawing.Color::get_B()
0x1d037  box      [mscorlib]System.Byte
0x1d03c  stelem.ref
0x1d03d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1d042  ret
```
