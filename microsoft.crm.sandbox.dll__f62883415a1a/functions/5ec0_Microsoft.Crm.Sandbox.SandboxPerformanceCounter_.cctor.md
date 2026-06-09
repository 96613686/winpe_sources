# Microsoft.Crm.Sandbox.SandboxPerformanceCounter::.cctor

- ea: `0x5ec0`
- end: `0x5fd6`
- name: `Microsoft.Crm.Sandbox.SandboxPerformanceCounter::.cctor`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x5ec9`: `Assembly Cache Organizations`
- `0x5ed9`: `% Assembly Cache Hits`
- `0x5f2d`: `Assembly Cache Disk Space (KB)`
- `0x5f36`: `% Assembly Cache Usage`
- `0x5f3f`: `Assembly Cache Assemblies`
- `0x5f5a`: `Concurrent Plugins`
- `0x5f63`: `Active Plugins`

## pseudocode

```c

```

## disassembly

```asm
0x5ec0  ldc.i4.s 0x15
0x5ec2  newarr   [mscorlib]System.String
0x5ec7  dup
0x5ec8  ldc.i4.0
0x5ec9  ldstr    aAssemblyCacheO// "Assembly Cache Organizations"
0x5ece  stelem.ref
0x5ecf  dup
0x5ed0  ldc.i4.1
0x5ed1  ldstr    aActiveOrganiza// "Active Organizations"
0x5ed6  stelem.ref
0x5ed7  dup
0x5ed8  ldc.i4.2
0x5ed9  ldstr    aAssemblyCacheH// "% Assembly Cache Hits"
0x5ede  stelem.ref
0x5edf  dup
0x5ee0  ldc.i4.3
0x5ee1  ldstr    aMemoryUsageMb// "Memory Usage (MB)"
0x5ee6  stelem.ref
0x5ee7  dup
0x5ee8  ldc.i4.4
0x5ee9  ldstr    aCpuUsage// "% CPU Usage"
0x5eee  stelem.ref
0x5eef  dup
0x5ef0  ldc.i4.5
0x5ef1  ldstr    aHandles// "Handles"
0x5ef6  stelem.ref
0x5ef7  dup
0x5ef8  ldc.i4.6
0x5ef9  ldstr    aSdkRequestsSec// "SDK Requests/sec"
0x5efe  stelem.ref
0x5eff  dup
0x5f00  ldc.i4.7
0x5f01  ldstr    aSdkResponseTim// "SDK Response Time (msec)"
0x5f06  stelem.ref
0x5f07  dup
0x5f08  ldc.i4.8
0x5f09  ldstr    aSdkFailures// "% SDK Failures"
0x5f0e  stelem.ref
0x5f0f  dup
0x5f10  ldc.i4.s 9
0x5f12  ldstr    aExecutesSec// "Executes/sec"
0x5f17  stelem.ref
0x5f18  dup
0x5f19  ldc.i4.s 0xA
0x5f1b  ldstr    aExecuteRespons// "Execute Response Time (msec)"
0x5f20  stelem.ref
0x5f21  dup
0x5f22  ldc.i4.s 0xB
0x5f24  ldstr    aExecuteFailure// "% Execute Failures"
0x5f29  stelem.ref
0x5f2a  dup
0x5f2b  ldc.i4.s 0xC
0x5f2d  ldstr    aAssemblyCacheD// "Assembly Cache Disk Space (KB)"
0x5f32  stelem.ref
0x5f33  dup
0x5f34  ldc.i4.s 0xD
0x5f36  ldstr    aAssemblyCacheU// "% Assembly Cache Usage"
0x5f3b  stelem.ref
0x5f3c  dup
0x5f3d  ldc.i4.s 0xE
0x5f3f  ldstr    aAssemblyCacheA// "Assembly Cache Assemblies"
0x5f44  stelem.ref
0x5f45  dup
0x5f46  ldc.i4.s 0xF
0x5f48  ldstr    aWorkerProcesse// "% Worker Processes Crashed"
0x5f4d  stelem.ref
0x5f4e  dup
0x5f4f  ldc.i4.s 0x10
0x5f51  ldstr    aWorkerProcesse_0// "% Worker Processes Terminated"
0x5f56  stelem.ref
0x5f57  dup
0x5f58  ldc.i4.s 0x11
0x5f5a  ldstr    aConcurrentPlug// "Concurrent Plugins"
0x5f5f  stelem.ref
0x5f60  dup
0x5f61  ldc.i4.s 0x12
0x5f63  ldstr    aActivePlugins// "Active Plugins"
0x5f68  stelem.ref
0x5f69  dup
0x5f6a  ldc.i4.s 0x13
0x5f6c  ldstr    aActiveCustomAc// "Active Custom Activities"
0x5f71  stelem.ref
0x5f72  dup
0x5f73  ldc.i4.s 0x14
0x5f75  ldstr    aActiveAssembli// "Active Assemblies"
0x5f7a  stelem.ref
0x5f7b  stsfld   string[] Microsoft.Crm.Sandbox.SandboxPerformanceCounter::HostPerformanceCounterNames
0x5f80  ldc.i4.8
0x5f81  newarr   [mscorlib]System.String
0x5f86  dup
0x5f87  ldc.i4.0
0x5f88  ldstr    aSdkRequestsSec// "SDK Requests/sec"
0x5f8d  stelem.ref
0x5f8e  dup
0x5f8f  ldc.i4.1
0x5f90  ldstr    aSdkResponseTim// "SDK Response Time (msec)"
0x5f95  stelem.ref
0x5f96  dup
0x5f97  ldc.i4.2
0x5f98  ldstr    aSdkFailures// "% SDK Failures"
0x5f9d  stelem.ref
0x5f9e  dup
0x5f9f  ldc.i4.3
0x5fa0  ldstr    aExecutesSec// "Executes/sec"
0x5fa5  stelem.ref
0x5fa6  dup
0x5fa7  ldc.i4.4
0x5fa8  ldstr    aExecuteRespons// "Execute Response Time (msec)"
0x5fad  stelem.ref
0x5fae  dup
0x5faf  ldc.i4.5
0x5fb0  ldstr    aExecuteFailure// "% Execute Failures"
0x5fb5  stelem.ref
0x5fb6  dup
0x5fb7  ldc.i4.6
0x5fb8  ldstr    aTotalSandboxSe// "Total Sandbox Servers"
0x5fbd  stelem.ref
0x5fbe  dup
0x5fbf  ldc.i4.7
0x5fc0  ldstr    aHealthySandbox// "% Healthy Sandbox Servers"
0x5fc5  stelem.ref
0x5fc6  stsfld   string[] Microsoft.Crm.Sandbox.SandboxPerformanceCounter::ClientPerformanceCounterNames
0x5fcb  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [System]System.Diagnostics.PerformanceCounter>::.ctor()
0x5fd0  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Sandbox.SandboxPerformanceCounter::_performanceCounters
0x5fd5  ret
```
