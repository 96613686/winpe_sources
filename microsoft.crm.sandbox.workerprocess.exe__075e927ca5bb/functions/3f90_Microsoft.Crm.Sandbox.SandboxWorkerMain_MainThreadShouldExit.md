# Microsoft.Crm.Sandbox.SandboxWorkerMain::MainThreadShouldExit

- ea: `0x3f90`
- end: `0x416a`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::MainThreadShouldExit`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x3aa0`

## callees

- `0x39a0`
- `0x39c0`
- `0x39d0`
- `0x3f90`
- `0x4170`
- `0x4200`
- `0x4720`
- `0x4820`

## string_xrefs

- `0x3fbb`: `SandboxWorkerMain.MainThreadShouldExit: Worker {0}: executeStartTime has value, checking max lifetime.`
- `0x3ffa`: `SandboxWorkerMain.MainThreadShouldExit: Worker {0}: lifetime exceeded, recycling process`
- `0x4051`: `SandboxWorkerMain.MainThreadShouldExit: Worker {0}: has execution since last check. Checking if idle.`
- `0x4094`: `SandboxWorkerMain.MainThreadShouldExit: Worker {0}: idle timeout exceeded, shutting down`
- `0x40e7`: `SandboxWorkerMain.MainThreadShouldExit: Worker {0}: Missing plugin assembly, which should never happen inside a WP. Shutting down`
- `0x410a`: `Missing Plugin Assembly`
- `0x412d`: `SandboxWorkerMain.MainThreadShouldExit: Worker {0}: Shutdown requested because of a crash.`

## pseudocode

```c

```

## disassembly

```asm
0x3f90  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::MinimumWorkerWait()
0x3f95  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::RecycleAppDomain()
0x3f9a  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::get_ExecuteStartTime()
0x3f9f  stloc.0
0x3fa0  ldloc.0
0x3fa1  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x3fa6  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3fab  brfalse  loc_403B
0x3fb0  ldnull
0x3fb1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3fb6  ldc.i4.3
0x3fb7  ldc.i4.s 0x26
0x3fb9  ldc.i4.0
0x3fba  ldc.i4.1
0x3fbb  ldstr    aSandboxworkerm_12// "SandboxWorkerMain.MainThreadShouldExit:"...
0x3fc0  ldc.i4.1
0x3fc1  newarr   [mscorlib]System.Object
0x3fc6  dup
0x3fc7  ldc.i4.0
0x3fc8  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0x3fcd  box      [mscorlib]System.Guid
0x3fd2  stelem.ref
0x3fd3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x3fd8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3fdd  ldloc.0
0x3fde  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3fe3  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.SandboxWorkerMain::_maxLifetime
0x3fe8  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3fed  brfalse.s loc_403B
0x3fef  ldnull
0x3ff0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ff5  ldc.i4.3
0x3ff6  ldc.i4.s 0x26
0x3ff8  ldc.i4.0
0x3ff9  ldc.i4.1
0x3ffa  ldstr    aSandboxworkerm_13// "SandboxWorkerMain.MainThreadShouldExit:"...
0x3fff  ldc.i4.1
0x4000  newarr   [mscorlib]System.Object
0x4005  dup
0x4006  ldc.i4.0
0x4007  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0x400c  box      [mscorlib]System.Guid
0x4011  stelem.ref
0x4012  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x4017  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::Shutdown()
0x401c  ldarg.0
0x401d  ldstr    aMaxLifecycleTi// "Max lifecycle Time Exceeded"
0x4022  stind.ref
0x4023  ldarg.1
0x4024  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalIdleTimeInMin
0x4029  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x402e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4033  stind.ref
0x4034  ldc.i4.1
0x4035  stloc.1
0x4036  leave    loc_4168
0x403b  call     int32 Microsoft.Crm.Sandbox.SandboxWorker::get_ExecuteCount()
0x4040  ldc.i4.0
0x4041  ble      loc_40D5
0x4046  ldnull
0x4047  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x404c  ldc.i4.3
0x404d  ldc.i4.s 0x26
0x404f  ldc.i4.0
0x4050  ldc.i4.1
0x4051  ldstr    aSandboxworkerm_14// "SandboxWorkerMain.MainThreadShouldExit:"...
0x4056  ldc.i4.1
0x4057  newarr   [mscorlib]System.Object
0x405c  dup
0x405d  ldc.i4.0
0x405e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0x4063  box      [mscorlib]System.Guid
0x4068  stelem.ref
0x4069  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x406e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4073  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::get_LastExecuteTime()
0x4078  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x407d  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.SandboxWorkerMain::_maxIdleTime
0x4082  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x4087  brfalse.s loc_40D5
0x4089  ldnull
0x408a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x408f  ldc.i4.3
0x4090  ldc.i4.s 0x26
0x4092  ldc.i4.0
0x4093  ldc.i4.1
0x4094  ldstr    aSandboxworkerm_15// "SandboxWorkerMain.MainThreadShouldExit:"...
0x4099  ldc.i4.1
0x409a  newarr   [mscorlib]System.Object
0x409f  dup
0x40a0  ldc.i4.0
0x40a1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0x40a6  box      [mscorlib]System.Guid
0x40ab  stelem.ref
0x40ac  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x40b1  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::Shutdown()
0x40b6  ldarg.0
0x40b7  ldstr    aIdleTimeExceed// "Idle Time Exceeded"
0x40bc  stind.ref
0x40bd  ldarg.1
0x40be  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalIdleTimeInMin
0x40c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40c8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x40cd  stind.ref
0x40ce  ldc.i4.1
0x40cf  stloc.1
0x40d0  leave    loc_4168
0x40d5  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerMain::_shutdownForMissingAssembly
0x40da  brfalse.s loc_411B
0x40dc  ldnull
0x40dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40e2  ldc.i4.1
0x40e3  ldc.i4.s 0x26
0x40e5  ldc.i4.0
0x40e6  ldc.i4.1
0x40e7  ldstr    aSandboxworkerm_16// "SandboxWorkerMain.MainThreadShouldExit:"...
0x40ec  ldc.i4.1
0x40ed  newarr   [mscorlib]System.Object
0x40f2  dup
0x40f3  ldc.i4.0
0x40f4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0x40f9  box      [mscorlib]System.Guid
0x40fe  stelem.ref
0x40ff  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x4104  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::Shutdown()
0x4109  ldarg.0
0x410a  ldstr    aMissingPluginA// "Missing Plugin Assembly"
0x410f  stind.ref
0x4110  ldarg.1
0x4111  ldsfld   string [mscorlib]System.String::Empty
0x4116  stind.ref
0x4117  ldc.i4.1
0x4118  stloc.1
0x4119  leave.s  loc_4168
0x411b  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerMain::_shutdownForCrash
0x4120  brfalse.s loc_415C
0x4122  ldnull
0x4123  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4128  ldc.i4.1
0x4129  ldc.i4.s 0x26
0x412b  ldc.i4.0
0x412c  ldc.i4.1
0x412d  ldstr    aSandboxworkerm_17// "SandboxWorkerMain.MainThreadShouldExit:"...
0x4132  ldc.i4.1
0x4133  newarr   [mscorlib]System.Object
0x4138  dup
0x4139  ldc.i4.0
0x413a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0x413f  box      [mscorlib]System.Guid
0x4144  stelem.ref
0x4145  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x414a  ldarg.0
0x414b  ldstr    aSandboxWorkerP_0// "Sandbox worker process crashed"
0x4150  stind.ref
0x4151  ldarg.1
0x4152  ldsfld   string [mscorlib]System.String::Empty
0x4157  stind.ref
0x4158  ldc.i4.1
0x4159  stloc.1
0x415a  leave.s  loc_4168
0x415c  ldc.i4.0
0x415d  stloc.1
0x415e  leave.s  loc_4168
0x4160  pop
0x4161  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::Shutdown()
0x4166  rethrow
0x4168  ldloc.1
0x4169  ret
```
