# Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::DeleteByFeature

- ea: `0xc180`
- end: `0xc1d7`
- name: `Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::DeleteByFeature`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xc800`

## callees

- `0xc180`

## string_xrefs

- `0xc1a9`: `FeatureAccessRightMap`
- `0xc1bf`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeatureAccessRightMapService.cs`
- `0xc1ba`: `DeleteByFeature`

## pseudocode

```c

```

## disassembly

```asm
0xc180  ldarg.1
0xc181  ldstr    aFeatureid_0// "featureId"
0xc186  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xc18b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc190  stloc.0
0xc191  ldloc.0
0xc192  ldstr    aFeatureid// "FeatureId"
0xc197  ldarg.1
0xc198  box      [mscorlib]System.Guid
0xc19d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc1a2  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc1a7  stloc.1
0xc1a8  ldloc.1
0xc1a9  ldstr    aFeatureaccessr_0// "FeatureAccessRightMap"
0xc1ae  ldc.i4.1
0xc1af  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xc1b4  dup
0xc1b5  ldc.i4.0
0xc1b6  ldloc.0
0xc1b7  stelem.ref
0xc1b8  ldc.i4.s 0x7A
0xc1ba  ldstr    aDeletebyfeatur// "DeleteByFeature"
0xc1bf  ldstr    aDA1SSrcCrmlive_13// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc1c4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xc1c9  pop
0xc1ca  leave.s  loc_C1D6
0xc1cc  ldloc.1
0xc1cd  brfalse.s loc_C1D5
0xc1cf  ldloc.1
0xc1d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc1d5  endfinally
0xc1d6  ret
```
