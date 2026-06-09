# Microsoft.Crm.Sandbox.SandboxStatistics::ReadCounts

- ea: `0x5970`
- end: `0x5a90`
- name: `Microsoft.Crm.Sandbox.SandboxStatistics::ReadCounts`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5be0`

## string_xrefs

- `0x5977`: `SandboxStatistics.ReadCounts: enter`

## pseudocode

```c

```

## disassembly

```asm
0x5970  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5975  ldc.i4.s 0x28
0x5977  ldstr    aSandboxstatist_0// "SandboxStatistics.ReadCounts: enter"
0x597c  ldc.i4.0
0x597d  newarr   [mscorlib]System.Object
0x5982  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5987  ldarg.1
0x5988  ldstr    aEntity// "entity"
0x598d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5992  ldarg.0
0x5993  ldarg.1
0x5994  ldstr    aExecutecount// "executecount"
0x5999  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x599e  unbox.any [mscorlib]System.Int32
0x59a3  conv.r8
0x59a4  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x59a9  ldarg.0
0x59aa  ldarg.1
0x59ab  ldstr    aFailurecount// "failurecount"
0x59b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59b5  unbox.any [mscorlib]System.Int32
0x59ba  conv.r8
0x59bb  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x59c0  ldarg.0
0x59c1  ldarg.1
0x59c2  ldstr    aCrashcount// "crashcount"
0x59c7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59cc  unbox.any [mscorlib]System.Int32
0x59d1  conv.r8
0x59d2  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x59d7  ldarg.0
0x59d8  ldarg.1
0x59d9  ldstr    aFailurepercent// "failurepercent"
0x59de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59e3  unbox.any [mscorlib]System.Int32
0x59e8  conv.r8
0x59e9  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failurePercent
0x59ee  ldarg.0
0x59ef  ldarg.1
0x59f0  ldstr    aCrashpercent// "crashpercent"
0x59f5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59fa  unbox.any [mscorlib]System.Int32
0x59ff  conv.r8
0x5a00  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashPercent
0x5a05  ldarg.0
0x5a06  ldarg.1
0x5a07  ldstr    aCrashcontribut// "crashcontributionpercent"
0x5a0c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a11  unbox.any [mscorlib]System.Int32
0x5a16  conv.r8
0x5a17  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5a1c  ldarg.0
0x5a1d  ldarg.1
0x5a1e  ldstr    aTerminatecpuco// "terminatecpucontributionpercent"
0x5a23  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a28  unbox.any [mscorlib]System.Int32
0x5a2d  conv.r8
0x5a2e  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5a33  ldarg.0
0x5a34  ldarg.1
0x5a35  ldstr    aTerminatememor// "terminatememorycontributionpercent"
0x5a3a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a3f  unbox.any [mscorlib]System.Int32
0x5a44  conv.r8
0x5a45  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5a4a  ldarg.0
0x5a4b  ldarg.1
0x5a4c  ldstr    aTerminatehandl// "terminatehandlescontributionpercent"
0x5a51  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a56  unbox.any [mscorlib]System.Int32
0x5a5b  conv.r8
0x5a5c  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5a61  ldarg.0
0x5a62  ldarg.1
0x5a63  ldstr    aTerminateother// "terminateothercontributionpercent"
0x5a68  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a6d  unbox.any [mscorlib]System.Int32
0x5a72  conv.r8
0x5a73  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5a78  ldarg.0
0x5a79  ldarg.1
0x5a7a  ldstr    aAverageexecute// "averageexecutetimeinmilliseconds"
0x5a7f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a84  unbox.any [mscorlib]System.Int32
0x5a89  conv.r8
0x5a8a  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x5a8f  ret
```
