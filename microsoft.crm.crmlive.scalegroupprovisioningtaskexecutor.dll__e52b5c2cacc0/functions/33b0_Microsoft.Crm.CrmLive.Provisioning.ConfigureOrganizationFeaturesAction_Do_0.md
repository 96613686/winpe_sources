# Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::Do_0

- ea: `0x33b0`
- end: `0x3461`
- name: `Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::Do_0`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3390`
- `0x24980`

## callees

- `0x33b0`
- `0x3470`
- `0x6520`
- `0x6550`

## string_xrefs

- `0x33b7`: `ConfigureOrganizationFeaturesAction`

## pseudocode

```c

```

## disassembly

```asm
0x33b0  ldarg.0
0x33b1  ldarg.1
0x33b2  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x33b7  ldstr    aConfigureorgan// "ConfigureOrganizationFeaturesAction"
0x33bc  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0x33c1  stloc.0
0x33c2  ldc.i4.6
0x33c3  newarr   [mscorlib]System.Guid
0x33c8  dup
0x33c9  ldc.i4.0
0x33ca  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateEntity
0x33cf  stelem   [mscorlib]System.Guid
0x33d4  dup
0x33d5  ldc.i4.1
0x33d6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateUser
0x33db  stelem   [mscorlib]System.Guid
0x33e0  dup
0x33e1  ldc.i4.2
0x33e2  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::GoOffline
0x33e7  stelem   [mscorlib]System.Guid
0x33ec  dup
0x33ed  ldc.i4.3
0x33ee  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateCustomEntity
0x33f3  stelem   [mscorlib]System.Guid
0x33f8  dup
0x33f9  ldc.i4.4
0x33fa  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::RegisterCustomCode
0x33ff  stelem   [mscorlib]System.Guid
0x3404  dup
0x3405  ldc.i4.5
0x3406  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::ExecuteCustomCode
0x340b  stelem   [mscorlib]System.Guid
0x3410  ldloc.0
0x3411  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationFeatureMapService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext)
0x3416  stloc.1
0x3417  stloc.2
0x3418  ldc.i4.0
0x3419  stloc.3
0x341a  br.s     loc_3447
0x341c  ldloc.2
0x341d  ldloc.3
0x341e  ldelem   [mscorlib]System.Guid
0x3423  stloc.s  4
0x3425  ldarg.1
0x3426  ldloc.s  4
0x3428  call     bool Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::GetOrganizationFeaturePurchaseStatus(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid featureId)
0x342d  brfalse.s loc_343A
0x342f  ldloc.1
0x3430  ldarg.1
0x3431  ldloc.s  4
0x3433  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationFeatureMapService::EnableFeature(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3438  br.s     loc_3443
0x343a  ldloc.1
0x343b  ldarg.1
0x343c  ldloc.s  4
0x343e  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationFeatureMapService::DisableFeature(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3443  ldloc.3
0x3444  ldc.i4.1
0x3445  add
0x3446  stloc.3
0x3447  ldloc.3
0x3448  ldloc.2
0x3449  ldlen
0x344a  conv.i4
0x344b  blt.s    loc_341C
0x344d  leave.s  loc_3459
0x344f  ldloc.0
0x3450  brfalse.s loc_3458
0x3452  ldloc.0
0x3453  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3458  endfinally
0x3459  ldarg.0
0x345a  ldarg.1
0x345b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x3460  ret
```
