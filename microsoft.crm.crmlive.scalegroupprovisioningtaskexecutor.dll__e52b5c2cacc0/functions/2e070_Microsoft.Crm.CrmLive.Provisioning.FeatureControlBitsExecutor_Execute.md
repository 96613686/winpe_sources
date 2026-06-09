# Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::Execute

- ea: `0x2e070`
- end: `0x2e1e4`
- name: `Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::Execute`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x2e070`
- `0x2e1f0`
- `0x2e340`
- `0x2e380`
- `0x2e530`
- `0x2e690`

## string_xrefs

- `0x2e081`: `task.QueueItem`
- `0x2e096`: `task.QueueItem.ItemData`

## pseudocode

```c

```

## disassembly

```asm
0x2e070  ldarg.1
0x2e071  ldstr    aTask// "task"
0x2e076  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e07b  ldarg.1
0x2e07c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e081  ldstr    aTaskQueueitem// "task.QueueItem"
0x2e086  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e08b  ldarg.1
0x2e08c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e091  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2e096  ldstr    aTaskQueueitemI// "task.QueueItem.ItemData"
0x2e09b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2e0a0  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::.ctor()
0x2e0a5  stloc.0
0x2e0a6  ldloc.0
0x2e0a7  ldc.i4.1
0x2e0a8  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::set_TaskScope(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x2e0ad  ldnull
0x2e0ae  stloc.1
0x2e0af  ldarg.1
0x2e0b0  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e0b5  stloc.2
0x2e0b6  ldnull
0x2e0b7  stloc.3
0x2e0b8  ldnull
0x2e0b9  stloc.s  4
0x2e0bb  ldarg.1
0x2e0bc  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e0c1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x2e0c6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e0cb  brfalse.s loc_2E0EA
0x2e0cd  ldloc.2
0x2e0ce  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2e0d3  call     T0x2B0000DC
0x2e0d8  stloc.3
0x2e0d9  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::.ctor()
0x2e0de  stloc.s  4
0x2e0e0  ldloc.s  4
0x2e0e2  ldc.i4.0
0x2e0e3  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::set_Stage(int32)
0x2e0e8  br.s     loc_2E117
0x2e0ea  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsInfo::.ctor()
0x2e0ef  stloc.3
0x2e0f0  ldarg.1
0x2e0f1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e0f6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x2e0fb  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::Deserialize(string)
0x2e100  stloc.s  4
0x2e102  ldloc.s  4
0x2e104  ldc.i4.1
0x2e105  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::set_Stage(int32)
0x2e10a  ldloc.s  4
0x2e10c  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::get_StageData()
0x2e111  call     T0x2B0000DD
0x2e116  stloc.1
0x2e117  ldloc.3
0x2e118  brfalse.s loc_2E12F
0x2e11a  ldloc.3
0x2e11b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitDetail> [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsInfo::get_Features()
0x2e120  call     T0x2B0000DE
0x2e125  ldc.i4.0
0x2e126  ble.s    loc_2E12F
0x2e128  ldloc.3
0x2e129  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet> Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::BuildFeatureSetData(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsInfo featureControlBits)
0x2e12e  stloc.1
0x2e12f  ldloc.1
0x2e130  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Count()
0x2e135  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::.ctor(int32)
0x2e13a  stloc.s  5
0x2e13c  ldloc.1
0x2e13d  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Count()
0x2e142  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::.ctor(int32)
0x2e147  stloc.s  6
0x2e149  ldloc.1
0x2e14a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::GetEnumerator()
0x2e14f  stloc.s  7
0x2e151  br.s     loc_2E19F
0x2e153  ldloca.s 7
0x2e155  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Current()
0x2e15a  stloc.s  8
0x2e15c  ldloca.s 8
0x2e15e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Key()
0x2e163  ldloca.s 8
0x2e165  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Value()
0x2e16a  call     void Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::UpdateOrganization(valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet features)
0x2e16f  leave.s  loc_2E19F
0x2e171  stloc.s  9
0x2e173  ldloc.s  5
0x2e175  ldloc.s  9
0x2e177  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitExecutorException::get_OrganizationId()
0x2e17c  ldloc.s  9
0x2e17e  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x2e183  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::set_Item(var<u1>, !!T0)
0x2e188  ldloc.s  6
0x2e18a  ldloca.s 8
0x2e18c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Key()
0x2e191  ldloca.s 8
0x2e193  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::get_Value()
0x2e198  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::set_Item(var<u1>, !!T0)
0x2e19d  leave.s  loc_2E19F
0x2e19f  ldloca.s 7
0x2e1a1  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>::MoveNext()
0x2e1a6  brtrue.s loc_2E153
0x2e1a8  leave.s  loc_2E1B8
0x2e1aa  ldloca.s 7
0x2e1ac  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet>
0x2e1b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e1b7  endfinally
0x2e1b8  ldloc.s  5
0x2e1ba  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::get_Count()
0x2e1bf  ldc.i4.0
0x2e1c0  ble.s    loc_2E1D8
0x2e1c2  ldloc.0
0x2e1c3  ldloc.2
0x2e1c4  ldloc.s  4
0x2e1c6  ldloc.s  6
0x2e1c8  call     void Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::UpdateQueueItemRuntimeData(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager queueManager, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData runtimeData, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.FeatureSet> failedOrgFeatureSets)
0x2e1cd  ldarg.0
0x2e1ce  ldarg.1
0x2e1cf  ldloc.2
0x2e1d0  ldloc.s  5
0x2e1d2  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::ProcessQueueItemExceptions(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception> aggregatedExceptions)
0x2e1d7  ret
0x2e1d8  ldc.i4.4
0x2e1d9  ldstr    aSuccess// "success"
0x2e1de  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2e1e3  ret
```
