# Microsoft.Crm.Asynchronous.WorkloadThrottler::GetCustomProperties

- ea: `0x5940`
- end: `0x5b43`
- name: `Microsoft.Crm.Asynchronous.WorkloadThrottler::GetCustomProperties`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xace0`
- `0xade0`

## callees

- `0x5940`
- `0x5d30`

## string_xrefs

- `0x59cd`: `ItemsInMemoryLow`
- `0x59e6`: `ItemsInMemoryHigh`

## pseudocode

```c

```

## disassembly

```asm
0x5940  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x5945  stloc.0
0x5946  ldloc.0
0x5947  ldstr    aAsyncmanagerna// "AsyncManagerNames"
0x594c  ldarg.0
0x594d  call     instance string Microsoft.Crm.Asynchronous.WorkloadThrottler::get_QueueManagerName()
0x5952  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5957  ldloc.0
0x5958  ldstr    aWorkloadthrott_1// "WorkloadThrottlerName"
0x595d  ldarg.1
0x595e  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_WorkloadThrottlerName()
0x5963  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5968  ldloc.0
0x5969  ldstr    aTotalpriority// "TotalPriority"
0x596e  ldarg.1
0x596f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalPriority()
0x5974  stloc.1
0x5975  ldloca.s 1
0x5977  call     instance string [mscorlib]System.Int32::ToString()
0x597c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5981  ldloc.0
0x5982  ldstr    aTotalcapacity// "TotalCapacity"
0x5987  ldarg.1
0x5988  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalCapacity()
0x598d  stloc.1
0x598e  ldloca.s 1
0x5990  call     instance string [mscorlib]System.Int32::ToString()
0x5995  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x599a  ldloc.0
0x599b  ldstr    aTotaloutstandi// "TotalOutstandingOperation"
0x59a0  ldarg.1
0x59a1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_TotalOutstandingOperation()
0x59a6  stloc.1
0x59a7  ldloca.s 1
0x59a9  call     instance string [mscorlib]System.Int32::ToString()
0x59ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x59b3  ldloc.0
0x59b4  ldstr    aIsinbacklogcon// "IsInBacklogControlMode"
0x59b9  ldarg.1
0x59ba  callvirt instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_IsInBacklogControlMode()
0x59bf  stloc.2
0x59c0  ldloca.s 2
0x59c2  call     instance string [mscorlib]System.Boolean::ToString()
0x59c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x59cc  ldloc.0
0x59cd  ldstr    aItemsinmemoryl// "ItemsInMemoryLow"
0x59d2  ldarg.1
0x59d3  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryLow()
0x59d8  stloc.1
0x59d9  ldloca.s 1
0x59db  call     instance string [mscorlib]System.Int32::ToString()
0x59e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x59e5  ldloc.0
0x59e6  ldstr    aItemsinmemoryh// "ItemsInMemoryHigh"
0x59eb  ldarg.1
0x59ec  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_ItemsInMemoryHigh()
0x59f1  stloc.1
0x59f2  ldloca.s 1
0x59f4  call     instance string [mscorlib]System.Int32::ToString()
0x59f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x59fe  ldloc.0
0x59ff  ldstr    aUselegacyworkl// "UseLegacyWorkloadThrottler"
0x5a04  ldarg.1
0x5a05  callvirt instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionInfo::get_UseLegacyWorkloadThrottler()
0x5a0a  stloc.2
0x5a0b  ldloca.s 2
0x5a0d  call     instance string [mscorlib]System.Boolean::ToString()
0x5a12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5a17  ldarg.2
0x5a18  brtrue.s loc_5A39
0x5a1a  ldloc.0
0x5a1b  ldstr    aAsyncselecteve// "AsyncSelectEventExecutionKind"
0x5a20  ldc.i4.1
0x5a21  stloc.3
0x5a22  ldloca.s 3
0x5a24  constrained. [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind
0x5a2a  callvirt instance string [mscorlib]System.Object::ToString()
0x5a2f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5a34  br       loc_5B41
0x5a39  ldloc.0
0x5a3a  ldstr    aPriority// "Priority"
0x5a3f  ldarg.2
0x5a40  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_Priority()
0x5a45  stloc.1
0x5a46  ldloca.s 1
0x5a48  call     instance string [mscorlib]System.Int32::ToString()
0x5a4d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5a52  ldloc.0
0x5a53  ldstr    aWaititerations// "WaitIterations"
0x5a58  ldarg.2
0x5a59  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_WaitIterations()
0x5a5e  stloc.1
0x5a5f  ldloca.s 1
0x5a61  call     instance string [mscorlib]System.Int32::ToString()
0x5a66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5a6b  ldloc.0
0x5a6c  ldstr    aCurrentthrough// "CurrentThroughputQuotaUsage"
0x5a71  ldarg.2
0x5a72  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_CurrentThroughputQuotaUsage()
0x5a77  stloc.1
0x5a78  ldloca.s 1
0x5a7a  call     instance string [mscorlib]System.Int32::ToString()
0x5a7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5a84  ldloc.0
0x5a85  ldstr    aMaxthroughputq// "MaxThroughputQuota"
0x5a8a  ldarg.2
0x5a8b  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_MaxThroughputQuota()
0x5a90  stloc.1
0x5a91  ldloca.s 1
0x5a93  call     instance string [mscorlib]System.Int32::ToString()
0x5a98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5a9d  ldloc.0
0x5a9e  ldstr    aAsyncselecteve// "AsyncSelectEventExecutionKind"
0x5aa3  ldarg.2
0x5aa4  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_SelectEventExecutionKind()
0x5aa9  stloc.3
0x5aaa  ldloca.s 3
0x5aac  constrained. [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind
0x5ab2  callvirt instance string [mscorlib]System.Object::ToString()
0x5ab7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5abc  ldarg.2
0x5abd  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectEventExecutionKind [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_SelectEventExecutionKind()
0x5ac2  brtrue.s loc_5B41
0x5ac4  ldloc.0
0x5ac5  ldstr    aCurrentoutstan// "CurrentOutstandingOperation"
0x5aca  ldarg.2
0x5acb  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_CurrentOutstandingOperation()
0x5ad0  stloc.1
0x5ad1  ldloca.s 1
0x5ad3  call     instance string [mscorlib]System.Int32::ToString()
0x5ad8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5add  ldloc.0
0x5ade  ldstr    aAvailablecapac// "AvailableCapacity"
0x5ae3  ldarg.2
0x5ae4  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_AvailableCapacity()
0x5ae9  stloc.1
0x5aea  ldloca.s 1
0x5aec  call     instance string [mscorlib]System.Int32::ToString()
0x5af1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5af6  ldloc.0
0x5af7  ldstr    aAllocatedcapac// "AllocatedCapacity"
0x5afc  ldarg.2
0x5afd  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_AllocatedCapacity()
0x5b02  stloc.1
0x5b03  ldloca.s 1
0x5b05  call     instance string [mscorlib]System.Int32::ToString()
0x5b0a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5b0f  ldloc.0
0x5b10  ldstr    aNewoperationsq// "NewOperationsQueued"
0x5b15  ldarg.2
0x5b16  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_NewOperationsQueued()
0x5b1b  stloc.1
0x5b1c  ldloca.s 1
0x5b1e  call     instance string [mscorlib]System.Int32::ToString()
0x5b23  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5b28  ldloc.0
0x5b29  ldstr    aActualworkallo// "ActualWorkAllocated"
0x5b2e  ldarg.2
0x5b2f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSelectExecutionTracker::get_ActualWorkAllocated()
0x5b34  stloc.1
0x5b35  ldloca.s 1
0x5b37  call     instance string [mscorlib]System.Int32::ToString()
0x5b3c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5b41  ldloc.0
0x5b42  ret
```
