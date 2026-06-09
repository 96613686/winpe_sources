# Microsoft.Crm.CrmLive.Provisioning.FlushCacheExecutor::Execute

- ea: `0x26110`
- end: `0x26264`
- name: `Microsoft.Crm.CrmLive.Provisioning.FlushCacheExecutor::Execute`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x26110`

## string_xrefs

- `0x2612e`: `metadatacache`
- `0x261bb`: `This API currently does not support flush for cache {0}. `
- `0x261eb`: `FlushCache failed for organization : {0}, cache: {1}, QueueItemId:{2} exception: {3}.`
- `0x26234`: `FlushCache succeeded for organization : {0}, cache: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x26110  ldarg.1
0x26111  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x26116  stloc.0
0x26117  ldloc.0
0x26118  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2611d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x26122  stloc.1
0x26123  ldloc.0
0x26124  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x26129  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2612e  ldstr    aMetadatacache// "metadatacache"
0x26133  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26138  brfalse.s loc_26146
0x2613a  ldloc.1
0x2613b  ldc.i4.1
0x2613c  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, bool)
0x26141  br       loc_261E0
0x26146  ldtoken  [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DebugService/CacheName
0x2614b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26150  ldloc.0
0x26151  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x26156  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x2615b  brfalse.s loc_261B4
0x2615d  ldloc.0
0x2615e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x26163  ldc.i4.0
0x26164  ldc.i4.0
0x26165  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x2616a  stloc.2
0x2616b  ldloc.2
0x2616c  ldc.i4.1
0x2616d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x26172  ldloc.2
0x26173  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x26178  stloc.3
0x26179  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DebugService::.ctor()
0x2617e  ldloc.0
0x2617f  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x26184  ldloc.2
0x26185  ldc.i4.1
0x26186  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DebugService::FlushCache(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x2618b  leave.s  loc_26197
0x2618d  ldloc.3
0x2618e  brfalse.s loc_26196
0x26190  ldloc.3
0x26191  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26196  endfinally
0x26197  ldloc.2
0x26198  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x2619d  leave.s  loc_261A8
0x2619f  pop
0x261a0  ldloc.2
0x261a1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x261a6  rethrow
0x261a8  leave.s  loc_261E0
0x261aa  ldloc.2
0x261ab  brfalse.s loc_261B3
0x261ad  ldloc.2
0x261ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x261b3  endfinally
0x261b4  ldc.i4.s 0xB
0x261b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x261bb  ldstr    aThisApiCurrent// "This API currently does not support flu"...
0x261c0  ldc.i4.1
0x261c1  newarr   [mscorlib]System.Object
0x261c6  dup
0x261c7  ldc.i4.0
0x261c8  ldloc.0
0x261c9  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x261ce  stelem.ref
0x261cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x261d4  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x261d9  stloc.s  4
0x261db  leave    loc_26261
0x261e0  leave.s  loc_2622E
0x261e2  stloc.s  5
0x261e4  ldc.i4.s 0xB
0x261e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x261eb  ldstr    aFlushcacheFail// "FlushCache failed for organization : {0"...
0x261f0  ldc.i4.4
0x261f1  newarr   [mscorlib]System.Object
0x261f6  dup
0x261f7  ldc.i4.0
0x261f8  ldloc.0
0x261f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x261fe  box      [mscorlib]System.Guid
0x26203  stelem.ref
0x26204  dup
0x26205  ldc.i4.1
0x26206  ldloc.0
0x26207  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2620c  stelem.ref
0x2620d  dup
0x2620e  ldc.i4.2
0x2620f  ldloc.0
0x26210  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x26215  box      [mscorlib]System.Guid
0x2621a  stelem.ref
0x2621b  dup
0x2621c  ldc.i4.3
0x2621d  ldloc.s  5
0x2621f  stelem.ref
0x26220  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26225  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2622a  stloc.s  4
0x2622c  leave.s  loc_26261
0x2622e  ldc.i4.4
0x2622f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26234  ldstr    aFlushcacheSucc// "FlushCache succeeded for organization :"...
0x26239  ldc.i4.2
0x2623a  newarr   [mscorlib]System.Object
0x2623f  dup
0x26240  ldc.i4.0
0x26241  ldloc.0
0x26242  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x26247  box      [mscorlib]System.Guid
0x2624c  stelem.ref
0x2624d  dup
0x2624e  ldc.i4.1
0x2624f  ldloc.0
0x26250  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x26255  stelem.ref
0x26256  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2625b  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x26260  ret
0x26261  ldloc.s  4
0x26263  ret
```
