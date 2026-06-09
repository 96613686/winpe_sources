# Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::Update

- ea: `0xc0e0`
- end: `0xc134`
- name: `Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::Update`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xbdf0`
- `0xbe70`
- `0xc0e0`

## string_xrefs

- `0xc117`: `Update`
- `0xc0e1`: `featureAccessRightMap`
- `0xc104`: `FeatureAccessRightMap`
- `0xc11c`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeatureAccessRightMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc0e0  ldarg.1
0xc0e1  ldstr    aFeatureaccessr// "featureAccessRightMap"
0xc0e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xc0eb  ldarg.1
0xc0ec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::ToPropertyBag()
0xc0f1  stloc.0
0xc0f2  ldloc.0
0xc0f3  ldstr    aId// "Id"
0xc0f8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Remove(string)
0xc0fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xc102  stloc.1
0xc103  ldloc.1
0xc104  ldstr    aFeatureaccessr_0// "FeatureAccessRightMap"
0xc109  ldarg.1
0xc10a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::get_Id()
0xc10f  box      [mscorlib]System.Guid
0xc114  ldloc.0
0xc115  ldc.i4.s 0x5E
0xc117  ldstr    aUpdate// "Update"
0xc11c  ldstr    aDA1SSrcCrmlive_13// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc121  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc126  pop
0xc127  leave.s  loc_C133
0xc129  ldloc.1
0xc12a  brfalse.s loc_C132
0xc12c  ldloc.1
0xc12d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc132  endfinally
0xc133  ret
```
