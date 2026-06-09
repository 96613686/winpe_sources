# Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::Create

- ea: `0xbfd0`
- end: `0xc00c`
- name: `Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::Create`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xbe70`
- `0xbfd0`

## string_xrefs

- `0xbfef`: `Create`
- `0xbfd1`: `featureAccessRightMap`
- `0xbfe2`: `FeatureAccessRightMap`
- `0xbff4`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeatureAccessRightMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xbfd0  ldarg.1
0xbfd1  ldstr    aFeatureaccessr// "featureAccessRightMap"
0xbfd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbfdb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xbfe0  stloc.0
0xbfe1  ldloc.0
0xbfe2  ldstr    aFeatureaccessr_0// "FeatureAccessRightMap"
0xbfe7  ldarg.1
0xbfe8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::ToPropertyBag()
0xbfed  ldc.i4.s 0x2F
0xbfef  ldstr    aCreate// "Create"
0xbff4  ldstr    aDA1SSrcCrmlive_13// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xbff9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xbffe  pop
0xbfff  leave.s  loc_C00B
0xc001  ldloc.0
0xc002  brfalse.s loc_C00A
0xc004  ldloc.0
0xc005  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc00a  endfinally
0xc00b  ret
```
