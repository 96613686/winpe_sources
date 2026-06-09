# Microsoft.Crm.Setup.Common.CA.DismWrapper::EnableFeature

- ea: `0x171b0`
- end: `0x1720c`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::EnableFeature`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17e00`

## callees

- `0x171b0`
- `0x17300`
- `0x17580`
- `0x176c0`
- `0x17990`

## string_xrefs

- `0x171cb`: `/online /english /enable-feature /norestart /all /featurename:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x171b0  ldarg.0
0x171b1  call     instance string Microsoft.Crm.Setup.Common.CA.DismWrapper::get_GetExePath()
0x171b6  ldnull
0x171b7  stloc.0
0x171b8  ldnull
0x171b9  stloc.1
0x171ba  ldarg.0
0x171bb  ldfld    string Microsoft.Crm.Setup.Common.CA.DismWrapper::_fileName
0x171c0  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x171c5  stloc.2
0x171c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x171cb  ldstr    aOnlineEnglishE// "/online /english /enable-feature /nores"...
0x171d0  ldc.i4.1
0x171d1  newarr   [mscorlib]System.Object
0x171d6  dup
0x171d7  ldc.i4.0
0x171d8  ldarg.1
0x171d9  stelem.ref
0x171da  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x171df  stloc.3
0x171e0  ldloc.2
0x171e1  ldloc.3
0x171e2  ldloca.s 0
0x171e4  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RunProcess(string, string, string&)
0x171e9  stloc.s  4
0x171eb  ldarg.0
0x171ec  ldloc.0
0x171ed  ldloc.s  4
0x171ef  call     instance valuetype Microsoft.Crm.Setup.Common.CA.DismCode Microsoft.Crm.Setup.Common.CA.DismWrapper::DismResults(string output, int32 exitCode)
0x171f4  ldarg.0
0x171f5  ldarg.1
0x171f6  call     instance class Microsoft.Crm.Setup.Common.CA.IFeatureInfo Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal(string featureName)
0x171fb  stloc.1
0x171fc  ldc.i4   0xBC2
0x17201  bne.un.s loc_1720A
0x17203  ldloc.1
0x17204  ldc.i4.2
0x17205  callvirt instance void Microsoft.Crm.Setup.Common.CA.IFeatureInfo::set_RestartRequired(valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureRestartType value)
0x1720a  ldloc.1
0x1720b  ret
```
