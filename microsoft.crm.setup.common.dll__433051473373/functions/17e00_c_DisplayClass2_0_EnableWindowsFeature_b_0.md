# <>c__DisplayClass2_0::<EnableWindowsFeature>b__0

- ea: `0x17e00`
- end: `0x17f2b`
- name: `<>c__DisplayClass2_0::<EnableWindowsFeature>b__0`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x16f50`
- `0x170f0`
- `0x17120`
- `0x171b0`
- `0x172c0`
- `0x17980`
- `0x179a0`
- `0x17e00`

## string_xrefs

- `0x17ed9`: `{0} Requires a Restart to complete.`

## pseudocode

```c

```

## disassembly

```asm
0x17e00  newobj   instance void Microsoft.Crm.Setup.Common.CA.DismWrapper::.ctor()
0x17e05  stloc.0
0x17e06  ldloc.0
0x17e07  ldarg.0
0x17e08  ldfld    string <>c__DisplayClass2_0::feature
0x17e0d  callvirt instance class Microsoft.Crm.Setup.Common.CA.IFeatureInfo Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfo(string featureName)
0x17e12  stloc.1
0x17e13  ldloc.1
0x17e14  brfalse  loc_17EF2
0x17e19  ldarg.0
0x17e1a  ldfld    class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session <>c__DisplayClass2_0::session
0x17e1f  ldstr    a0IsAnAvailable// "{0} is an available feature on this Ope"...
0x17e24  ldc.i4.1
0x17e25  newarr   [mscorlib]System.String
0x17e2a  dup
0x17e2b  ldc.i4.0
0x17e2c  ldarg.0
0x17e2d  ldfld    string <>c__DisplayClass2_0::feature
0x17e32  stelem.ref
0x17e33  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17e38  ldloc.1
0x17e39  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_FeatureState()
0x17e3e  ldc.i4.4
0x17e3f  beq      loc_17EF2
0x17e44  ldarg.0
0x17e45  ldfld    class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session <>c__DisplayClass2_0::session
0x17e4a  ldstr    aEnabling0// "Enabling {0}."
0x17e4f  ldc.i4.1
0x17e50  newarr   [mscorlib]System.String
0x17e55  dup
0x17e56  ldc.i4.0
0x17e57  ldarg.0
0x17e58  ldfld    string <>c__DisplayClass2_0::feature
0x17e5d  stelem.ref
0x17e5e  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17e63  ldloc.0
0x17e64  ldarg.0
0x17e65  ldfld    string <>c__DisplayClass2_0::feature
0x17e6a  callvirt instance class Microsoft.Crm.Setup.Common.CA.IFeatureInfo Microsoft.Crm.Setup.Common.CA.DismWrapper::EnableFeature(string featureName)
0x17e6f  stloc.2
0x17e70  ldloc.2
0x17e71  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_FeatureState()
0x17e76  ldc.i4.4
0x17e77  bne.un.s loc_17EAB
0x17e79  ldloc.2
0x17e7a  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureRestartType Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_RestartRequired()
0x17e7f  brfalse.s loc_17E8A
0x17e81  ldloc.2
0x17e82  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureRestartType Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_RestartRequired()
0x17e87  ldc.i4.1
0x17e88  bne.un.s loc_17EAB
0x17e8a  ldarg.0
0x17e8b  ldfld    class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session <>c__DisplayClass2_0::session
0x17e90  ldstr    a0Enabled// "{0} Enabled."
0x17e95  ldc.i4.1
0x17e96  newarr   [mscorlib]System.String
0x17e9b  dup
0x17e9c  ldc.i4.0
0x17e9d  ldarg.0
0x17e9e  ldfld    string <>c__DisplayClass2_0::feature
0x17ea3  stelem.ref
0x17ea4  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17ea9  br.s     loc_17EF2
0x17eab  ldloc.2
0x17eac  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_FeatureState()
0x17eb1  ldc.i4.2
0x17eb2  beq.s    loc_17EC6
0x17eb4  ldloc.2
0x17eb5  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_FeatureState()
0x17eba  ldc.i4.3
0x17ebb  beq.s    loc_17EC6
0x17ebd  ldloc.2
0x17ebe  callvirt instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState Microsoft.Crm.Setup.Common.CA.IFeatureInfo::get_FeatureState()
0x17ec3  ldc.i4.1
0x17ec4  bne.un.s loc_17ED3
0x17ec6  ldarg.0
0x17ec7  ldfld    string <>c__DisplayClass2_0::disabledRegKeyName
0x17ecc  call     void Microsoft.Crm.Setup.Common.CA.CommonCustomActions::SetDisabledRegKey(string name)
0x17ed1  br.s     loc_17EF2
0x17ed3  ldarg.0
0x17ed4  ldfld    class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session <>c__DisplayClass2_0::session
0x17ed9  ldstr    a0RequiresARest// "{0} Requires a Restart to complete."
0x17ede  ldc.i4.1
0x17edf  newarr   [mscorlib]System.String
0x17ee4  dup
0x17ee5  ldc.i4.0
0x17ee6  ldarg.0
0x17ee7  ldfld    string <>c__DisplayClass2_0::feature
0x17eec  stelem.ref
0x17eed  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17ef2  leave.s  loc_17F2A
0x17ef4  stloc.3
0x17ef5  ldarg.0
0x17ef6  ldfld    string <>c__DisplayClass2_0::disabledRegKeyName
0x17efb  call     void Microsoft.Crm.Setup.Common.CA.CommonCustomActions::SetDisabledRegKey(string name)
0x17f00  ldarg.0
0x17f01  ldfld    class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session <>c__DisplayClass2_0::session
0x17f06  ldstr    aErrorOccurredI_0// "Error occurred in EnableWindowsFeature "...
0x17f0b  ldc.i4.2
0x17f0c  newarr   [mscorlib]System.String
0x17f11  dup
0x17f12  ldc.i4.0
0x17f13  ldarg.0
0x17f14  ldfld    string <>c__DisplayClass2_0::feature
0x17f19  stelem.ref
0x17f1a  dup
0x17f1b  ldc.i4.1
0x17f1c  ldloc.3
0x17f1d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x17f22  stelem.ref
0x17f23  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17f28  leave.s  loc_17F2A
0x17f2a  ret
```
