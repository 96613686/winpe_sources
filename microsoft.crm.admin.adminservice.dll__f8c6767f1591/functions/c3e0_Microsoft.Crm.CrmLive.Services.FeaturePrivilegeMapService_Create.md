# Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::Create

- ea: `0xc3e0`
- end: `0xc41c`
- name: `Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMapService::Create`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xc280`
- `0xc3e0`

## string_xrefs

- `0xc3ff`: `Create`
- `0xc3e1`: `featurePrivilegeMap`
- `0xc3f2`: `FeaturePrivilegeMap`
- `0xc404`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeaturePrivilegeMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc3e0  ldarg.1
0xc3e1  ldstr    aFeatureprivile// "featurePrivilegeMap"
0xc3e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xc3eb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc3f0  stloc.0
0xc3f1  ldloc.0
0xc3f2  ldstr    aFeatureprivile_0// "FeaturePrivilegeMap"
0xc3f7  ldarg.1
0xc3f8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::ToPropertyBag()
0xc3fd  ldc.i4.s 0x2F
0xc3ff  ldstr    aCreate// "Create"
0xc404  ldstr    aDA1SSrcCrmlive_14// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc409  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc40e  pop
0xc40f  leave.s  loc_C41B
0xc411  ldloc.0
0xc412  brfalse.s loc_C41A
0xc414  ldloc.0
0xc415  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc41a  endfinally
0xc41b  ret
```
