# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::RemoveRegistryKey

- ea: `0x16970`
- end: `0x1699b`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::RemoveRegistryKey`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x166f0`

## callees

- `0x164e0`

## string_xrefs

- `0x16970`: `Removing registry subkey HKLM:\{0}`

## pseudocode

```c

```

## disassembly

```asm
0x16970  ldstr    aRemovingRegist_0// "Removing registry subkey HKLM:\\{0}"
0x16975  ldc.i4.1
0x16976  newarr   [mscorlib]System.Object
0x1697b  dup
0x1697c  ldc.i4.0
0x1697d  ldarg.0
0x1697e  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16983  stelem.ref
0x16984  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x16989  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1698e  ldarg.0
0x1698f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16994  ldc.i4.0
0x16995  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string, bool)
0x1699a  ret
```
