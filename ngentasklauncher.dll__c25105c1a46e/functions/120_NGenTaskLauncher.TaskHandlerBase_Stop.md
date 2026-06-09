# NGenTaskLauncher.TaskHandlerBase::Stop

- ea: `0x120`
- end: `0x1b5`
- name: `NGenTaskLauncher.TaskHandlerBase::Stop`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x120`
- `0x2d0`
- `0x6a0`
- `0x7b0`

## string_xrefs

- `0x121`: `Task scheduler requested stopping `

## pseudocode

```c

```

## disassembly

```asm
0x120  ldc.i4.2
0x121  ldstr    aTaskSchedulerR_0// "Task scheduler requested stopping "
0x126  ldarg.0
0x127  call     instance string NGenTaskLauncher.TaskHandlerBase::get_TaskId()
0x12c  call     string [mscorlib]System.String::Concat(string, string)
0x131  ldc.i4.0
0x132  newarr   [mscorlib]System.Object
0x137  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x13c  ldarg.0
0x13d  ldfld    class NGenTaskLauncher.NGenTaskLauncher NGenTaskLauncher.TaskHandlerBase::launcher
0x142  brfalse.s loc_1B1
0x144  ldc.i4.1
0x145  stloc.0
0x146  ldarg.0
0x147  ldfld    object NGenTaskLauncher.TaskHandlerBase::lockObject
0x14c  stloc.1
0x14d  ldc.i4.0
0x14e  stloc.2
0x14f  ldloc.1
0x150  ldloca.s 2
0x152  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x157  ldarg.0
0x158  ldnull
0x159  stfld    class NGenTaskLauncher.ITaskHandlerStatus NGenTaskLauncher.TaskHandlerBase::pTaskHandlerStatus
0x15e  ldarg.0
0x15f  ldfld    bool NGenTaskLauncher.TaskHandlerBase::fCompleted
0x164  brfalse.s loc_168
0x166  ldc.i4.0
0x167  stloc.0
0x168  leave.s  loc_174
0x16a  ldloc.2
0x16b  brfalse.s loc_173
0x16d  ldloc.1
0x16e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x173  endfinally
0x174  ldloc.0
0x175  brfalse.s loc_182
0x177  ldarg.0
0x178  ldfld    class NGenTaskLauncher.NGenTaskLauncher NGenTaskLauncher.TaskHandlerBase::launcher
0x17d  callvirt instance void NGenTaskLauncher.NGenTaskLauncher::Stop()
0x182  ldarg.0
0x183  ldfld    class [mscorlib]System.Threading.Thread NGenTaskLauncher.TaskHandlerBase::workerThread
0x188  brfalse.s loc_195
0x18a  ldarg.0
0x18b  ldfld    class [mscorlib]System.Threading.Thread NGenTaskLauncher.TaskHandlerBase::workerThread
0x190  callvirt instance void [mscorlib]System.Threading.Thread::Join()
0x195  ldc.i4.2
0x196  ldstr    aStopped// "Stopped "
0x19b  ldarg.0
0x19c  call     instance string NGenTaskLauncher.TaskHandlerBase::get_TaskId()
0x1a1  call     string [mscorlib]System.String::Concat(string, string)
0x1a6  ldc.i4.0
0x1a7  newarr   [mscorlib]System.Object
0x1ac  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1b1  ldarg.1
0x1b2  ldc.i4.0
0x1b3  stind.i4
0x1b4  ret
```
