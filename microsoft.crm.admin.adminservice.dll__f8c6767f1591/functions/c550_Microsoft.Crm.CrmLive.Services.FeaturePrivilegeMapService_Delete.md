# Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::Delete

- ea: `0xc550`
- end: `0xc58b`
- name: `Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::Delete`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0xc550`

## string_xrefs

- `0xc56f`: `Delete`
- `0xc562`: `FeaturePrivilegeMap`
- `0xc574`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeaturePrivilegeMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc550  ldarg.1
0xc551  ldstr    aId_0// "id"
0xc556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xc55b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc560  stloc.0
0xc561  ldloc.0
0xc562  ldstr    aFeatureprivile_0// "FeaturePrivilegeMap"
0xc567  ldarg.1
0xc568  box      [mscorlib]System.Guid
0xc56d  ldc.i4.s 0x68
0xc56f  ldstr    aDelete// "Delete"
0xc574  ldstr    aDA1SSrcCrmlive_14// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc579  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0xc57e  leave.s  loc_C58A
0xc580  ldloc.0
0xc581  brfalse.s loc_C589
0xc583  ldloc.0
0xc584  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc589  endfinally
0xc58a  ret
```
