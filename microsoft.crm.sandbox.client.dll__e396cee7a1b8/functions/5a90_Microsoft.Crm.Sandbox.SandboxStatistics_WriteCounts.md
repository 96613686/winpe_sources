# Microsoft.Crm.Sandbox.SandboxStatistics::WriteCounts

- ea: `0x5a90`
- end: `0x5bb0`
- name: `Microsoft.Crm.Sandbox.SandboxStatistics::WriteCounts`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5bb0`
- `0x5be0`

## string_xrefs

- `0x5a97`: `SandboxStatistics.WriteCounts: enter`

## pseudocode

```c

```

## disassembly

```asm
0x5a90  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a95  ldc.i4.s 0x28
0x5a97  ldstr    aSandboxstatist_1// "SandboxStatistics.WriteCounts: enter"
0x5a9c  ldc.i4.0
0x5a9d  newarr   [mscorlib]System.Object
0x5aa2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5aa7  ldarg.1
0x5aa8  ldstr    aEntity// "entity"
0x5aad  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5ab2  ldarg.1
0x5ab3  ldstr    aExecutecount// "executecount"
0x5ab8  ldarg.0
0x5ab9  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5abe  conv.i4
0x5abf  box      [mscorlib]System.Int32
0x5ac4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5ac9  ldarg.1
0x5aca  ldstr    aFailurecount// "failurecount"
0x5acf  ldarg.0
0x5ad0  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5ad5  conv.i4
0x5ad6  box      [mscorlib]System.Int32
0x5adb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5ae0  ldarg.1
0x5ae1  ldstr    aCrashcount// "crashcount"
0x5ae6  ldarg.0
0x5ae7  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5aec  conv.i4
0x5aed  box      [mscorlib]System.Int32
0x5af2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5af7  ldarg.1
0x5af8  ldstr    aFailurepercent// "failurepercent"
0x5afd  ldarg.0
0x5afe  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failurePercent
0x5b03  conv.i4
0x5b04  box      [mscorlib]System.Int32
0x5b09  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b0e  ldarg.1
0x5b0f  ldstr    aCrashpercent// "crashpercent"
0x5b14  ldarg.0
0x5b15  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashPercent
0x5b1a  conv.i4
0x5b1b  box      [mscorlib]System.Int32
0x5b20  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b25  ldarg.1
0x5b26  ldstr    aCrashcontribut// "crashcontributionpercent"
0x5b2b  ldarg.0
0x5b2c  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5b31  conv.i4
0x5b32  box      [mscorlib]System.Int32
0x5b37  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b3c  ldarg.1
0x5b3d  ldstr    aTerminatecpuco// "terminatecpucontributionpercent"
0x5b42  ldarg.0
0x5b43  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5b48  conv.i4
0x5b49  box      [mscorlib]System.Int32
0x5b4e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b53  ldarg.1
0x5b54  ldstr    aTerminatememor// "terminatememorycontributionpercent"
0x5b59  ldarg.0
0x5b5a  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5b5f  conv.i4
0x5b60  box      [mscorlib]System.Int32
0x5b65  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b6a  ldarg.1
0x5b6b  ldstr    aTerminatehandl// "terminatehandlescontributionpercent"
0x5b70  ldarg.0
0x5b71  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5b76  conv.i4
0x5b77  box      [mscorlib]System.Int32
0x5b7c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b81  ldarg.1
0x5b82  ldstr    aTerminateother// "terminateothercontributionpercent"
0x5b87  ldarg.0
0x5b88  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5b8d  conv.i4
0x5b8e  box      [mscorlib]System.Int32
0x5b93  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b98  ldarg.1
0x5b99  ldstr    aAverageexecute// "averageexecutetimeinmilliseconds"
0x5b9e  ldarg.0
0x5b9f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x5ba4  conv.i4
0x5ba5  box      [mscorlib]System.Int32
0x5baa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5baf  ret
```
