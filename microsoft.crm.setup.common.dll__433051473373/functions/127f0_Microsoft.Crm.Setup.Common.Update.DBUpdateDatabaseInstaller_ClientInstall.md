# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ClientInstall

- ea: `0x127f0`
- end: `0x12841`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ClientInstall`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x12510`

## callees

- `0x12f20`

## string_xrefs

- `0x12825`: `DBUpdate_Client.xml`
- `0x12830`: `DBUpdate_Client.xml`

## pseudocode

```c

```

## disassembly

```asm
0x127f0  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x127f5  ldarg.0
0x127f6  call     instance string Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::GetClientInstallPath()
0x127fb  ldstr    aDatabasefixes// "DatabaseFixes"
0x12800  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x12805  stloc.0
0x12806  dup
0x12807  ldarg.0
0x12808  ldfld    string Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ClientActionsDirectory
0x1280d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x12812  ldloc.0
0x12813  ldarg.0
0x12814  ldfld    string Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ClientActionsDirectory
0x12819  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1281e  ldnull
0x1281f  ldnull
0x12820  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateUtility::CopyDirectory(string, string, string[], string[])
0x12825  ldstr    aDbupdateClient// "DBUpdate_Client.xml"
0x1282a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1282f  ldloc.0
0x12830  ldstr    aDbupdateClient// "DBUpdate_Client.xml"
0x12835  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1283a  ldc.i4.1
0x1283b  call     void [mscorlib]System.IO.File::Copy(string, string, bool)
0x12840  ret
```
