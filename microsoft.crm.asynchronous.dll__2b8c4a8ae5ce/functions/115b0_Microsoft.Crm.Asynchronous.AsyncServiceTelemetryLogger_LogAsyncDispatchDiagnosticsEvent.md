# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncDispatchDiagnosticsEvent

- ea: `0x115b0`
- end: `0x1171a`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncDispatchDiagnosticsEvent`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x6450`
- `0x6470`
- `0x6490`
- `0x64b0`
- `0x64d0`
- `0x64f0`
- `0x6510`
- `0x6530`
- `0x6600`
- `0x6640`
- `0x6660`
- `0x6680`
- `0x66a0`
- `0x66c0`
- `0x66e0`
- `0x6700`
- `0x6720`
- `0x6740`
- `0x115b0`
- `0x14000`
- `0x14730`

## pseudocode

```c

```

## disassembly

```asm
0x115b0  ldarg.1
0x115b1  switch   loc_115C3, loc_11652, loc_116A9
0x115c2  ret
0x115c3  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x115c8  ldarga.s 1
0x115ca  constrained. Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind
0x115d0  callvirt instance string [mscorlib]System.Object::ToString()
0x115d5  ldarg.3
0x115d6  callvirt instance string Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_WorkloadThrottlerName()
0x115db  ldarg.3
0x115dc  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalPriority()
0x115e1  ldarg.3
0x115e2  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalCapacity()
0x115e7  ldarg.3
0x115e8  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalOutstandingOperation()
0x115ed  ldarg.3
0x115ee  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_IsInBacklogControlMode()
0x115f3  ldarg.3
0x115f4  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryLow()
0x115f9  ldarg.3
0x115fa  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryHigh()
0x115ff  ldarg.3
0x11600  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_UseLegacyWorkloadThrottler()
0x11605  ldarg.2
0x11606  ldarg.s  4
0x11608  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_OrganizationId()
0x1160d  ldarg.s  4
0x1160f  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_Priority()
0x11614  ldarg.s  4
0x11616  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_WaitIterations()
0x1161b  ldarg.s  4
0x1161d  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_CurrentThroughputQuotaUsage()
0x11622  ldarg.s  4
0x11624  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_MaxThroughputQuota()
0x11629  ldarg.s  4
0x1162b  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_CurrentOutstandingOperation()
0x11630  ldarg.s  4
0x11632  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_AvailableCapacity()
0x11637  ldarg.s  4
0x11639  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_AllocatedCapacity()
0x1163e  ldarg.s  4
0x11640  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_NewOperationsQueued()
0x11645  ldarg.s  4
0x11647  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_ActualWorkAllocated()
0x1164c  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogAsyncDispatchDiagnosticsEvent(string selectExecutionKind, string workloadThrottlerName, int32 totalPriority, int32 totalCapacity, int32 totalOutstandingOperation, bool isInBacklogControlMode, int32 itemsInMemoryLow, int32 itemsInMemoryHigh, bool useLegacyWorkloadThrottler, int64 selectExecutionTimeInSec, valuetype [mscorlib]System.Guid organizationId, [opt] int32 orgPriority, [opt] int32 orgWaitIterations, [opt] int32 orgCurrentThroughputQuotaUsage, [opt] int32 orgMaxThroughputQuota, [opt] int32 orgCurrentOutstandingOperation, [opt] int32 orgAvailableCapacity, [opt] int32 orgAllocatedCapacity, [opt] int32 newOperationsQueued, [opt] int32 actualWorkAllocated)
0x11651  ret
0x11652  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11657  ldarga.s 1
0x11659  constrained. Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind
0x1165f  callvirt instance string [mscorlib]System.Object::ToString()
0x11664  ldarg.3
0x11665  callvirt instance string Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_WorkloadThrottlerName()
0x1166a  ldarg.3
0x1166b  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalPriority()
0x11670  ldarg.3
0x11671  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalCapacity()
0x11676  ldarg.3
0x11677  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalOutstandingOperation()
0x1167c  ldarg.3
0x1167d  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_IsInBacklogControlMode()
0x11682  ldarg.3
0x11683  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryLow()
0x11688  ldarg.3
0x11689  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryHigh()
0x1168e  ldarg.3
0x1168f  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_UseLegacyWorkloadThrottler()
0x11694  ldarg.2
0x11695  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1169a  ldc.i4.0
0x1169b  ldc.i4.m1
0x1169c  ldc.i4.m1
0x1169d  ldc.i4.m1
0x1169e  ldc.i4.m1
0x1169f  ldc.i4.m1
0x116a0  ldc.i4.m1
0x116a1  ldc.i4.m1
0x116a2  ldc.i4.m1
0x116a3  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogAsyncDispatchDiagnosticsEvent(string selectExecutionKind, string workloadThrottlerName, int32 totalPriority, int32 totalCapacity, int32 totalOutstandingOperation, bool isInBacklogControlMode, int32 itemsInMemoryLow, int32 itemsInMemoryHigh, bool useLegacyWorkloadThrottler, int64 selectExecutionTimeInSec, valuetype [mscorlib]System.Guid organizationId, [opt] int32 orgPriority, [opt] int32 orgWaitIterations, [opt] int32 orgCurrentThroughputQuotaUsage, [opt] int32 orgMaxThroughputQuota, [opt] int32 orgCurrentOutstandingOperation, [opt] int32 orgAvailableCapacity, [opt] int32 orgAllocatedCapacity, [opt] int32 newOperationsQueued, [opt] int32 actualWorkAllocated)
0x116a8  ret
0x116a9  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x116ae  ldarga.s 1
0x116b0  constrained. Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind
0x116b6  callvirt instance string [mscorlib]System.Object::ToString()
0x116bb  ldarg.3
0x116bc  callvirt instance string Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_WorkloadThrottlerName()
0x116c1  ldarg.3
0x116c2  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalPriority()
0x116c7  ldarg.3
0x116c8  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalCapacity()
0x116cd  ldarg.3
0x116ce  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalOutstandingOperation()
0x116d3  ldarg.3
0x116d4  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_IsInBacklogControlMode()
0x116d9  ldarg.3
0x116da  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryLow()
0x116df  ldarg.3
0x116e0  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryHigh()
0x116e5  ldarg.3
0x116e6  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_UseLegacyWorkloadThrottler()
0x116eb  ldarg.2
0x116ec  ldarg.s  4
0x116ee  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_OrganizationId()
0x116f3  ldarg.s  4
0x116f5  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_Priority()
0x116fa  ldarg.s  4
0x116fc  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_WaitIterations()
0x11701  ldarg.s  4
0x11703  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_CurrentThroughputQuotaUsage()
0x11708  ldarg.s  4
0x1170a  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_MaxThroughputQuota()
0x1170f  ldc.i4.m1
0x11710  ldc.i4.m1
0x11711  ldc.i4.m1
0x11712  ldc.i4.m1
0x11713  ldc.i4.m1
0x11714  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogAsyncDispatchDiagnosticsEvent(string selectExecutionKind, string workloadThrottlerName, int32 totalPriority, int32 totalCapacity, int32 totalOutstandingOperation, bool isInBacklogControlMode, int32 itemsInMemoryLow, int32 itemsInMemoryHigh, bool useLegacyWorkloadThrottler, int64 selectExecutionTimeInSec, valuetype [mscorlib]System.Guid organizationId, [opt] int32 orgPriority, [opt] int32 orgWaitIterations, [opt] int32 orgCurrentThroughputQuotaUsage, [opt] int32 orgMaxThroughputQuota, [opt] int32 orgCurrentOutstandingOperation, [opt] int32 orgAvailableCapacity, [opt] int32 orgAllocatedCapacity, [opt] int32 newOperationsQueued, [opt] int32 actualWorkAllocated)
0x11719  ret
```
