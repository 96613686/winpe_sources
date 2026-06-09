# Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::TryFindConnectionStringFromRegistry

- ea: `0xe30`
- end: `0xe67`
- name: `Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::TryFindConnectionStringFromRegistry`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0xe30`

## string_xrefs

- `0xe45`: `configdb`

## pseudocode

```c

```

## disassembly

```asm
0xe30  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xe35  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM"
0xe3a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xe3f  stloc.0
0xe40  ldloc.0
0xe41  brfalse.s loc_E5A
0xe43  ldarg.0
0xe44  ldloc.0
0xe45  ldstr    aConfigdb// "configdb"
0xe4a  ldnull
0xe4b  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0xe50  isinst   [mscorlib]System.String
0xe55  stfld    string Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::_connectionString
0xe5a  leave.s  loc_E66
0xe5c  ldloc.0
0xe5d  brfalse.s loc_E65
0xe5f  ldloc.0
0xe60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe65  endfinally
0xe66  ret
```
