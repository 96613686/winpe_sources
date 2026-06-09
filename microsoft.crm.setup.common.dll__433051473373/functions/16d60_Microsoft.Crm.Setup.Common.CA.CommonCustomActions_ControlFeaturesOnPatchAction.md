# Microsoft.Crm.Setup.Common.CA.CommonCustomActions::ControlFeaturesOnPatchAction

- ea: `0x16d60`
- end: `0x16ed8`
- name: `Microsoft.Crm.Setup.Common.CA.CommonCustomActions::ControlFeaturesOnPatchAction`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x16d60`
- `0x16fa0`
- `0x170e0`
- `0x170f0`

## string_xrefs

- `0x16dbe`: `Patch action has requested repair of the Feature(s):  {0}`
- `0x16e08`: `FeaturesToInstallWithPatch`
- `0x16e81`: `Feature {0} is listed for installation.`

## pseudocode

```c

```

## disassembly

```asm
0x16d60  ldc.i4.0
0x16d61  stloc.0
0x16d62  ldarg.0
0x16d63  ldstr    aPatchApplicati// "Patch application or removal:  checking"...
0x16d68  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message)
0x16d6d  ldarg.0
0x16d6e  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_Property()
0x16d73  ldstr    aAddlocal// "ADDLOCAL"
0x16d78  callvirt instance string [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties::get_Item(string)
0x16d7d  stloc.1
0x16d7e  ldloc.1
0x16d7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16d84  brfalse.s loc_16D96
0x16d86  ldarg.0
0x16d87  ldstr    aPatchActionIsN// "Patch action is not adding any features"
0x16d8c  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message)
0x16d91  br       loc_16EAF
0x16d96  ldarg.0
0x16d97  ldstr    aPatchActionHas// "Patch action has requested addition of "...
0x16d9c  ldc.i4.1
0x16d9d  newarr   [mscorlib]System.String
0x16da2  dup
0x16da3  ldc.i4.0
0x16da4  ldloc.1
0x16da5  stelem.ref
0x16da6  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x16dab  ldloc.1
0x16dac  ldc.i4.1
0x16dad  newarr   [mscorlib]System.Char
0x16db2  dup
0x16db3  ldc.i4.0
0x16db4  ldc.i4.s 0x2C
0x16db6  stelem.i2
0x16db7  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16dbc  stloc.2
0x16dbd  ldarg.0
0x16dbe  ldstr    aPatchActionHas_0// "Patch action has requested repair of th"...
0x16dc3  ldc.i4.1
0x16dc4  newarr   [mscorlib]System.String
0x16dc9  dup
0x16dca  ldc.i4.0
0x16dcb  ldarg.0
0x16dcc  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_Property()
0x16dd1  ldstr    aFeaturestounad// "FEATURESTOUNADVERTISE"
0x16dd6  callvirt instance string [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties::get_Item(string)
0x16ddb  stelem.ref
0x16ddc  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x16de1  ldarg.0
0x16de2  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_Property()
0x16de7  ldstr    aFeaturestounad// "FEATURESTOUNADVERTISE"
0x16dec  callvirt instance string [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties::get_Item(string)
0x16df1  ldc.i4.1
0x16df2  newarr   [mscorlib]System.Char
0x16df7  dup
0x16df8  ldc.i4.0
0x16df9  ldc.i4.s 0x2C
0x16dfb  stelem.i2
0x16dfc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16e01  stloc.3
0x16e02  ldarg.0
0x16e03  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_Property()
0x16e08  ldstr    aFeaturestoinst// "FeaturesToInstallWithPatch"
0x16e0d  callvirt instance string [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties::get_Item(string)
0x16e12  ldarg.0
0x16e13  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_Property()
0x16e18  ldstr    aFeaturesaddedw// "FEATURESADDEDWITHPATCH"
0x16e1d  callvirt instance string [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionProperties::get_Item(string)
0x16e22  stloc.s  4
0x16e24  ldc.i4.1
0x16e25  newarr   [mscorlib]System.Char
0x16e2a  dup
0x16e2b  ldc.i4.0
0x16e2c  ldc.i4.s 0x2C
0x16e2e  stelem.i2
0x16e2f  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16e34  ldloc.s  4
0x16e36  ldc.i4.1
0x16e37  newarr   [mscorlib]System.Char
0x16e3c  dup
0x16e3d  ldc.i4.0
0x16e3e  ldc.i4.s 0x2C
0x16e40  stelem.i2
0x16e41  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16e46  call     T0x2B000022
0x16e4b  call     T0x2B000023
0x16e50  stloc.s  5
0x16e52  ldloc.2
0x16e53  stloc.s  6
0x16e55  ldc.i4.0
0x16e56  stloc.s  7
0x16e58  br.s     loc_16EA7
0x16e5a  ldloc.s  6
0x16e5c  ldloc.s  7
0x16e5e  ldelem.ref
0x16e5f  stloc.s  8
0x16e61  ldloc.s  5
0x16e63  ldloc.s  8
0x16e65  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x16e6a  call     T0x2B000020
0x16e6f  brtrue.s loc_16E80
0x16e71  ldloc.3
0x16e72  ldloc.s  8
0x16e74  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x16e79  call     T0x2B000020
0x16e7e  brfalse.s loc_16E98
0x16e80  ldarg.0
0x16e81  ldstr    aFeature0IsList// "Feature {0} is listed for installation."
0x16e86  ldc.i4.1
0x16e87  newarr   [mscorlib]System.String
0x16e8c  dup
0x16e8d  ldc.i4.0
0x16e8e  ldloc.s  8
0x16e90  stelem.ref
0x16e91  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x16e96  br.s     loc_16EA1
0x16e98  ldarg.0
0x16e99  ldloc.s  8
0x16e9b  ldc.i4.2
0x16e9c  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::SetFeatureState(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string featureName, valuetype [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.InstallState requestedFeatureState)
0x16ea1  ldloc.s  7
0x16ea3  ldc.i4.1
0x16ea4  add
0x16ea5  stloc.s  7
0x16ea7  ldloc.s  7
0x16ea9  ldloc.s  6
0x16eab  ldlen
0x16eac  conv.i4
0x16ead  blt.s    loc_16E5A
0x16eaf  leave.s  loc_16ED6
0x16eb1  stloc.s  9
0x16eb3  ldarg.0
0x16eb4  ldstr    aErrorOccurredI// "Error occurred in ControlFeaturesOnPatc"...
0x16eb9  ldc.i4.1
0x16eba  newarr   [mscorlib]System.String
0x16ebf  dup
0x16ec0  ldc.i4.0
0x16ec1  ldloc.s  9
0x16ec3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16ec8  stelem.ref
0x16ec9  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x16ece  ldc.i4   0x643
0x16ed3  stloc.0
0x16ed4  leave.s  loc_16ED6
0x16ed6  ldloc.0
0x16ed7  ret
```
