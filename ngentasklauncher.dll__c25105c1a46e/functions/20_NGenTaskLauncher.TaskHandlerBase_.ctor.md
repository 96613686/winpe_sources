# NGenTaskLauncher.TaskHandlerBase::.ctor

- ea: `0x20`
- end: `0x5c`
- name: `NGenTaskLauncher.TaskHandlerBase::.ctor`
- size: `60`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x370`
- `0x390`
- `0x3b0`
- `0x3d0`
- `0x3f0`
- `0x410`

## callees

- `0x2d0`
- `0x7b0`

## string_xrefs

- `0x40`: `Created launcher for `

## pseudocode

```c

```

## disassembly

```asm
0x20  ldarg.0
0x21  newobj   instance void [mscorlib]System.Object::.ctor()
0x26  stfld    object NGenTaskLauncher.TaskHandlerBase::lockObject
0x2b  ldarg.0
0x2c  call     instance void [mscorlib]System.Object::.ctor()
0x31  ldarg.0
0x32  ldarg.1
0x33  stfld    bool NGenTaskLauncher.TaskHandlerBase::isCritical
0x38  ldarg.0
0x39  ldarg.2
0x3a  stfld    valuetype NGenTaskLauncher.Architecture NGenTaskLauncher.TaskHandlerBase::architecture
0x3f  ldc.i4.3
0x40  ldstr    aCreatedLaunche// "Created launcher for "
0x45  ldarg.0
0x46  call     instance string NGenTaskLauncher.TaskHandlerBase::get_TaskId()
0x4b  call     string [mscorlib]System.String::Concat(string, string)
0x50  ldc.i4.0
0x51  newarr   [mscorlib]System.Object
0x56  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x5b  ret
```
