# Microsoft.Crm.Sandbox.SandboxStatistics::.ctor

- ea: `0x57c0`
- end: `0x5968`
- name: `Microsoft.Crm.Sandbox.SandboxStatistics::.ctor`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5be0`
- `0x60b0`

## callees

- `0x57c0`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  ldarg.0
0x57c1  call     instance void [mscorlib]System.Object::.ctor()
0x57c6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x57cb  ldc.i4.s 0x28
0x57cd  ldstr    aSandboxstatist// "SandboxStatistics.ctor: enter"
0x57d2  ldc.i4.0
0x57d3  newarr   [mscorlib]System.Object
0x57d8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x57dd  ldarg.1
0x57de  ldstr    aWxr// "wxr"
0x57e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x57e8  ldarg.2
0x57e9  ldstr    aPxr// "pxr"
0x57ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x57f3  ldarg.0
0x57f4  ldarg.1
0x57f5  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_wxr
0x57fa  ldarg.0
0x57fb  ldarg.2
0x57fc  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5801  ldarg.0
0x5802  ldarg.0
0x5803  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5808  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
0x580d  conv.r8
0x580e  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5813  ldarg.0
0x5814  ldarg.0
0x5815  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x581a  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfBadRequests()
0x581f  conv.r8
0x5820  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5825  ldarg.0
0x5826  ldarg.0
0x5827  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x582c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginTypeId()
0x5831  ldarg.0
0x5832  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_wxr
0x5837  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_CrashPluginId()
0x583c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5841  brtrue.s loc_5846
0x5843  ldc.i4.0
0x5844  br.s     loc_5847
0x5846  ldc.i4.1
0x5847  conv.r8
0x5848  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x584d  ldarg.0
0x584e  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5853  ldc.r8   0.0
0x585c  ble.un.s loc_58C6
0x585e  ldarg.0
0x585f  ldarg.0
0x5860  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x5865  ldarg.0
0x5866  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x586b  div
0x586c  ldc.r8   100.0
0x5875  mul
0x5876  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failurePercent
0x587b  ldarg.0
0x587c  ldarg.0
0x587d  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashCount
0x5882  ldarg.0
0x5883  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x5888  div
0x5889  ldc.r8   100.0
0x5892  mul
0x5893  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashPercent
0x5898  ldarg.0
0x5899  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_executeCount
0x589e  ldarg.0
0x589f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_failureCount
0x58a4  sub
0x58a5  stloc.0
0x58a6  ldloc.0
0x58a7  ldc.r8   0.0
0x58b0  ble.un.s loc_58C6
0x58b2  ldarg.0
0x58b3  ldarg.0
0x58b4  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x58b9  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter::get_TotalRequestTimeInMSec()
0x58be  conv.r8
0x58bf  ldloc.0
0x58c0  div
0x58c1  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_averageExecuteTimeInMilliseconds
0x58c6  ldarg.0
0x58c7  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_wxr
0x58cc  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_ExitReason()
0x58d1  stloc.1
0x58d2  ldloc.1
0x58d3  switch   loc_5967, loc_5909, loc_5909, loc_5967, loc_5967, loc_5909, loc_591C, loc_592F, loc_5942, loc_5955, loc_5955, loc_5955
0x5908  ret
0x5909  ldarg.0
0x590a  ldarg.0
0x590b  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5910  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_Contribution()
0x5915  conv.r8
0x5916  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_crashContributionPercent
0x591b  ret
0x591c  ldarg.0
0x591d  ldarg.0
0x591e  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5923  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_Contribution()
0x5928  conv.r8
0x5929  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateCpuContributionPercent
0x592e  ret
0x592f  ldarg.0
0x5930  ldarg.0
0x5931  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5936  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_Contribution()
0x593b  conv.r8
0x593c  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateMemoryContributionPercent
0x5941  ret
0x5942  ldarg.0
0x5943  ldarg.0
0x5944  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5949  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_Contribution()
0x594e  conv.r8
0x594f  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateHandlesContributionPercent
0x5954  ret
0x5955  ldarg.0
0x5956  ldarg.0
0x5957  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x595c  callvirt instance int64 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_Contribution()
0x5961  conv.r8
0x5962  stfld    float64 Microsoft.Crm.Sandbox.SandboxStatistics::_terminateOtherContributionPercent
0x5967  ret
```
