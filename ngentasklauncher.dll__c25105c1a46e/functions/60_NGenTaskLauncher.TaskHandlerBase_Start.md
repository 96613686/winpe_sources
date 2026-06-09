# NGenTaskLauncher.TaskHandlerBase::Start

- ea: `0x60`
- end: `0x111`
- name: `NGenTaskLauncher.TaskHandlerBase::Start`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x60`
- `0x2d0`
- `0x730`
- `0x7b0`
- `0x850`

## string_xrefs

- `0xb3`: `Task scheduler requested starting `

## pseudocode

```c

```

## disassembly

```asm
0x60  ldarg.2
0x61  brfalse.s loc_6D
0x63  ldarg.2
0x64  ldnull
0x65  ldc.i4.1
0x66  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x6b  br.s     loc_73
0x6d  ldc.i4.0
0x6e  newarr   [mscorlib]System.String
0x73  stloc.0
0x74  ldloc.0
0x75  stloc.1
0x76  ldc.i4.0
0x77  stloc.2
0x78  br.s     loc_AC
0x7a  ldloc.1
0x7b  ldloc.2
0x7c  ldelem.ref
0x7d  stloc.3
0x7e  ldloc.3
0x7f  ldstr    aVerbose// "/Verbose"
0x84  ldc.i4.5
0x85  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8a  brfalse.s loc_94
0x8c  ldc.i4.3
0x8d  call     void NGenTaskLauncher.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x92  br.s     loc_A8
0x94  ldloc.3
0x95  ldstr    aSilent// "/Silent"
0x9a  ldc.i4.5
0x9b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xa0  brfalse.s loc_A8
0xa2  ldc.i4.1
0xa3  call     void NGenTaskLauncher.Logger::set_MaxLogLevel(valuetype LogLevel value)
0xa8  ldloc.2
0xa9  ldc.i4.1
0xaa  add
0xab  stloc.2
0xac  ldloc.2
0xad  ldloc.1
0xae  ldlen
0xaf  conv.i4
0xb0  blt.s    loc_7A
0xb2  ldc.i4.2
0xb3  ldstr    aTaskSchedulerR// "Task scheduler requested starting "
0xb8  ldarg.0
0xb9  call     instance string NGenTaskLauncher.TaskHandlerBase::get_TaskId()
0xbe  call     string [mscorlib]System.String::Concat(string, string)
0xc3  ldc.i4.0
0xc4  newarr   [mscorlib]System.Object
0xc9  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0xce  ldarg.0
0xcf  ldarg.1
0xd0  stfld    class NGenTaskLauncher.ITaskHandlerStatus NGenTaskLauncher.TaskHandlerBase::pTaskHandlerStatus
0xd5  ldarg.0
0xd6  ldarg.2
0xd7  stfld    string NGenTaskLauncher.TaskHandlerBase::taskParameters
0xdc  ldarg.0
0xdd  newobj   instance void NGenTaskLauncher.NGenTaskLauncher::.ctor()
0xe2  stfld    class NGenTaskLauncher.NGenTaskLauncher NGenTaskLauncher.TaskHandlerBase::launcher
0xe7  ldarg.0
0xe8  ldc.i4.0
0xe9  stfld    bool NGenTaskLauncher.TaskHandlerBase::fCompleted
0xee  ldarg.0
0xef  ldarg.0
0xf0  ldftn    instance void NGenTaskLauncher.TaskHandlerBase::ThreadProc()
0xf6  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0xfb  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x100  stfld    class [mscorlib]System.Threading.Thread NGenTaskLauncher.TaskHandlerBase::workerThread
0x105  ldarg.0
0x106  ldfld    class [mscorlib]System.Threading.Thread NGenTaskLauncher.TaskHandlerBase::workerThread
0x10b  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x110  ret
```
