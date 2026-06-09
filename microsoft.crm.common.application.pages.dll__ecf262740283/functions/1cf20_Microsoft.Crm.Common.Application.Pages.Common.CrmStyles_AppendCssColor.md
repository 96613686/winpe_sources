# Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor

- ea: `0x1cf20`
- end: `0x1cf51`
- name: `Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1ca60`
- `0x1cf60`

## callees

- `0x1cf20`
- `0x1d000`

## pseudocode

```c

```

## disassembly

```asm
0x1cf20  ldarga.s 3
0x1cf22  call     instance bool [System.Drawing]System.Drawing.Color::get_IsEmpty()
0x1cf27  brtrue.s loc_1CF50
0x1cf29  ldstr    a01_1// "\t{0}:{1};\n"
0x1cf2e  stloc.0
0x1cf2f  ldarg.1
0x1cf30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cf35  ldloc.0
0x1cf36  ldc.i4.2
0x1cf37  newarr   [mscorlib]System.Object
0x1cf3c  dup
0x1cf3d  ldc.i4.0
0x1cf3e  ldarg.2
0x1cf3f  stelem.ref
0x1cf40  dup
0x1cf41  ldc.i4.1
0x1cf42  ldarg.0
0x1cf43  ldarg.3
0x1cf44  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssColor(valuetype [System.Drawing]System.Drawing.Color color)
0x1cf49  stelem.ref
0x1cf4a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1cf4f  pop
0x1cf50  ret
```
