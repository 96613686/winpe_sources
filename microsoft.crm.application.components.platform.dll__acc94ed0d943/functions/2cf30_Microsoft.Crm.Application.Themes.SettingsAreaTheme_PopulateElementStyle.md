# Microsoft.Crm.Application.Themes.SettingsAreaTheme::PopulateElementStyle

- ea: `0x2cf30`
- end: `0x2d0da`
- name: `Microsoft.Crm.Application.Themes.SettingsAreaTheme::PopulateElementStyle`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2cf30`
- `0x2d0f0`
- `0x2d110`
- `0x2d130`
- `0x2d150`
- `0x2d170`
- `0x2d190`
- `0x2d1b0`
- `0x2d1d0`
- `0x2d1f0`
- `0x2d210`
- `0x9ca50`

## string_xrefs

- `0x2d02c`: `AreaDescription`
- `0x2d03e`: `SystemSettingsGlobalLink`
- `0x2d05c`: `NotesUserLink`
- `0x2d06b`: `DynamicsMarketingLink`

## pseudocode

```c

```

## disassembly

```asm
0x2cf30  ldarg.1
0x2cf31  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2cf36  stloc.0
0x2cf37  ldloc.0
0x2cf38  ldc.i4   0x3130D14E
0x2cf3d  bgt.un.s loc_2CF88
0x2cf3f  ldloc.0
0x2cf40  ldc.i4   0x1D4236A0
0x2cf45  bgt.un.s loc_2CF62
0x2cf47  ldloc.0
0x2cf48  ldc.i4   0x117AE6C3
0x2cf4d  beq      loc_2D007
0x2cf52  ldloc.0
0x2cf53  ldc.i4   0x1D4236A0
0x2cf58  beq      loc_2D04C
0x2cf5d  br       loc_2D0C9
0x2cf62  ldloc.0
0x2cf63  ldc.i4   0x2DBEB522
0x2cf68  beq      loc_2D03D
0x2cf6d  ldloc.0
0x2cf6e  ldc.i4   0x2DFE8882
0x2cf73  beq      loc_2D019
0x2cf78  ldloc.0
0x2cf79  ldc.i4   0x3130D14E
0x2cf7e  beq      loc_2D02B
0x2cf83  br       loc_2D0C9
0x2cf88  ldloc.0
0x2cf89  ldc.i4   0x5DDB48F2
0x2cf8e  bgt.un.s loc_2CFA8
0x2cf90  ldloc.0
0x2cf91  ldc.i4   0x47DF3831
0x2cf96  beq      loc_2D05B
0x2cf9b  ldloc.0
0x2cf9c  ldc.i4   0x5DDB48F2
0x2cfa1  beq.s    loc_2CFDD
0x2cfa3  br       loc_2D0C9
0x2cfa8  ldloc.0
0x2cfa9  ldc.i4   0x7776444C
0x2cfae  beq.s    loc_2CFC8
0x2cfb0  ldloc.0
0x2cfb1  ldc.i4   0xBB872909
0x2cfb6  beq      loc_2D06A
0x2cfbb  ldloc.0
0x2cfbc  ldc.i4   0xCBFACA80
0x2cfc1  beq.s    loc_2CFF2
0x2cfc3  br       loc_2D0C9
0x2cfc8  ldarg.1
0x2cfc9  ldstr    aPagecontents// "PageContents"
0x2cfce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cfd3  brtrue   loc_2D079
0x2cfd8  br       loc_2D0C9
0x2cfdd  ldarg.1
0x2cfde  ldstr    aAreatitle// "AreaTitle"
0x2cfe3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cfe8  brtrue   loc_2D081
0x2cfed  br       loc_2D0C9
0x2cff2  ldarg.1
0x2cff3  ldstr    aPagetitle// "PageTitle"
0x2cff8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cffd  brtrue   loc_2D089
0x2d002  br       loc_2D0C9
0x2d007  ldarg.1
0x2d008  ldstr    aSettingspageti// "SettingsPageTitle"
0x2d00d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d012  brtrue.s loc_2D091
0x2d014  br       loc_2D0C9
0x2d019  ldarg.1
0x2d01a  ldstr    aPagesubtitle// "PageSubtitle"
0x2d01f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d024  brtrue.s loc_2D099
0x2d026  br       loc_2D0C9
0x2d02b  ldarg.1
0x2d02c  ldstr    aAreadescriptio// "AreaDescription"
0x2d031  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d036  brtrue.s loc_2D0A1
0x2d038  br       loc_2D0C9
0x2d03d  ldarg.1
0x2d03e  ldstr    aSystemsettings// "SystemSettingsGlobalLink"
0x2d043  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d048  brtrue.s loc_2D0A9
0x2d04a  br.s     loc_2D0C9
0x2d04c  ldarg.1
0x2d04d  ldstr    aCasesettingsse// "CaseSettingsSelectedBackgroundColor"
0x2d052  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d057  brtrue.s loc_2D0B1
0x2d059  br.s     loc_2D0C9
0x2d05b  ldarg.1
0x2d05c  ldstr    aNotesuserlink// "NotesUserLink"
0x2d061  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d066  brtrue.s loc_2D0B9
0x2d068  br.s     loc_2D0C9
0x2d06a  ldarg.1
0x2d06b  ldstr    aDynamicsmarket// "DynamicsMarketingLink"
0x2d070  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d075  brtrue.s loc_2D0C1
0x2d077  br.s     loc_2D0C9
0x2d079  ldarg.0
0x2d07a  ldarg.2
0x2d07b  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_PageContents(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d080  ret
0x2d081  ldarg.0
0x2d082  ldarg.2
0x2d083  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_AreaTitle(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d088  ret
0x2d089  ldarg.0
0x2d08a  ldarg.2
0x2d08b  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_PageTitle(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d090  ret
0x2d091  ldarg.0
0x2d092  ldarg.2
0x2d093  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_SettingsPageTitle(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d098  ret
0x2d099  ldarg.0
0x2d09a  ldarg.2
0x2d09b  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_PageSubtitle(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d0a0  ret
0x2d0a1  ldarg.0
0x2d0a2  ldarg.2
0x2d0a3  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_AreaDescription(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d0a8  ret
0x2d0a9  ldarg.0
0x2d0aa  ldarg.2
0x2d0ab  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_SystemSettingsGlobalLink(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d0b0  ret
0x2d0b1  ldarg.0
0x2d0b2  ldarg.2
0x2d0b3  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_CaseSettingsSelectedBackgroundColor(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d0b8  ret
0x2d0b9  ldarg.0
0x2d0ba  ldarg.2
0x2d0bb  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_NotesUserLink(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d0c0  ret
0x2d0c1  ldarg.0
0x2d0c2  ldarg.2
0x2d0c3  call     instance void Microsoft.Crm.Application.Themes.SettingsAreaTheme::set_DynamicsMarketingLink(class Microsoft.Crm.Application.Themes.ThemeStyle value)
0x2d0c8  ret
0x2d0c9  ldstr    aUnknownSetting// "Unknown settings theme element: "
0x2d0ce  ldarg.1
0x2d0cf  call     string [mscorlib]System.String::Concat(string, string)
0x2d0d4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d0d9  throw
```
