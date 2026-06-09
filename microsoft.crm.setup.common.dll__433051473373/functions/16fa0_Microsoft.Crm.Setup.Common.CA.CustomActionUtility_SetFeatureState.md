# Microsoft.Crm.Setup.Common.CA.CustomActionUtility::SetFeatureState

- ea: `0x16fa0`
- end: `0x1707a`
- name: `Microsoft.Crm.Setup.Common.CA.CustomActionUtility::SetFeatureState`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x16d60`

## callees

- `0x16fa0`
- `0x17080`
- `0x170f0`

## string_xrefs

- `0x16fa8`: `Setting install state for {0} feature to {1}.`
- `0x16fea`: `REMOVE`
- `0x17019`: `Error occurred attempting to set feature {0} state to {1}: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x16fa0  ldarg.0
0x16fa1  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionFeatureRequestStates [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_FeatureRequestState()
0x16fa6  stloc.0
0x16fa7  ldarg.0
0x16fa8  ldstr    aSettingInstall// "Setting install state for {0} feature t"...
0x16fad  ldc.i4.2
0x16fae  newarr   [mscorlib]System.String
0x16fb3  dup
0x16fb4  ldc.i4.0
0x16fb5  ldarg.1
0x16fb6  stelem.ref
0x16fb7  dup
0x16fb8  ldc.i4.1
0x16fb9  ldarga.s 2
0x16fbb  constrained. [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.InstallState
0x16fc1  callvirt instance string [mscorlib]System.Object::ToString()
0x16fc6  stelem.ref
0x16fc7  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x16fcc  ldloc.0
0x16fcd  ldarg.1
0x16fce  ldarg.2
0x16fcf  callvirt instance void [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionFeatureRequestStates::set_Item(string, valuetype [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.InstallState)
0x16fd4  ldarg.0
0x16fd5  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionFeatureCurrentStates [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_FeatureCurrentState()
0x16fda  ldarg.1
0x16fdb  callvirt instance valuetype [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.InstallState [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionFeatureCurrentStates::get_Item(string)
0x16fe0  stloc.1
0x16fe1  ldloc.1
0x16fe2  ldc.i4.3
0x16fe3  bne.un.s loc_16FFC
0x16fe5  ldarg.2
0x16fe6  ldc.i4.2
0x16fe7  bne.un.s loc_16FFC
0x16fe9  ldarg.0
0x16fea  ldstr    aRemove// "REMOVE"
0x16fef  ldarg.1
0x16ff0  ldstr    asc_26DBA// ","
0x16ff5  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::AppendToProperty(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string property, string textToAdd, string separator)
0x16ffa  br.s     loc_17015
0x16ffc  ldloc.1
0x16ffd  ldc.i4.2
0x16ffe  bne.un.s loc_17015
0x17000  ldarg.2
0x17001  ldc.i4.3
0x17002  bne.un.s loc_17015
0x17004  ldarg.0
0x17005  ldstr    aAddlocal// "ADDLOCAL"
0x1700a  ldarg.1
0x1700b  ldstr    asc_26DBA// ","
0x17010  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::AppendToProperty(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string property, string textToAdd, string separator)
0x17015  leave.s  loc_17079
0x17017  stloc.2
0x17018  ldarg.0
0x17019  ldstr    aErrorOccurredA// "Error occurred attempting to set featur"...
0x1701e  ldc.i4.3
0x1701f  newarr   [mscorlib]System.String
0x17024  dup
0x17025  ldc.i4.0
0x17026  ldarg.1
0x17027  stelem.ref
0x17028  dup
0x17029  ldc.i4.1
0x1702a  ldarga.s 2
0x1702c  constrained. [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.InstallState
0x17032  callvirt instance string [mscorlib]System.Object::ToString()
0x17037  stelem.ref
0x17038  dup
0x17039  ldc.i4.2
0x1703a  ldloc.2
0x1703b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x17040  stelem.ref
0x17041  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17046  ldarg.0
0x17047  ldstr    aValidfeaturest// "ValidFeatureStates for {0}: {1}"
0x1704c  ldc.i4.2
0x1704d  newarr   [mscorlib]System.String
0x17052  dup
0x17053  ldc.i4.0
0x17054  ldarg.1
0x17055  stelem.ref
0x17056  dup
0x17057  ldc.i4.1
0x17058  ldarg.0
0x17059  callvirt instance class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionFeatureValidStates [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session::get_FeatureValidStates()
0x1705e  ldarg.1
0x1705f  callvirt instance int32 [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.SessionFeatureValidStates::get_Item(string)
0x17064  stloc.3
0x17065  ldloca.s 3
0x17067  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1706c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x17071  stelem.ref
0x17072  call     void Microsoft.Crm.Setup.Common.CA.CustomActionUtility::LogToMsi(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string message, string[] args)
0x17077  rethrow
0x17079  ret
```
