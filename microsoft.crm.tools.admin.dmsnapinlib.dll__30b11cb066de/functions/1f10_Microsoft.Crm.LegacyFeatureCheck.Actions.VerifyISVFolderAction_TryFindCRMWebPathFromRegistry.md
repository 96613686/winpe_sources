# Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyISVFolderAction::TryFindCRMWebPathFromRegistry

- ea: `0x1f10`
- end: `0x1f45`
- name: `Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyISVFolderAction::TryFindCRMWebPathFromRegistry`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1e90`

## callees

- `0x1f10`

## string_xrefs

- `0x1f26`: `WebSitePath`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldnull
0x1f11  stloc.0
0x1f12  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1f17  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM"
0x1f1c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1f21  stloc.1
0x1f22  ldloc.1
0x1f23  brfalse.s loc_1F37
0x1f25  ldloc.1
0x1f26  ldstr    aWebsitepath// "WebSitePath"
0x1f2b  ldnull
0x1f2c  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x1f31  isinst   [mscorlib]System.String
0x1f36  stloc.0
0x1f37  leave.s  loc_1F43
0x1f39  ldloc.1
0x1f3a  brfalse.s loc_1F42
0x1f3c  ldloc.1
0x1f3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f42  endfinally
0x1f43  ldloc.0
0x1f44  ret
```
