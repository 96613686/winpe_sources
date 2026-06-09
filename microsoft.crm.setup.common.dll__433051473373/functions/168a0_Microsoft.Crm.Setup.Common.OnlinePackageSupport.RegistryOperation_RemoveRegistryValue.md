# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::RemoveRegistryValue

- ea: `0x168a0`
- end: `0x16907`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::RemoveRegistryValue`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x166f0`

## callees

- `0x164e0`
- `0x16510`
- `0x168a0`

## string_xrefs

- `0x168c2`: `Removing registry value HKLM:\{0}:{1} -- Current value: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x168a0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x168a5  ldarg.0
0x168a6  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x168ab  ldc.i4.1
0x168ac  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x168b1  stloc.0
0x168b2  ldloc.0
0x168b3  ldarg.0
0x168b4  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x168b9  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x168be  stloc.1
0x168bf  ldloc.1
0x168c0  brfalse.s loc_168FA
0x168c2  ldstr    aRemovingRegist// "Removing registry value HKLM:\\{0}:{1} "...
0x168c7  ldc.i4.3
0x168c8  newarr   [mscorlib]System.Object
0x168cd  dup
0x168ce  ldc.i4.0
0x168cf  ldarg.0
0x168d0  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x168d5  stelem.ref
0x168d6  dup
0x168d7  ldc.i4.1
0x168d8  ldarg.0
0x168d9  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x168de  stelem.ref
0x168df  dup
0x168e0  ldc.i4.2
0x168e1  ldloc.1
0x168e2  callvirt instance string [mscorlib]System.Object::ToString()
0x168e7  stelem.ref
0x168e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x168ed  ldloc.0
0x168ee  ldarg.0
0x168ef  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x168f4  ldc.i4.0
0x168f5  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string, bool)
0x168fa  leave.s  loc_16906
0x168fc  ldloc.0
0x168fd  brfalse.s loc_16905
0x168ff  ldloc.0
0x16900  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16905  endfinally
0x16906  ret
```
