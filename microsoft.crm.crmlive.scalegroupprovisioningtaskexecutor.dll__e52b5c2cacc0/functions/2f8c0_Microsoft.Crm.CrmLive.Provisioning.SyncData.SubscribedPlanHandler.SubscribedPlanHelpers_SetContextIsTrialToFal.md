# Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::SetContextIsTrialToFalse

- ea: `0x2f8c0`
- end: `0x2f9b3`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::SetContextIsTrialToFalse`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xf540`

## callees

- `0x2f8c0`
- `0x2f9c0`
- `0x2fa20`
- `0x2fa50`

## string_xrefs

- `0x2f8f0`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SubscribedPlanHandler\SubscribedPlanHelpers.cs`
- `0x2f94a`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SubscribedPlanHandler\SubscribedPlanHelpers.cs`
- `0x2f98a`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SubscribedPlanHandler\SubscribedPlanHelpers.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2f8c0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2f8c5  stloc.0
0x2f8c6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2f8cb  stloc.1
0x2f8cc  ldloc.0
0x2f8cd  ldstr    aContext_0// "Context"
0x2f8d2  ldarg.0
0x2f8d3  box      [mscorlib]System.Guid
0x2f8d8  ldc.i4.1
0x2f8d9  newarr   [mscorlib]System.String
0x2f8de  dup
0x2f8df  ldc.i4.0
0x2f8e0  ldstr    aIstrial// "IsTrial"
0x2f8e5  stelem.ref
0x2f8e6  ldc.i4   0xCD
0x2f8eb  ldstr    aSetcontextistr// "SetContextIsTrialToFalse"
0x2f8f0  ldstr    aDDbsShDccm2110_45// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2f8f5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x2f8fa  stloc.2
0x2f8fb  ldloc.2
0x2f8fc  brfalse.s loc_2F957
0x2f8fe  ldloc.2
0x2f8ff  ldstr    aIstrial// "IsTrial"
0x2f904  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2f909  brfalse.s loc_2F922
0x2f90b  ldloc.2
0x2f90c  ldstr    aIstrial// "IsTrial"
0x2f911  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2f916  unbox.any [mscorlib]System.Boolean
0x2f91b  brtrue.s loc_2F922
0x2f91d  leave    loc_2F9B2
0x2f922  ldloc.1
0x2f923  ldstr    aIstrial// "IsTrial"
0x2f928  ldc.i4.0
0x2f929  box      [mscorlib]System.Boolean
0x2f92e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2f933  ldloc.0
0x2f934  ldstr    aContext_0// "Context"
0x2f939  ldarg.0
0x2f93a  box      [mscorlib]System.Guid
0x2f93f  ldloc.1
0x2f940  ldc.i4   0xD7
0x2f945  ldstr    aSetcontextistr// "SetContextIsTrialToFalse"
0x2f94a  ldstr    aDDbsShDccm2110_45// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2f94f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2f954  pop
0x2f955  leave.s  loc_2F9A1
0x2f957  ldloc.1
0x2f958  ldstr    aContextid// "ContextId"
0x2f95d  ldarg.0
0x2f95e  box      [mscorlib]System.Guid
0x2f963  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2f968  ldloc.1
0x2f969  ldstr    aIstrial// "IsTrial"
0x2f96e  ldc.i4.0
0x2f96f  box      [mscorlib]System.Boolean
0x2f974  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2f979  ldloc.0
0x2f97a  ldstr    aContext_0// "Context"
0x2f97f  ldloc.1
0x2f980  ldc.i4   0xDD
0x2f985  ldstr    aSetcontextistr// "SetContextIsTrialToFalse"
0x2f98a  ldstr    aDDbsShDccm2110_45// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2f98f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2f994  pop
0x2f995  leave.s  loc_2F9A1
0x2f997  ldloc.0
0x2f998  brfalse.s loc_2F9A0
0x2f99a  ldloc.0
0x2f99b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f9a0  endfinally
0x2f9a1  call     class Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.IFlushOrgSettingUtil Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.FlushOrgSettingUtil::NewService()
0x2f9a6  ldarg.1
0x2f9a7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.IFlushOrgSettingUtil::FlushOrganizationSettings(valuetype [mscorlib]System.Guid orgId)
0x2f9ac  ldarg.1
0x2f9ad  call     void Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::CreateDeleteInitialSolutionQueueItem(valuetype [mscorlib]System.Guid orgId)
0x2f9b2  ret
```
