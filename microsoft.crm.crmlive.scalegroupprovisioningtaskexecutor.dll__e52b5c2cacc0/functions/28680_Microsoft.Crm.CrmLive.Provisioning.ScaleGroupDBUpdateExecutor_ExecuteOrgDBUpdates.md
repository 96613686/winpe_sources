# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::ExecuteOrgDBUpdates

- ea: `0x28680`
- end: `0x288dc`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::ExecuteOrgDBUpdates`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x28560`

## callees

- `0x28680`
- `0x288e0`

## string_xrefs

- `0x287fe`: `Unable to create DBUpdate queue item for organization:{0}. Exception:{1}`
- `0x28834`: `ScaleGroupDBUpdateExecutor`
- `0x28839`: `ApplyDBUpdates`
- `0x288ba`: `Waiting for successfully created OrganizationDBUpdate queueItems.`
- `0x288d1`: `Unexpected stage in ScaleGroupDBUpdateExecutor!`

## pseudocode

```c

```

## disassembly

```asm
0x28680  ldnull
0x28681  stloc.0
0x28682  ldarg.0
0x28683  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x28688  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2868d  brtrue.s loc_2869D
0x2868f  ldarg.0
0x28690  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x28695  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::Deserialize(string)
0x2869a  stloc.0
0x2869b  br.s     loc_286AA
0x2869d  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::.ctor()
0x286a2  stloc.0
0x286a3  ldloc.0
0x286a4  ldc.i4.0
0x286a5  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::set_Stage(int32)
0x286aa  ldloc.0
0x286ab  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::get_Stage()
0x286b0  stloc.1
0x286b1  ldloc.1
0x286b2  brfalse.s loc_286C0
0x286b4  ldloc.1
0x286b5  ldc.i4.5
0x286b6  beq      loc_288C5
0x286bb  br       loc_288D1
0x286c0  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext::.ctor()
0x286c5  stloc.2
0x286c6  ldloc.2
0x286c7  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x286cc  stloc.3
0x286cd  ldloca.s 4
0x286cf  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>
0x286d5  ldarg.1
0x286d6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_OrgStateFilter()
0x286db  brfalse.s loc_28715
0x286dd  ldarg.1
0x286de  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_OrgStateFilter()
0x286e3  ldstr    aEnabled_0// "enabled"
0x286e8  ldc.i4.5
0x286e9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x286ee  brtrue.s loc_286FA
0x286f0  ldloca.s 4
0x286f2  ldc.i4.1
0x286f3  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::.ctor(var<u1>)
0x286f8  br.s     loc_28715
0x286fa  ldarg.1
0x286fb  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_OrgStateFilter()
0x28700  ldstr    aDisabled// "disabled"
0x28705  ldc.i4.5
0x28706  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2870b  brtrue.s loc_28715
0x2870d  ldloca.s 4
0x2870f  ldc.i4.0
0x28710  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::.ctor(var<u1>)
0x28715  ldloca.s 5
0x28717  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2871d  ldarg.1
0x2871e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_OrgMinRevisionFilter()
0x28723  brfalse.s loc_2873D
0x28725  ldarg.1
0x28726  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_OrgMinRevisionFilter()
0x2872b  ldloca.s 6
0x2872d  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x28732  brfalse.s loc_2873D
0x28734  ldloca.s 5
0x28736  ldloc.s  6
0x28738  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2873d  ldc.i4.3
0x2873e  newarr   [mscorlib]System.String
0x28743  dup
0x28744  ldc.i4.0
0x28745  ldstr    aId// "Id"
0x2874a  stelem.ref
0x2874b  dup
0x2874c  ldc.i4.1
0x2874d  ldstr    aState// "State"
0x28752  stelem.ref
0x28753  dup
0x28754  ldc.i4.2
0x28755  ldstr    aRevision// "Revision"
0x2875a  stelem.ref
0x2875b  ldarg.1
0x2875c  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_ScaleGroupName()
0x28761  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x28766  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x2876b  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext::.ctor()
0x28770  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveListOfOrgs(string[], string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x28775  stloc.s  7
0x28777  ldc.i4.0
0x28778  stloc.s  8
0x2877a  br       loc_28873
0x2877f  ldloc.s  7
0x28781  ldloc.s  8
0x28783  ldelem.ref
0x28784  stloc.s  9
0x28786  ldloca.s 5
0x28788  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x2878d  brfalse.s loc_287B2
0x2878f  ldloc.s  9
0x28791  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Revision()
0x28796  ldloc.s  5
0x28798  stloc.s  0xA
0x2879a  ldloca.s 0xA
0x2879c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x287a1  bge.s    loc_287A6
0x287a3  ldc.i4.0
0x287a4  br.s     loc_287AD
0x287a6  ldloca.s 0xA
0x287a8  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x287ad  brfalse  loc_2886D
0x287b2  ldloca.s 4
0x287b4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_HasValue()
0x287b9  brfalse.s loc_287DE
0x287bb  ldloc.s  9
0x287bd  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_State()
0x287c2  ldloc.s  4
0x287c4  stloc.s  0xB
0x287c6  ldloca.s 0xB
0x287c8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::GetValueOrDefault()
0x287cd  beq.s    loc_287D2
0x287cf  ldc.i4.0
0x287d0  br.s     loc_287D9
0x287d2  ldloca.s 0xB
0x287d4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_HasValue()
0x287d9  brfalse  loc_2886D
0x287de  nop
0x287df  ldloc.3
0x287e0  ldloc.s  9
0x287e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x287e7  ldc.i4.1
0x287e8  ldarg.1
0x287e9  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_Uninstall()
0x287ee  ldarg.0
0x287ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::ApplyDBUpdates(valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x287f4  pop
0x287f5  leave.s  loc_2886D
0x287f7  stloc.s  0xC
0x287f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x287fe  ldstr    aUnableToCreate_0// "Unable to create DBUpdate queue item fo"...
0x28803  ldc.i4.2
0x28804  newarr   [mscorlib]System.Object
0x28809  dup
0x2880a  ldc.i4.0
0x2880b  ldloc.s  9
0x2880d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x28812  box      [mscorlib]System.Guid
0x28817  stelem.ref
0x28818  dup
0x28819  ldc.i4.1
0x2881a  ldloc.s  0xC
0x2881c  callvirt instance string [mscorlib]System.Object::ToString()
0x28821  stelem.ref
0x28822  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28827  stloc.s  0xD
0x28829  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x2882e  ldarg.0
0x2882f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x28834  ldstr    aScalegroupdbup// "ScaleGroupDBUpdateExecutor"
0x28839  ldstr    aApplydbupdates// "ApplyDBUpdates"
0x2883e  ldloc.s  0xD
0x28840  ldc.i4.0
0x28841  ldloc.s  9
0x28843  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x28848  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x2884d  ldloc.s  9
0x2884f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x28854  ldc.i4.s 0xA
0x28856  ldstr    a0// "{0}"
0x2885b  ldc.i4.1
0x2885c  newarr   [mscorlib]System.Object
0x28861  dup
0x28862  ldc.i4.0
0x28863  ldloc.s  0xD
0x28865  stelem.ref
0x28866  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2886b  leave.s  loc_2886D
0x2886d  ldloc.s  8
0x2886f  ldc.i4.1
0x28870  add
0x28871  stloc.s  8
0x28873  ldloc.s  8
0x28875  ldloc.s  7
0x28877  ldlen
0x28878  conv.i4
0x28879  blt      loc_2877F
0x2887e  leave.s  loc_2888A
0x28880  ldloc.2
0x28881  brfalse.s loc_28889
0x28883  ldloc.2
0x28884  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28889  endfinally
0x2888a  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::.ctor()
0x2888f  ldloc.0
0x28890  ldc.i4.5
0x28891  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::set_Stage(int32)
0x28896  ldloc.0
0x28897  ldstr    aWaiting// "Waiting"
0x2889c  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::set_StageDescription(string)
0x288a1  ldarg.0
0x288a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x288a7  ldloc.0
0x288a8  call     string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::Serialize(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData)
0x288ad  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x288b2  ldnull
0x288b3  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItem(valuetype [mscorlib]System.Guid, string, object, string)
0x288b8  ldc.i4.s 0xC
0x288ba  ldstr    aWaitingForSucc// "Waiting for successfully created Organi"...
0x288bf  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x288c4  ret
0x288c5  ldarg.0
0x288c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x288cb  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::WaitForChildren(valuetype [mscorlib]System.Guid queueItemId)
0x288d0  ret
0x288d1  ldstr    aUnexpectedStag// "Unexpected stage in ScaleGroupDBUpdateE"...
0x288d6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x288db  throw
```
