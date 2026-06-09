# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::SetRegistryValue

- ea: `0x167c0`
- end: `0x16897`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::SetRegistryValue`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x166f0`

## callees

- `0x164e0`
- `0x16510`
- `0x16540`
- `0x167c0`

## string_xrefs

- `0x167e8`: `Creating registry key HKLM:\{0}`
- `0x16811`: `Updating registry value HKLM:\{0}:{1} from {2} to {3}`
- `0x16847`: `Setting registry value HKLM:\{0}:{1} to {2}`

## pseudocode

```c

```

## disassembly

```asm
0x167c0  ldnull
0x167c1  stloc.0
0x167c2  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x167c7  ldarg.0
0x167c8  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x167cd  ldc.i4.1
0x167ce  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x167d3  stloc.0
0x167d4  ldloc.0
0x167d5  brtrue.s loc_16801
0x167d7  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x167dc  ldarg.0
0x167dd  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x167e2  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x167e7  stloc.0
0x167e8  ldstr    aCreatingRegist// "Creating registry key HKLM:\\{0}"
0x167ed  ldc.i4.1
0x167ee  newarr   [mscorlib]System.Object
0x167f3  dup
0x167f4  ldc.i4.0
0x167f5  ldarg.0
0x167f6  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x167fb  stelem.ref
0x167fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x16801  ldloc.0
0x16802  ldarg.0
0x16803  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16808  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1680d  stloc.1
0x1680e  ldloc.1
0x1680f  brfalse.s loc_16847
0x16811  ldstr    aUpdatingRegist// "Updating registry value HKLM:\\{0}:{1} "...
0x16816  ldc.i4.4
0x16817  newarr   [mscorlib]System.Object
0x1681c  dup
0x1681d  ldc.i4.0
0x1681e  ldarg.0
0x1681f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16824  stelem.ref
0x16825  dup
0x16826  ldc.i4.1
0x16827  ldarg.0
0x16828  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x1682d  stelem.ref
0x1682e  dup
0x1682f  ldc.i4.2
0x16830  ldloc.1
0x16831  callvirt instance string [mscorlib]System.Object::ToString()
0x16836  stelem.ref
0x16837  dup
0x16838  ldc.i4.3
0x16839  ldarg.0
0x1683a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Value()
0x1683f  stelem.ref
0x16840  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x16845  br.s     loc_16872
0x16847  ldstr    aSettingRegistr// "Setting registry value HKLM:\\{0}:{1} t"...
0x1684c  ldc.i4.3
0x1684d  newarr   [mscorlib]System.Object
0x16852  dup
0x16853  ldc.i4.0
0x16854  ldarg.0
0x16855  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x1685a  stelem.ref
0x1685b  dup
0x1685c  ldc.i4.1
0x1685d  ldarg.0
0x1685e  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16863  stelem.ref
0x16864  dup
0x16865  ldc.i4.2
0x16866  ldarg.0
0x16867  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Value()
0x1686c  stelem.ref
0x1686d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x16872  ldloc.0
0x16873  ldarg.0
0x16874  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16879  ldarg.0
0x1687a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Value()
0x1687f  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x16884  leave.s  loc_16896
0x16886  ldloc.0
0x16887  brfalse.s loc_16895
0x16889  ldloc.0
0x1688a  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x1688f  ldloc.0
0x16890  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Dispose()
0x16895  endfinally
0x16896  ret
```
