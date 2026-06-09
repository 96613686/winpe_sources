# Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::WriteCaseForByPassObject

- ea: `0x1d710`
- end: `0x1d921`
- name: `Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::WriteCaseForByPassObject`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d5c0`

## callees

- `0x1d710`

## pseudocode

```c

```

## disassembly

```asm
0x1d710  ldarg.1
0x1d711  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d716  ldstr    aCase0_1// "case {0}:"
0x1d71b  ldc.i4.1
0x1d71c  newarr   [mscorlib]System.Object
0x1d721  dup
0x1d722  ldc.i4.0
0x1d723  ldc.i4   0x11FE
0x1d728  box      [mscorlib]System.Int32
0x1d72d  stelem.ref
0x1d72e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d733  pop
0x1d734  ldarg.1
0x1d735  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d73a  ldstr    aCase0_1// "case {0}:"
0x1d73f  ldc.i4.1
0x1d740  newarr   [mscorlib]System.Object
0x1d745  dup
0x1d746  ldc.i4.0
0x1d747  ldc.i4   0x11FF
0x1d74c  box      [mscorlib]System.Int32
0x1d751  stelem.ref
0x1d752  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d757  pop
0x1d758  ldarg.1
0x1d759  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d75e  ldstr    aCase0_1// "case {0}:"
0x1d763  ldc.i4.1
0x1d764  newarr   [mscorlib]System.Object
0x1d769  dup
0x1d76a  ldc.i4.0
0x1d76b  ldc.i4   0x1200
0x1d770  box      [mscorlib]System.Int32
0x1d775  stelem.ref
0x1d776  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d77b  pop
0x1d77c  ldarg.1
0x1d77d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d782  ldstr    aCase0_1// "case {0}:"
0x1d787  ldc.i4.1
0x1d788  newarr   [mscorlib]System.Object
0x1d78d  dup
0x1d78e  ldc.i4.0
0x1d78f  ldc.i4   0x1207
0x1d794  box      [mscorlib]System.Int32
0x1d799  stelem.ref
0x1d79a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d79f  pop
0x1d7a0  ldarg.1
0x1d7a1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d7a6  ldstr    aCase0_1// "case {0}:"
0x1d7ab  ldc.i4.1
0x1d7ac  newarr   [mscorlib]System.Object
0x1d7b1  dup
0x1d7b2  ldc.i4.0
0x1d7b3  ldc.i4   0x1208
0x1d7b8  box      [mscorlib]System.Int32
0x1d7bd  stelem.ref
0x1d7be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d7c3  pop
0x1d7c4  ldarg.1
0x1d7c5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d7ca  ldstr    aCase0_1// "case {0}:"
0x1d7cf  ldc.i4.1
0x1d7d0  newarr   [mscorlib]System.Object
0x1d7d5  dup
0x1d7d6  ldc.i4.0
0x1d7d7  ldc.i4   0x120A
0x1d7dc  box      [mscorlib]System.Int32
0x1d7e1  stelem.ref
0x1d7e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d7e7  pop
0x1d7e8  ldarg.1
0x1d7e9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d7ee  ldstr    aCase0_1// "case {0}:"
0x1d7f3  ldc.i4.1
0x1d7f4  newarr   [mscorlib]System.Object
0x1d7f9  dup
0x1d7fa  ldc.i4.0
0x1d7fb  ldc.i4   0x11FD
0x1d800  box      [mscorlib]System.Int32
0x1d805  stelem.ref
0x1d806  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d80b  pop
0x1d80c  ldarg.1
0x1d80d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d812  ldstr    aCase0_1// "case {0}:"
0x1d817  ldc.i4.1
0x1d818  newarr   [mscorlib]System.Object
0x1d81d  dup
0x1d81e  ldc.i4.0
0x1d81f  ldc.i4.s 0x4E
0x1d821  box      [mscorlib]System.Int32
0x1d826  stelem.ref
0x1d827  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d82c  pop
0x1d82d  ldarg.1
0x1d82e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d833  ldstr    aCase0_1// "case {0}:"
0x1d838  ldc.i4.1
0x1d839  newarr   [mscorlib]System.Object
0x1d83e  dup
0x1d83f  ldc.i4.0
0x1d840  ldc.i4   0x11FA
0x1d845  box      [mscorlib]System.Int32
0x1d84a  stelem.ref
0x1d84b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d850  pop
0x1d851  ldarg.1
0x1d852  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d857  ldstr    aCase0ReturnNul// "case {0}:return null;"
0x1d85c  ldc.i4.1
0x1d85d  newarr   [mscorlib]System.Object
0x1d862  dup
0x1d863  ldc.i4.0
0x1d864  ldc.i4   0x11FB
0x1d869  box      [mscorlib]System.Int32
0x1d86e  stelem.ref
0x1d86f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d874  pop
0x1d875  ldarg.1
0x1d876  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d87b  ldstr    aCase0ReturnNul// "case {0}:return null;"
0x1d880  ldc.i4.1
0x1d881  newarr   [mscorlib]System.Object
0x1d886  dup
0x1d887  ldc.i4.0
0x1d888  ldc.i4   0x1F40
0x1d88d  box      [mscorlib]System.Int32
0x1d892  stelem.ref
0x1d893  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d898  pop
0x1d899  ldarg.1
0x1d89a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d89f  ldstr    aCase0ReturnNul// "case {0}:return null;"
0x1d8a4  ldc.i4.1
0x1d8a5  newarr   [mscorlib]System.Object
0x1d8aa  dup
0x1d8ab  ldc.i4.0
0x1d8ac  ldc.i4   0x1162
0x1d8b1  box      [mscorlib]System.Int32
0x1d8b6  stelem.ref
0x1d8b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d8bc  pop
0x1d8bd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1d8c2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1d8c7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x1d8cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d8d1  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d8d6  brfalse.s loc_1D920
0x1d8d8  ldarg.1
0x1d8d9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d8de  ldstr    aCase0ReturnNul// "case {0}:return null;"
0x1d8e3  ldc.i4.1
0x1d8e4  newarr   [mscorlib]System.Object
0x1d8e9  dup
0x1d8ea  ldc.i4.0
0x1d8eb  ldc.i4   0x2619
0x1d8f0  box      [mscorlib]System.Int32
0x1d8f5  stelem.ref
0x1d8f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d8fb  pop
0x1d8fc  ldarg.1
0x1d8fd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1d902  ldstr    aCase0ReturnNul// "case {0}:return null;"
0x1d907  ldc.i4.1
0x1d908  newarr   [mscorlib]System.Object
0x1d90d  dup
0x1d90e  ldc.i4.0
0x1d90f  ldc.i4   0x261B
0x1d914  box      [mscorlib]System.Int32
0x1d919  stelem.ref
0x1d91a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1d91f  pop
0x1d920  ret
```
