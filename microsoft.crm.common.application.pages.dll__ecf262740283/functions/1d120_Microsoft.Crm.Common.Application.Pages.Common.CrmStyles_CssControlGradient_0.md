# Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::CssControlGradient_0

- ea: `0x1d120`
- end: `0x1d358`
- name: `Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::CssControlGradient_0`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1d100`

## callees

- `0x1d000`
- `0x1d120`
- `0x1d3c0`
- `0x1d410`

## pseudocode

```c

```

## disassembly

```asm
0x1d120  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1d125  stloc.0
0x1d126  ldsfld   string [mscorlib]System.String::Empty
0x1d12b  stloc.1
0x1d12c  ldarg.s  8
0x1d12e  brfalse.s loc_1D136
0x1d130  ldstr    aImportant// "!important"
0x1d135  stloc.1
0x1d136  ldarg.s  6
0x1d138  brfalse.s loc_1D165
0x1d13a  ldloc.0
0x1d13b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d140  ldstr    aBackground012// "background: {0} {1} {2};"
0x1d145  ldc.i4.3
0x1d146  newarr   [mscorlib]System.Object
0x1d14b  dup
0x1d14c  ldc.i4.0
0x1d14d  ldarg.0
0x1d14e  ldarg.1
0x1d14f  ldarg.s  7
0x1d151  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d156  stelem.ref
0x1d157  dup
0x1d158  ldc.i4.1
0x1d159  ldarg.2
0x1d15a  stelem.ref
0x1d15b  dup
0x1d15c  ldc.i4.2
0x1d15d  ldloc.1
0x1d15e  stelem.ref
0x1d15f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d164  pop
0x1d165  ldloc.0
0x1d166  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d16b  ldstr    aBackgroundMozL_0// "background: -moz-linear-gradient({0},  "...
0x1d170  ldc.i4.6
0x1d171  newarr   [mscorlib]System.Object
0x1d176  dup
0x1d177  ldc.i4.0
0x1d178  ldarg.s  5
0x1d17a  stelem.ref
0x1d17b  dup
0x1d17c  ldc.i4.1
0x1d17d  ldarg.0
0x1d17e  ldarg.1
0x1d17f  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGB(valuetype [System.Drawing]System.Drawing.Color color)
0x1d184  stelem.ref
0x1d185  dup
0x1d186  ldc.i4.2
0x1d187  ldarg.2
0x1d188  stelem.ref
0x1d189  dup
0x1d18a  ldc.i4.3
0x1d18b  ldarg.0
0x1d18c  ldarg.3
0x1d18d  ldc.r8   0.0
0x1d196  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d19b  stelem.ref
0x1d19c  dup
0x1d19d  ldc.i4.4
0x1d19e  ldarg.s  4
0x1d1a0  stelem.ref
0x1d1a1  dup
0x1d1a2  ldc.i4.5
0x1d1a3  ldloc.1
0x1d1a4  stelem.ref
0x1d1a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d1aa  pop
0x1d1ab  ldarg.s  5
0x1d1ad  ldstr    aLeft// "left"
0x1d1b2  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d1b7  brfalse.s loc_1D201
0x1d1b9  ldloc.0
0x1d1ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d1bf  ldstr    aBackgroundWebk_0// "background: -webkit-gradient(linear,{0}"...
0x1d1c4  ldc.i4.6
0x1d1c5  newarr   [mscorlib]System.Object
0x1d1ca  dup
0x1d1cb  ldc.i4.0
0x1d1cc  ldarg.s  5
0x1d1ce  stelem.ref
0x1d1cf  dup
0x1d1d0  ldc.i4.1
0x1d1d1  ldarg.2
0x1d1d2  stelem.ref
0x1d1d3  dup
0x1d1d4  ldc.i4.2
0x1d1d5  ldarg.0
0x1d1d6  ldarg.1
0x1d1d7  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGB(valuetype [System.Drawing]System.Drawing.Color color)
0x1d1dc  stelem.ref
0x1d1dd  dup
0x1d1de  ldc.i4.3
0x1d1df  ldarg.s  4
0x1d1e1  stelem.ref
0x1d1e2  dup
0x1d1e3  ldc.i4.4
0x1d1e4  ldarg.0
0x1d1e5  ldarg.3
0x1d1e6  ldc.r8   0.0
0x1d1ef  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d1f4  stelem.ref
0x1d1f5  dup
0x1d1f6  ldc.i4.5
0x1d1f7  ldloc.1
0x1d1f8  stelem.ref
0x1d1f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d1fe  pop
0x1d1ff  br.s     loc_1D247
0x1d201  ldloc.0
0x1d202  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d207  ldstr    aBackgroundWebk_1// "background: -webkit-gradient(linear,{0}"...
0x1d20c  ldc.i4.6
0x1d20d  newarr   [mscorlib]System.Object
0x1d212  dup
0x1d213  ldc.i4.0
0x1d214  ldarg.s  5
0x1d216  stelem.ref
0x1d217  dup
0x1d218  ldc.i4.1
0x1d219  ldarg.2
0x1d21a  stelem.ref
0x1d21b  dup
0x1d21c  ldc.i4.2
0x1d21d  ldarg.0
0x1d21e  ldarg.1
0x1d21f  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGB(valuetype [System.Drawing]System.Drawing.Color color)
0x1d224  stelem.ref
0x1d225  dup
0x1d226  ldc.i4.3
0x1d227  ldarg.s  4
0x1d229  stelem.ref
0x1d22a  dup
0x1d22b  ldc.i4.4
0x1d22c  ldarg.0
0x1d22d  ldarg.3
0x1d22e  ldc.r8   0.0
0x1d237  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d23c  stelem.ref
0x1d23d  dup
0x1d23e  ldc.i4.5
0x1d23f  ldloc.1
0x1d240  stelem.ref
0x1d241  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d246  pop
0x1d247  ldloc.0
0x1d248  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d24d  ldstr    aBackgroundWebk_2// "background: -webkit-linear-gradient({0}"...
0x1d252  ldc.i4.6
0x1d253  newarr   [mscorlib]System.Object
0x1d258  dup
0x1d259  ldc.i4.0
0x1d25a  ldarg.s  5
0x1d25c  stelem.ref
0x1d25d  dup
0x1d25e  ldc.i4.1
0x1d25f  ldarg.0
0x1d260  ldarg.1
0x1d261  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGB(valuetype [System.Drawing]System.Drawing.Color color)
0x1d266  stelem.ref
0x1d267  dup
0x1d268  ldc.i4.2
0x1d269  ldarg.2
0x1d26a  stelem.ref
0x1d26b  dup
0x1d26c  ldc.i4.3
0x1d26d  ldarg.0
0x1d26e  ldarg.3
0x1d26f  ldc.r8   0.0
0x1d278  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d27d  stelem.ref
0x1d27e  dup
0x1d27f  ldc.i4.4
0x1d280  ldarg.s  4
0x1d282  stelem.ref
0x1d283  dup
0x1d284  ldc.i4.5
0x1d285  ldloc.1
0x1d286  stelem.ref
0x1d287  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d28c  pop
0x1d28d  ldloc.0
0x1d28e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d293  ldstr    aBackgroundMsLi_0// "background: -ms-linear-gradient({0},  {"...
0x1d298  ldc.i4.6
0x1d299  newarr   [mscorlib]System.Object
0x1d29e  dup
0x1d29f  ldc.i4.0
0x1d2a0  ldarg.s  5
0x1d2a2  stelem.ref
0x1d2a3  dup
0x1d2a4  ldc.i4.1
0x1d2a5  ldarg.0
0x1d2a6  ldarg.1
0x1d2a7  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGB(valuetype [System.Drawing]System.Drawing.Color color)
0x1d2ac  stelem.ref
0x1d2ad  dup
0x1d2ae  ldc.i4.2
0x1d2af  ldarg.2
0x1d2b0  stelem.ref
0x1d2b1  dup
0x1d2b2  ldc.i4.3
0x1d2b3  ldarg.0
0x1d2b4  ldarg.3
0x1d2b5  ldc.r8   0.0
0x1d2be  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d2c3  stelem.ref
0x1d2c4  dup
0x1d2c5  ldc.i4.4
0x1d2c6  ldarg.s  4
0x1d2c8  stelem.ref
0x1d2c9  dup
0x1d2ca  ldc.i4.5
0x1d2cb  ldloc.1
0x1d2cc  stelem.ref
0x1d2cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d2d2  pop
0x1d2d3  ldloc.0
0x1d2d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d2d9  ldstr    aBackgroundLine_0// "background: linear-gradient({0},  {1} {"...
0x1d2de  ldc.i4.6
0x1d2df  newarr   [mscorlib]System.Object
0x1d2e4  dup
0x1d2e5  ldc.i4.0
0x1d2e6  ldarg.s  5
0x1d2e8  stelem.ref
0x1d2e9  dup
0x1d2ea  ldc.i4.1
0x1d2eb  ldarg.0
0x1d2ec  ldarg.1
0x1d2ed  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGB(valuetype [System.Drawing]System.Drawing.Color color)
0x1d2f2  stelem.ref
0x1d2f3  dup
0x1d2f4  ldc.i4.2
0x1d2f5  ldarg.2
0x1d2f6  stelem.ref
0x1d2f7  dup
0x1d2f8  ldc.i4.3
0x1d2f9  ldarg.0
0x1d2fa  ldarg.3
0x1d2fb  ldc.r8   0.0
0x1d304  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssRGBA(valuetype [System.Drawing]System.Drawing.Color color, float64 Opacity)
0x1d309  stelem.ref
0x1d30a  dup
0x1d30b  ldc.i4.4
0x1d30c  ldarg.s  4
0x1d30e  stelem.ref
0x1d30f  dup
0x1d310  ldc.i4.5
0x1d311  ldloc.1
0x1d312  stelem.ref
0x1d313  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d318  pop
0x1d319  ldloc.0
0x1d31a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d31f  ldstr    aFilterProgidDx_1// "filter: progid:DXImageTransform.Microso"...
0x1d324  ldc.i4.4
0x1d325  newarr   [mscorlib]System.Object
0x1d32a  dup
0x1d32b  ldc.i4.0
0x1d32c  ldarg.0
0x1d32d  ldarg.1
0x1d32e  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssColor(valuetype [System.Drawing]System.Drawing.Color color)
0x1d333  stelem.ref
0x1d334  dup
0x1d335  ldc.i4.1
0x1d336  ldarg.0
0x1d337  ldarg.3
0x1d338  call     instance string Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConvertToCssColor(valuetype [System.Drawing]System.Drawing.Color color)
0x1d33d  stelem.ref
0x1d33e  dup
0x1d33f  ldc.i4.2
0x1d340  ldc.i4.1
0x1d341  box      [mscorlib]System.Int32
0x1d346  stelem.ref
0x1d347  dup
0x1d348  ldc.i4.3
0x1d349  ldloc.1
0x1d34a  stelem.ref
0x1d34b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d350  pop
0x1d351  ldloc.0
0x1d352  callvirt instance string [mscorlib]System.Object::ToString()
0x1d357  ret
```
