# Microsoft.Crm.ServerLocatorService::SaveFederationProviderSettings

- ea: `0xc360`
- end: `0xc3e3`
- name: `Microsoft.Crm.ServerLocatorService::SaveFederationProviderSettings`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x92c0`
- `0xc360`
- `0x4d7e0`
- `0x64b30`
- `0x64b60`

## string_xrefs

- `0xc38a`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xc3ad`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xc3cb`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc360  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc365  stloc.0
0xc366  ldarg.0
0xc367  ldstr    aFederationprov// "FederationProvider"
0xc36c  ldarg.1
0xc36d  box      [mscorlib]System.Guid
0xc372  ldc.i4.1
0xc373  newarr   [mscorlib]System.String
0xc378  dup
0xc379  ldc.i4.0
0xc37a  ldstr    aId_0// "id"
0xc37f  stelem.ref
0xc380  ldc.i4   0xE2B
0xc385  ldstr    aSavefederation// "SaveFederationProviderSettings"
0xc38a  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc38f  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc394  brfalse.s loc_C3BA
0xc396  ldloc.0
0xc397  ldstr    aFederationprov// "FederationProvider"
0xc39c  ldarg.1
0xc39d  box      [mscorlib]System.Guid
0xc3a2  ldarg.2
0xc3a3  ldc.i4   0xE2F
0xc3a8  ldstr    aSavefederation// "SaveFederationProviderSettings"
0xc3ad  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc3b2  callvirt instance int32 Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc3b7  pop
0xc3b8  leave.s  loc_C3E2
0xc3ba  ldloc.0
0xc3bb  ldstr    aFederationprov// "FederationProvider"
0xc3c0  ldarg.2
0xc3c1  ldc.i4   0xE33
0xc3c6  ldstr    aSavefederation// "SaveFederationProviderSettings"
0xc3cb  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc3d0  callvirt instance object Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc3d5  pop
0xc3d6  leave.s  loc_C3E2
0xc3d8  ldloc.0
0xc3d9  brfalse.s loc_C3E1
0xc3db  ldloc.0
0xc3dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc3e1  endfinally
0xc3e2  ret
```
