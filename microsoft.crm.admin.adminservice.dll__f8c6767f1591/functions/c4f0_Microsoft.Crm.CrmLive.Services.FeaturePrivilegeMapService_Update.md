# Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::Update

- ea: `0xc4f0`
- end: `0xc544`
- name: `Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::Update`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0xc200`
- `0xc280`
- `0xc4f0`

## string_xrefs

- `0xc527`: `Update`
- `0xc4f1`: `featurePrivilegeMap`
- `0xc514`: `FeaturePrivilegeMap`
- `0xc52c`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeaturePrivilegeMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc4f0  ldarg.1
0xc4f1  ldstr    aFeatureprivile// "featurePrivilegeMap"
0xc4f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xc4fb  ldarg.1
0xc4fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::ToPropertyBag()
0xc501  stloc.0
0xc502  ldloc.0
0xc503  ldstr    aId// "Id"
0xc508  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Remove(string)
0xc50d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xc512  stloc.1
0xc513  ldloc.1
0xc514  ldstr    aFeatureprivile_0// "FeaturePrivilegeMap"
0xc519  ldarg.1
0xc51a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::get_Id()
0xc51f  box      [mscorlib]System.Guid
0xc524  ldloc.0
0xc525  ldc.i4.s 0x5E
0xc527  ldstr    aUpdate// "Update"
0xc52c  ldstr    aDA1SSrcCrmlive_14// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc531  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc536  pop
0xc537  leave.s  loc_C543
0xc539  ldloc.1
0xc53a  brfalse.s loc_C542
0xc53c  ldloc.1
0xc53d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc542  endfinally
0xc543  ret
```
