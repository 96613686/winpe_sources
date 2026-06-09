# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::CreateRegistryKey

- ea: `0x16910`
- end: `0x16967`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::CreateRegistryKey`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x166f0`

## callees

- `0x164e0`
- `0x16910`

## string_xrefs

- `0x16924`: `Creating registry subkey HKLM:\{0}`

## pseudocode

```c

```

## disassembly

```asm
0x16910  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x16915  ldarg.0
0x16916  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x1691b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x16920  stloc.0
0x16921  ldloc.0
0x16922  brtrue.s loc_1695A
0x16924  ldstr    aCreatingRegist_0// "Creating registry subkey HKLM:\\{0}"
0x16929  ldc.i4.1
0x1692a  newarr   [mscorlib]System.Object
0x1692f  dup
0x16930  ldc.i4.0
0x16931  ldarg.0
0x16932  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16937  stelem.ref
0x16938  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1693d  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x16942  ldarg.0
0x16943  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16948  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1694d  stloc.1
0x1694e  leave.s  loc_16966
0x16950  ldloc.1
0x16951  brfalse.s loc_16959
0x16953  ldloc.1
0x16954  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16959  endfinally
0x1695a  leave.s  loc_16966
0x1695c  ldloc.0
0x1695d  brfalse.s loc_16965
0x1695f  ldloc.0
0x16960  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16965  endfinally
0x16966  ret
```
