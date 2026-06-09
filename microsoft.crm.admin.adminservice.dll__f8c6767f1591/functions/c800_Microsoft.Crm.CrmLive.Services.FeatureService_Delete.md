# Microsoft.Crm.CrmLive.Services.FeatureService::Delete

- ea: `0xc800`
- end: `0xc886`
- name: `Microsoft.Crm.CrmLive.Services.FeatureService::Delete`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0xbfa0`
- `0xc180`
- `0xc3b0`
- `0xc590`
- `0xc610`
- `0xc800`
- `0xcad0`
- `0xcc60`

## string_xrefs

- `0xc86a`: `Delete`
- `0xc86f`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeatureService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc800  ldarg.1
0xc801  ldstr    aFeatureid_0// "featureId"
0xc806  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xc80b  ldarg.0
0xc80c  call     instance class Microsoft.Crm.CrmLive.Services.CrmLiveContext Microsoft.Crm.CrmLive.Services.FeatureService::get_Context()
0xc811  newobj   instance void Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::.ctor(class Microsoft.Crm.CrmLive.Services.CrmLiveContext context)
0xc816  stloc.0
0xc817  ldloc.0
0xc818  ldarg.1
0xc819  callvirt instance void Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::DeleteByFeature(valuetype [mscorlib]System.Guid featureId)
0xc81e  leave.s  loc_C823
0xc820  pop
0xc821  leave.s  loc_C823
0xc823  ldarg.0
0xc824  call     instance class Microsoft.Crm.CrmLive.Services.CrmLiveContext Microsoft.Crm.CrmLive.Services.FeatureService::get_Context()
0xc829  newobj   instance void Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::.ctor(class Microsoft.Crm.CrmLive.Services.CrmLiveContext context)
0xc82e  stloc.1
0xc82f  ldloc.1
0xc830  ldarg.1
0xc831  callvirt instance void Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::DeleteByFeature(valuetype [mscorlib]System.Guid featureId)
0xc836  leave.s  loc_C83B
0xc838  pop
0xc839  leave.s  loc_C83B
0xc83b  ldarg.0
0xc83c  call     instance class Microsoft.Crm.CrmLive.Services.CrmLiveContext Microsoft.Crm.CrmLive.Services.FeatureService::get_Context()
0xc841  newobj   instance void Microsoft.Crm.CrmLive.Services.OrganizationFeatureMapService::.ctor(class Microsoft.Crm.CrmLive.Services.CrmLiveContext context)
0xc846  stloc.2
0xc847  ldloc.2
0xc848  ldarg.1
0xc849  callvirt instance void Microsoft.Crm.CrmLive.Services.OrganizationFeatureMapService::DeleteByFeature(valuetype [mscorlib]System.Guid featureId)
0xc84e  leave.s  loc_C853
0xc850  pop
0xc851  leave.s  loc_C853
0xc853  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc858  stloc.3
0xc859  ldloc.3
0xc85a  ldstr    aFeature_0// "Feature"
0xc85f  ldarg.1
0xc860  box      [mscorlib]System.Guid
0xc865  ldc.i4   0x9F
0xc86a  ldstr    aDelete// "Delete"
0xc86f  ldstr    aDA1SSrcCrmlive_15// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc874  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0xc879  leave.s  loc_C885
0xc87b  ldloc.3
0xc87c  brfalse.s loc_C884
0xc87e  ldloc.3
0xc87f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc884  endfinally
0xc885  ret
```
