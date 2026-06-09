# NGenTaskLauncher.TaskHandlerBase::ThreadProc

- ea: `0x1e0`
- end: `0x2c1`
- name: `NGenTaskLauncher.TaskHandlerBase::ThreadProc`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1e0`
- `0x2d0`
- `0x490`
- `0x4b0`
- `0x7b0`
- `0x7d0`

## string_xrefs

- `0x21f`: `Unable to launch NGen Task`
- `0x282`: `ITaskHandlerStatus::TaskCompleted failed`
- `0x2a7`: `Task completed with status {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1e0  ldc.i4.3
0x1e1  ldarg.0
0x1e2  call     instance string NGenTaskLauncher.TaskHandlerBase::get_TaskId()
0x1e7  ldstr    aStarting// " starting"
0x1ec  call     string [mscorlib]System.String::Concat(string, string)
0x1f1  ldc.i4.0
0x1f2  newarr   [mscorlib]System.Object
0x1f7  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1fc  ldarg.0
0x1fd  ldfld    class NGenTaskLauncher.NGenTaskLauncher NGenTaskLauncher.TaskHandlerBase::launcher
0x202  ldarg.0
0x203  ldfld    string NGenTaskLauncher.TaskHandlerBase::taskParameters
0x208  ldarg.0
0x209  ldfld    bool NGenTaskLauncher.TaskHandlerBase::isCritical
0x20e  ldarg.0
0x20f  ldfld    valuetype NGenTaskLauncher.Architecture NGenTaskLauncher.TaskHandlerBase::architecture
0x214  callvirt instance int32 NGenTaskLauncher.NGenTaskLauncher::Launch(string taskParameters, bool isCritical, valuetype NGenTaskLauncher.Architecture architecture)
0x219  stloc.0
0x21a  leave.s  loc_233
0x21c  stloc.1
0x21d  ldc.i4.0
0x21e  ldloc.1
0x21f  ldstr    aUnableToLaunch// "Unable to launch NGen Task"
0x224  ldc.i4.0
0x225  newarr   [mscorlib]System.Object
0x22a  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x22f  ldc.i4.m1
0x230  stloc.0
0x231  leave.s  loc_233
0x233  ldc.i4.3
0x234  ldarg.0
0x235  call     instance string NGenTaskLauncher.TaskHandlerBase::get_TaskId()
0x23a  ldstr    aEnding// " ending"
0x23f  call     string [mscorlib]System.String::Concat(string, string)
0x244  ldc.i4.0
0x245  newarr   [mscorlib]System.Object
0x24a  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x24f  ldarg.0
0x250  ldfld    object NGenTaskLauncher.TaskHandlerBase::lockObject
0x255  stloc.2
0x256  ldc.i4.0
0x257  stloc.3
0x258  ldloc.2
0x259  ldloca.s 3
0x25b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x260  ldarg.0
0x261  ldfld    class NGenTaskLauncher.ITaskHandlerStatus NGenTaskLauncher.TaskHandlerBase::pTaskHandlerStatus
0x266  brfalse.s loc_294
0x268  ldarg.0
0x269  ldfld    class NGenTaskLauncher.ITaskHandlerStatus NGenTaskLauncher.TaskHandlerBase::pTaskHandlerStatus
0x26e  ldloc.0
0x26f  callvirt instance void NGenTaskLauncher.ITaskHandlerStatus::TaskCompleted(int32 taskErrCode)
0x274  ldarg.0
0x275  ldc.i4.1
0x276  stfld    bool NGenTaskLauncher.TaskHandlerBase::fCompleted
0x27b  leave.s  loc_2A0
0x27d  stloc.s  4
0x27f  ldc.i4.0
0x280  ldloc.s  4
0x282  ldstr    aItaskhandlerst// "ITaskHandlerStatus::TaskCompleted faile"...
0x287  ldc.i4.0
0x288  newarr   [mscorlib]System.Object
0x28d  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x292  leave.s  loc_2A0
0x294  leave.s  loc_2A0
0x296  ldloc.3
0x297  brfalse.s loc_29F
0x299  ldloc.2
0x29a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x29f  endfinally
0x2a0  ldloc.0
0x2a1  brfalse.s loc_2A6
0x2a3  ldc.i4.0
0x2a4  br.s     loc_2A7
0x2a6  ldc.i4.2
0x2a7  ldstr    aTaskCompletedW// "Task completed with status {0}"
0x2ac  ldc.i4.1
0x2ad  newarr   [mscorlib]System.Object
0x2b2  dup
0x2b3  ldc.i4.0
0x2b4  ldloc.0
0x2b5  box      [mscorlib]System.Int32
0x2ba  stelem.ref
0x2bb  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2c0  ret
```
