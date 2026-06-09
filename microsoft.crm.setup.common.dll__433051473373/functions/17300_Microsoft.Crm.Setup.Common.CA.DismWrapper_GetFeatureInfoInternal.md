# Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal

- ea: `0x17300`
- end: `0x1735c`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x171b0`
- `0x172c0`

## callees

- `0x17300`
- `0x17440`
- `0x17580`
- `0x176c0`

## string_xrefs

- `0x17308`: `featureName`
- `0x1732c`: `/online /english /get-featureinfo /featurename:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x17300  ldarg.1
0x17301  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17306  brfalse.s loc_17313
0x17308  ldstr    aFeaturename// "featureName"
0x1730d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17312  throw
0x17313  ldnull
0x17314  stloc.0
0x17315  ldarg.0
0x17316  call     instance string Microsoft.Crm.Setup.Common.CA.DismWrapper::get_GetExePath()
0x1731b  ldarg.0
0x1731c  ldfld    string Microsoft.Crm.Setup.Common.CA.DismWrapper::_fileName
0x17321  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x17326  stloc.1
0x17327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1732c  ldstr    aOnlineEnglishG_0// "/online /english /get-featureinfo /feat"...
0x17331  ldc.i4.1
0x17332  newarr   [mscorlib]System.Object
0x17337  dup
0x17338  ldc.i4.0
0x17339  ldarg.1
0x1733a  stelem.ref
0x1733b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17340  stloc.2
0x17341  ldloc.1
0x17342  ldloc.2
0x17343  ldloca.s 0
0x17345  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RunProcess(string, string, string&)
0x1734a  stloc.3
0x1734b  ldarg.0
0x1734c  ldloc.0
0x1734d  ldloc.3
0x1734e  call     instance valuetype Microsoft.Crm.Setup.Common.CA.DismCode Microsoft.Crm.Setup.Common.CA.DismWrapper::DismResults(string output, int32 exitCode)
0x17353  pop
0x17354  ldarg.0
0x17355  ldloc.0
0x17356  call     instance class Microsoft.Crm.Setup.Common.CA.IFeatureInfo Microsoft.Crm.Setup.Common.CA.DismWrapper::MapOutputToFeatureDetail(string data)
0x1735b  ret
```
