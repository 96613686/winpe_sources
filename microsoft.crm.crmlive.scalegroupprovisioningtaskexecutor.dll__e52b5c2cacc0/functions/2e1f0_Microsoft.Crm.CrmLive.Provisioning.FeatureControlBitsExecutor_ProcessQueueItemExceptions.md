# Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::ProcessQueueItemExceptions

- ea: `0x2e1f0`
- end: `0x2e337`
- name: `Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::ProcessQueueItemExceptions`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2e070`

## callees

- `0x2e1f0`

## string_xrefs

- `0x2e299`: `CrmScaleGroupProvisioningService`
- `0x2e20c`: `task.QueueItem`
- `0x2e229`: `Queue Item retry due to Update failures for the following Organizations: {0}`
- `0x2e304`: `Queue Item Failure due to Update failures for the following Organizations: {0} . See Event Log for more details.`

## pseudocode

```c

```

## disassembly

```asm
0x2e1f0  ldarg.1
0x2e1f1  ldstr    aTask// "task"
0x2e1f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e1fb  ldarg.3
0x2e1fc  ldstr    aAggregatedexce// "aggregatedExceptions"
0x2e201  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e206  ldarg.1
0x2e207  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e20c  ldstr    aTaskQueueitem// "task.QueueItem"
0x2e211  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e216  ldarg.2
0x2e217  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x2e21c  ldarg.0
0x2e21d  ldfld    int32 Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::_maxRetryCount
0x2e222  bge.s    loc_2E280
0x2e224  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e229  ldstr    aQueueItemRetry// "Queue Item retry due to Update failures"...
0x2e22e  ldc.i4.1
0x2e22f  newarr   [mscorlib]System.Object
0x2e234  dup
0x2e235  ldc.i4.0
0x2e236  ldstr    asc_3F5CC// ", "
0x2e23b  ldarg.3
0x2e23c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::get_Keys()
0x2e241  call     T0x2B0000DF
0x2e246  call     T0x2B0000E0
0x2e24b  stelem.ref
0x2e24c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e251  ldc.r8   30.0
0x2e25a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x2e25f  stloc.0
0x2e260  ldnull
0x2e261  ldarg.1
0x2e262  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e267  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x2e26c  ldloca.s 0
0x2e26e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2e273  conv.i4
0x2e274  ldarg.0
0x2e275  ldfld    int32 Microsoft.Crm.CrmLive.Provisioning.FeatureControlBitsExecutor::_maxRetryCount
0x2e27a  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32, int32, int32)
0x2e27f  ret
0x2e280  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x2e285  stloc.2
0x2e286  ldarg.3
0x2e287  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::GetEnumerator()
0x2e28c  stloc.3
0x2e28d  br.s     loc_2E2DC
0x2e28f  ldloca.s 3
0x2e291  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::get_Current()
0x2e296  stloc.s  4
0x2e298  ldloc.2
0x2e299  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x2e29e  ldc.i4.1
0x2e29f  ldc.i4   0xC0006100
0x2e2a4  conv.u8
0x2e2a5  ldc.i4.3
0x2e2a6  newarr   [mscorlib]System.Object
0x2e2ab  dup
0x2e2ac  ldc.i4.0
0x2e2ad  ldloca.s 4
0x2e2af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::get_Key()
0x2e2b4  box      [mscorlib]System.Guid
0x2e2b9  stelem.ref
0x2e2ba  dup
0x2e2bb  ldc.i4.1
0x2e2bc  ldarg.1
0x2e2bd  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2e2c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2e2c7  box      [mscorlib]System.Guid
0x2e2cc  stelem.ref
0x2e2cd  dup
0x2e2ce  ldc.i4.2
0x2e2cf  ldloca.s 4
0x2e2d1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::get_Value()
0x2e2d6  stelem.ref
0x2e2d7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x2e2dc  ldloca.s 3
0x2e2de  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::MoveNext()
0x2e2e3  brtrue.s loc_2E28F
0x2e2e5  leave.s  loc_2E2FF
0x2e2e7  ldloca.s 3
0x2e2e9  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>
0x2e2ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e2f4  endfinally
0x2e2f5  ldloc.2
0x2e2f6  brfalse.s loc_2E2FE
0x2e2f8  ldloc.2
0x2e2f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e2fe  endfinally
0x2e2ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e304  ldstr    aQueueItemFailu// "Queue Item Failure due to Update failur"...
0x2e309  ldc.i4.1
0x2e30a  newarr   [mscorlib]System.Object
0x2e30f  dup
0x2e310  ldc.i4.0
0x2e311  ldstr    asc_3F5CC// ", "
0x2e316  ldarg.3
0x2e317  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception>::get_Keys()
0x2e31c  call     T0x2B0000DF
0x2e321  call     T0x2B0000E0
0x2e326  stelem.ref
0x2e327  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e32c  stloc.1
0x2e32d  ldc.i4.s 0xB
0x2e32f  ldloc.1
0x2e330  ldnull
0x2e331  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception)
0x2e336  ret
```
