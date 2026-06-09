# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyConfigDBUpdates_0

- ea: `0x12e00`
- end: `0x12e15`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyConfigDBUpdates_0`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x12dc0`

## string_xrefs

- `0x12e01`: `releaseFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x12e00  ldarg.1
0x12e01  ldstr    aReleasefilepat// "releaseFilePath"
0x12e06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x12e0b  ldarg.0
0x12e0c  ldarg.1
0x12e0d  ldarg.2
0x12e0e  ldarg.3
0x12e0f  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ConfigInstallerHelper::ApplyConfigDBUpdates(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase, string, string, bool)
0x12e14  ret
```
