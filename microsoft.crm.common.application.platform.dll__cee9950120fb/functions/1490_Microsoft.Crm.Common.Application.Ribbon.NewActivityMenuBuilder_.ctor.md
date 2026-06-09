# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::.ctor

- ea: `0x1490`
- end: `0x14f0`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::.ctor`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x45e0`

## callees

- `0x1490`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldarg.0
0x1491  ldstr    aMnuNewActivity// "mnu_new_activity"
0x1496  stfld    string Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_outlook14GlobalToolbarMenuId
0x149b  ldarg.0
0x149c  ldstr    aMnuNewActivity// "mnu_new_activity"
0x14a1  stfld    string Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_outlookLegacyOfficeMenubarId
0x14a6  ldarg.0
0x14a7  ldarg.1
0x14a8  ldarg.2
0x14a9  ldarg.3
0x14aa  ldarg.s  4
0x14ac  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::.ctor(string, string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14b1  ldarg.s  4
0x14b3  isinst   [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx
0x14b8  stloc.0
0x14b9  ldarg.0
0x14ba  ldarg.s  6
0x14bc  stfld    bool Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_replaceLocalStrings
0x14c1  ldarg.s  5
0x14c3  ldc.i4.0
0x14c4  ble.s    loc_14D4
0x14c6  ldarg.0
0x14c7  ldarg.s  5
0x14c9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::GetCultureInfo(int32)
0x14ce  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x14d3  ret
0x14d4  ldloc.0
0x14d5  brfalse.s loc_14E4
0x14d7  ldarg.0
0x14d8  ldloc.0
0x14d9  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserUICulture()
0x14de  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x14e3  ret
0x14e4  ldarg.0
0x14e5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x14ea  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_resourceCulture
0x14ef  ret
```
