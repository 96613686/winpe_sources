# Microsoft.Crm.Asynchronous.JobManager::CreateTimers

- ea: `0x4110`
- end: `0x4222`
- name: `Microsoft.Crm.Asynchronous.JobManager::CreateTimers`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x3f60`
- `0x4110`

## pseudocode

```c

```

## disassembly

```asm
0x4110  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::.ctor()
0x4115  stloc.0
0x4116  ldloc.0
0x4117  ldarg.0
0x4118  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x411d  ldarg.0
0x411e  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4123  ldstr    aCrmOrganizatio// "CRM Organizations db Maintenance"
0x4128  ldarg.0
0x4129  ldftn    instance void Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x412f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x4134  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x4139  ldarg.0
0x413a  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x413f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgDatabaseMaintenanceInterval()
0x4144  stloc.1
0x4145  ldloca.s 1
0x4147  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x414c  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaintenanceIntervalTimerFrequencyMultiplier()
0x4151  conv.r8
0x4152  div
0x4153  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x4158  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x415d  ldloc.0
0x415e  ldarg.0
0x415f  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4164  ldarg.0
0x4165  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x416a  ldstr    aCrmOrganizatio_0// "CRM Organizations db Maintenance timeou"...
0x416f  ldarg.0
0x4170  ldftn    instance void Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_1(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4176  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x417b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x4180  ldarg.0
0x4181  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x4186  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgDatabaseJobTimeoutLockedInterval()
0x418b  stloc.1
0x418c  ldloca.s 1
0x418e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4193  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x4198  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x419d  ldloc.0
0x419e  ldarg.0
0x419f  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x41a4  ldarg.0
0x41a5  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x41aa  ldstr    aCrmOrganizatio_1// "CRM Organizations Maintenance jobs sync"
0x41af  ldarg.0
0x41b0  ldftn    instance void Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_2(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x41b6  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x41bb  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x41c0  ldc.r8   1.44e7
0x41c9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x41ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x41d3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x41d8  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x41dd  ldc.i4.2
0x41de  bne.un.s loc_4220
0x41e0  ldloc.0
0x41e1  ldarg.0
0x41e2  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x41e7  ldarg.0
0x41e8  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x41ed  ldstr    aCrmOrganizatio_2// "CRM Organizations db backup cleanup tim"...
0x41f2  ldarg.0
0x41f3  ldftn    instance void Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_3(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x41f9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x41fe  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x4203  ldarg.0
0x4204  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x4209  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_ScaleGroupDatabaseBackupCleanupInterval()
0x420e  stloc.1
0x420f  ldloca.s 1
0x4211  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4216  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x421b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x4220  ldloc.0
0x4221  ret
```
