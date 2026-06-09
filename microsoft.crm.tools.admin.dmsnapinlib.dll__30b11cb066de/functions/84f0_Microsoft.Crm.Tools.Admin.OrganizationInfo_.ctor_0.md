# Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor_0

- ea: `0x84f0`
- end: `0x85b7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor_0`
- size: `199`
- prototype: ``
- caller_count: `117`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5e80`
- `0x72c0`
- `0x7320`
- `0x73b0`
- `0x73d0`
- `0x7490`
- `0x74e0`
- `0x7590`
- `0x85c0`
- `0x85e0`
- `0x97d0`
- `0xa840`
- `0xa880`
- `0xad20`
- `0xadf0`
- `0xae30`
- `0xaf90`
- `0xbe80`
- `0xc110`
- `0xc400`
- `0xc4c0`
- `0xc600`
- `0xc6b0`
- `0xc710`
- `0xc7b0`
- `0xc860`
- `0xc8d0`
- `0xc960`
- `0xc9f0`
- `0xcab0`
- `0xcb90`
- `0xcc60`
- `0xcd20`
- `0xcda0`
- `0xce00`
- `0xce70`
- `0xcf20`
- `0xcfc0`
- `0xd010`
- `0xd220`
- `0xdb40`
- `0xdc10`
- `0xdc60`
- `0xdd50`
- `0xdf10`
- `0xe040`
- `0xe110`
- `0xe150`
- `0xe210`
- `0xe250`

## callees

- `0x84f0`
- `0x8610`
- `0x87a0`
- `0x87e0`
- `0x8820`
- `0x8870`

## string_xrefs

- `0x84f8`: `InstallInfo.InstallType`

## pseudocode

```c

```

## disassembly

```asm
0x84f0  ldarg.0
0x84f1  ldarg.1
0x84f2  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::.ctor(class [mscorlib]System.Collections.IDictionary)
0x84f7  ldarg.1
0x84f8  ldstr    aInstallinfoIns// "InstallInfo.InstallType"
0x84fd  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8502  brtrue.s loc_8510
0x8504  ldarg.1
0x8505  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x850a  ldc.i4.0
0x850b  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_InstallType(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType)
0x8510  ldarg.0
0x8511  ldc.i4.0
0x8512  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0x8517  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x851c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8521  ldc.i4.2
0x8522  bne.un.s loc_8525
0x8524  ret
0x8525  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x852a  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x852f  newobj   instance void [mscorlib]System.Globalization.RegionInfo::.ctor(string)
0x8534  stloc.0
0x8535  ldarg.0
0x8536  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x853b  ldstr    aOrganizationin_1// "OrganizationInfo.BaseCurrencyName"
0x8540  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8545  brtrue.s loc_8553
0x8547  ldarg.0
0x8548  ldloc.0
0x8549  callvirt instance string [mscorlib]System.Globalization.RegionInfo::get_CurrencyNativeName()
0x854e  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_BaseCurrencyName(string value)
0x8553  ldarg.0
0x8554  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8559  ldstr    aOrganizationin_2// "OrganizationInfo.BaseCurrencyCode"
0x855e  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8563  brtrue.s loc_8571
0x8565  ldarg.0
0x8566  ldloc.0
0x8567  callvirt instance string [mscorlib]System.Globalization.RegionInfo::get_ISOCurrencySymbol()
0x856c  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_BaseCurrencyCode(string value)
0x8571  ldarg.0
0x8572  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8577  ldstr    aOrganizationin_3// "OrganizationInfo.BaseCurrencySymbol"
0x857c  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8581  brtrue.s loc_858F
0x8583  ldarg.0
0x8584  ldloc.0
0x8585  callvirt instance string [mscorlib]System.Globalization.RegionInfo::get_CurrencySymbol()
0x858a  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_BaseCurrencySymbol(string value)
0x858f  ldarg.0
0x8590  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8595  ldstr    aOrganizationin_4// "OrganizationInfo.BaseCurrencyPrecision"
0x859a  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x859f  brtrue.s loc_85B6
0x85a1  ldarg.0
0x85a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x85a7  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x85ac  callvirt instance int32 [mscorlib]System.Globalization.NumberFormatInfo::get_CurrencyDecimalDigits()
0x85b1  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_BaseCurrencyPrecision(int32 value)
0x85b6  ret
```
