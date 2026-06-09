# Microsoft.Crm.Sandbox.SandboxStatistics::UpdateExisting

- ea: `0x5be0`
- end: `0x5f52`
- name: `Microsoft.Crm.Sandbox.SandboxStatistics::UpdateExisting`
- size: `882`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1a80`
- `0x57c0`
- `0x5970`
- `0x5a90`
- `0x5be0`

## string_xrefs

- `0x5be7`: `SandboxStatistics.UpdateExisting: enter`

## pseudocode

```c

```

## disassembly

```asm
0x5be0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5be5  ldc.i4.s 0x28
0x5be7  ldstr    aSandboxstatist_3// "SandboxStatistics.UpdateExisting: enter"
0x5bec  ldc.i4.0
0x5bed  newarr   [mscorlib]System.Object
0x5bf2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5bf7  ldarg.1
0x5bf8  ldstr    aEntity// "entity"
0x5bfd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c02  ldarg.0
0x5c03  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_wxr
0x5c08  ldstr    aWxr_0// "_wxr"
0x5c0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c12  ldarg.0
0x5c13  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5c18  ldstr    aPxr_0// "_pxr"
0x5c1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c22  ldarg.0
0x5c23  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_wxr
0x5c28  ldarg.0
0x5c29  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5c2e  newobj   instance void Microsoft.Crm.Sandbox.SandboxStatistics::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord wxr, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord pxr)
0x5c33  stloc.0
0x5c34  ldarg.0
0x5c35  ldarg.1
0x5c36  call     instance void Microsoft.Crm.Sandbox.SandboxStatistics::ReadCounts(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic entity)
0x5c3b  ldarg.0
0x5c3c  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5c41  ldloc.0
0x5c42  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5c47  add
0x5c48  stloc.1
0x5c49  ldloc.1
0x5c4a  ldc.r8   0.0
0x5c53  ble.un   loc_5DCC
0x5c58  ldarg.0
0x5c59  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5c5e  ldarg.0
0x5c5f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5c64  mul
0x5c65  ldloc.0
0x5c66  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5c6b  ldloc.0
0x5c6c  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5c71  mul
0x5c72  add
0x5c73  stloc.3
0x5c74  ldarg.0
0x5c75  ldloc.3
0x5c76  ldloc.1
0x5c77  div
0x5c78  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5c7d  ldarg.0
0x5c7e  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5c83  ldc.r8   100.0
0x5c8c  cgt.un
0x5c8e  ldc.i4.0
0x5c8f  ceq
0x5c91  ldstr    aCrashcontribut_0// "_crashContributionPercent"
0x5c96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5c9b  ldarg.0
0x5c9c  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5ca1  ldarg.0
0x5ca2  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5ca7  mul
0x5ca8  ldloc.0
0x5ca9  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5cae  ldloc.0
0x5caf  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5cb4  mul
0x5cb5  add
0x5cb6  stloc.3
0x5cb7  ldarg.0
0x5cb8  ldloc.3
0x5cb9  ldloc.1
0x5cba  div
0x5cbb  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5cc0  ldarg.0
0x5cc1  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5cc6  ldc.r8   100.0
0x5ccf  cgt.un
0x5cd1  ldc.i4.0
0x5cd2  ceq
0x5cd4  ldstr    aTerminatecpuco_0// "_terminateCpuContributionPercent"
0x5cd9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5cde  ldarg.0
0x5cdf  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5ce4  ldarg.0
0x5ce5  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5cea  mul
0x5ceb  ldloc.0
0x5cec  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5cf1  ldloc.0
0x5cf2  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5cf7  mul
0x5cf8  add
0x5cf9  stloc.3
0x5cfa  ldarg.0
0x5cfb  ldloc.3
0x5cfc  ldloc.1
0x5cfd  div
0x5cfe  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5d03  ldarg.0
0x5d04  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5d09  ldc.r8   100.0
0x5d12  cgt.un
0x5d14  ldc.i4.0
0x5d15  ceq
0x5d17  ldstr    aTerminatememor_0// "_terminateMemoryContributionPercent"
0x5d1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5d21  ldarg.0
0x5d22  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5d27  ldarg.0
0x5d28  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5d2d  mul
0x5d2e  ldloc.0
0x5d2f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5d34  ldloc.0
0x5d35  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5d3a  mul
0x5d3b  add
0x5d3c  stloc.3
0x5d3d  ldarg.0
0x5d3e  ldloc.3
0x5d3f  ldloc.1
0x5d40  div
0x5d41  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5d46  ldarg.0
0x5d47  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5d4c  ldc.r8   100.0
0x5d55  cgt.un
0x5d57  ldc.i4.0
0x5d58  ceq
0x5d5a  ldstr    aTerminatehandl_0// "_terminateHandlesContributionPercent"
0x5d5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5d64  ldarg.0
0x5d65  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5d6a  ldarg.0
0x5d6b  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5d70  mul
0x5d71  ldloc.0
0x5d72  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5d77  ldloc.0
0x5d78  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5d7d  mul
0x5d7e  add
0x5d7f  stloc.3
0x5d80  ldarg.0
0x5d81  ldloc.3
0x5d82  ldloc.1
0x5d83  div
0x5d84  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5d89  ldarg.0
0x5d8a  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5d8f  ldc.r8   100.0
0x5d98  cgt.un
0x5d9a  ldc.i4.0
0x5d9b  ceq
0x5d9d  ldstr    aTerminateother_0// "_terminateOtherContributionPercent"
0x5da2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5da7  ldarg.0
0x5da8  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x5dad  ldarg.0
0x5dae  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5db3  mul
0x5db4  ldloc.0
0x5db5  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x5dba  ldloc.0
0x5dbb  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5dc0  mul
0x5dc1  add
0x5dc2  stloc.3
0x5dc3  ldarg.0
0x5dc4  ldloc.3
0x5dc5  ldloc.1
0x5dc6  div
0x5dc7  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x5dcc  ldarg.0
0x5dcd  ldarg.0
0x5dce  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5dd3  ldloc.0
0x5dd4  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5dd9  add
0x5dda  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5ddf  ldarg.0
0x5de0  ldarg.0
0x5de1  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5de6  ldloc.0
0x5de7  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5dec  add
0x5ded  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5df2  ldarg.0
0x5df3  ldarg.0
0x5df4  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5df9  ldloc.0
0x5dfa  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5dff  add
0x5e00  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5e05  ldarg.0
0x5e06  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5e0b  ldc.r8   0.0
0x5e14  ble.un.s loc_5E8C
0x5e16  ldarg.0
0x5e17  ldarg.0
0x5e18  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5e1d  ldarg.0
0x5e1e  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5e23  div
0x5e24  ldc.r8   100.0
0x5e2d  mul
0x5e2e  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failurePercent
0x5e33  ldarg.0
0x5e34  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failurePercent
0x5e39  ldc.r8   100.0
0x5e42  cgt.un
0x5e44  ldc.i4.0
0x5e45  ceq
0x5e47  ldstr    aFailurepercent_0// "_failurePercent"
0x5e4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5e51  ldarg.0
0x5e52  ldarg.0
0x5e53  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5e58  ldarg.0
0x5e59  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5e5e  div
0x5e5f  ldc.r8   100.0
0x5e68  mul
0x5e69  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashPercent
0x5e6e  ldarg.0
0x5e6f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashPercent
0x5e74  ldc.r8   100.0
0x5e7d  cgt.un
0x5e7f  ldc.i4.0
0x5e80  ceq
0x5e82  ldstr    aCrashpercent_0// "_crashPercent"
0x5e87  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5e8c  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::get_ClientConfiguration()
0x5e91  ldc.i4.3
0x5e92  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientProperty)
0x5e97  stloc.2
0x5e98  ldarg.0
0x5e99  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5e9e  ldloc.2
0x5e9f  conv.r8
0x5ea0  ble.un   loc_5F4A
0x5ea5  ldarg.0
0x5ea6  ldc.r8   0.0
0x5eaf  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5eb4  ldarg.0
0x5eb5  ldc.r8   0.0
0x5ebe  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5ec3  ldarg.0
0x5ec4  ldc.r8   0.0
0x5ecd  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5ed2  ldarg.0
0x5ed3  ldc.r8   0.0
0x5edc  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failurePercent
0x5ee1  ldarg.0
0x5ee2  ldc.r8   0.0
0x5eeb  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashPercent
0x5ef0  ldarg.0
0x5ef1  ldc.r8   0.0
0x5efa  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x5eff  ldarg.0
0x5f00  ldc.r8   0.0
0x5f09  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x5f0e  ldarg.0
0x5f0f  ldc.r8   0.0
0x5f18  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5f1d  ldarg.0
0x5f1e  ldc.r8   0.0
0x5f27  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5f2c  ldarg.0
0x5f2d  ldc.r8   0.0
0x5f36  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5f3b  ldarg.0
0x5f3c  ldc.r8   0.0
0x5f45  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x5f4a  ldarg.0
0x5f4b  ldarg.1
0x5f4c  call     instance void Microsoft.Crm.Sandbox.SandboxStatistics::WriteCounts(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic entity)
0x5f51  ret
```
