# Microsoft.Crm.ServerLocatorService::UpdateSiteSetting

- ea: `0x72b0`
- end: `0x72ea`
- name: `Microsoft.Crm.ServerLocatorService::UpdateSiteSetting`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x8190`

## callees

- `0x72b0`
- `0xb8a0`
- `0x4d750`
- `0x62440`

## string_xrefs

- `0x72d2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x72cd`: `UpdateSiteSetting`

## pseudocode

```c

```

## disassembly

```asm
0x72b0  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x72b5  stloc.0
0x72b6  ldloc.0
0x72b7  ldstr    aServersettings// "ServerSettings"
0x72bc  ldarg.0
0x72bd  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServerLocatorService::GetSiteSettingId()
0x72c2  box      [mscorlib]System.Guid
0x72c7  ldarg.1
0x72c8  ldc.i4   0x1E3
0x72cd  ldstr    aUpdatesitesett// "UpdateSiteSetting"
0x72d2  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x72d7  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x72dc  pop
0x72dd  leave.s  loc_72E9
0x72df  ldloc.0
0x72e0  brfalse.s loc_72E8
0x72e2  ldloc.0
0x72e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72e8  endfinally
0x72e9  ret
```
