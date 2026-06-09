# Microsoft.Crm.Sandbox.SandboxWorkerProcess::TrackCall

- ea: `0xa810`
- end: `0xa91a`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::TrackCall`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xa960`
- `0xb140`

## callees

- `0x48e0`
- `0x4900`
- `0x57c0`
- `0x9730`
- `0xa810`

## pseudocode

```c

```

## disassembly

```asm
0xa810  ldarg.1
0xa811  ldarg.s  4
0xa813  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xa818  ldarg.s  5
0xa81a  ldarg.s  6
0xa81c  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid, string, string)
0xa821  ldarg.1
0xa822  ldarg.2
0xa823  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_Destination()
0xa828  ldarg.s  4
0xa82a  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0xa82f  ldarg.3
0xa830  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Call(string, int32, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0xa835  ldarg.0
0xa836  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerExecuteCount
0xa83b  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xa840  pop
0xa841  ldarg.0
0xa842  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_totalWorkerExecuteCount
0xa847  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xa84c  pop
0xa84d  ldarg.0
0xa84e  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xa853  ldc.i4.s 0xA
0xa855  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xa85a  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostWorkerConfiguration()
0xa85f  ldc.i4.4
0xa860  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0xa865  ldc.i4.s 0x1E
0xa867  add
0xa868  call     int32 [mscorlib]System.Math::Max(int32, int32)
0xa86d  stfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_operationTimeoutInSec
0xa872  ldarg.2
0xa873  ldc.i4.0
0xa874  ldc.i4.0
0xa875  ldarg.0
0xa876  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_operationTimeoutInSec
0xa87b  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa880  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::SetOperationTimeout(valuetype [mscorlib]System.TimeSpan)
0xa885  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa88a  ldstr    a01// "{0}{1}"
0xa88f  ldc.i4.2
0xa890  newarr   [mscorlib]System.Object
0xa895  dup
0xa896  ldc.i4.0
0xa897  ldc.i4.2
0xa898  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0xa89d  stelem.ref
0xa89e  dup
0xa89f  ldc.i4.1
0xa8a0  ldc.i4.s 0x10
0xa8a2  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0xa8a7  stelem.ref
0xa8a8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8ad  ldc.i4.s 0x28
0xa8af  box      [mscorlib]System.Int32
0xa8b4  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xa8b9  unbox.any [mscorlib]System.Int32
0xa8be  stloc.0
0xa8bf  ldarg.0
0xa8c0  ldarg.0
0xa8c1  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_operationTimeoutInSec
0xa8c6  ldloc.0
0xa8c7  sub
0xa8c8  stfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_executionTimeoutInSec
0xa8cd  ldarg.0
0xa8ce  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa8d3  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xa8d8  ldarg.s  7
0xa8da  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::ActiveAssembly(valuetype [mscorlib]System.Guid)
0xa8df  ldarg.s  4
0xa8e1  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext
0xa8e6  brfalse.s loc_A8FC
0xa8e8  ldarg.0
0xa8e9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa8ee  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xa8f3  ldarg.s  8
0xa8f5  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::ActiveCustomActivity(valuetype [mscorlib]System.Guid)
0xa8fa  br.s     loc_A90E
0xa8fc  ldarg.0
0xa8fd  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa902  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xa907  ldarg.s  8
0xa909  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::ActivePlugin(valuetype [mscorlib]System.Guid)
0xa90e  ldarg.2
0xa90f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa914  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_LastCall(valuetype [mscorlib]System.DateTime value)
0xa919  ret
```
