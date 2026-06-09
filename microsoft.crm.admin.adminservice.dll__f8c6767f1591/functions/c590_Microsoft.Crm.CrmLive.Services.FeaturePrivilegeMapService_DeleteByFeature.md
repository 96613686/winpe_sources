# Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::DeleteByFeature

- ea: `0xc590`
- end: `0xc5e7`
- name: `Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::DeleteByFeature`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xc800`

## callees

- `0xc590`

## string_xrefs

- `0xc5ca`: `DeleteByFeature`
- `0xc5b9`: `FeaturePrivilegeMap`
- `0xc5cf`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeaturePrivilegeMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc590  ldarg.1
0xc591  ldstr    aFeatureid_0// "featureId"
0xc596  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xc59b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc5a0  stloc.0
0xc5a1  ldloc.0
0xc5a2  ldstr    aFeatureid// "FeatureId"
0xc5a7  ldarg.1
0xc5a8  box      [mscorlib]System.Guid
0xc5ad  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc5b2  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc5b7  stloc.1
0xc5b8  ldloc.1
0xc5b9  ldstr    aFeatureprivile_0// "FeaturePrivilegeMap"
0xc5be  ldc.i4.1
0xc5bf  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xc5c4  dup
0xc5c5  ldc.i4.0
0xc5c6  ldloc.0
0xc5c7  stelem.ref
0xc5c8  ldc.i4.s 0x7B
0xc5ca  ldstr    aDeletebyfeatur// "DeleteByFeature"
0xc5cf  ldstr    aDA1SSrcCrmlive_14// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc5d4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xc5d9  pop
0xc5da  leave.s  loc_C5E6
0xc5dc  ldloc.1
0xc5dd  brfalse.s loc_C5E5
0xc5df  ldloc.1
0xc5e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc5e5  endfinally
0xc5e6  ret
```
