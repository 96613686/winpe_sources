# NGenTaskLauncher.TaskHandlerBase::get_TaskId

- ea: `0x2d0`
- end: `0x358`
- name: `NGenTaskLauncher.TaskHandlerBase::get_TaskId`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x20`
- `0x60`
- `0x120`
- `0x1e0`

## callees

- `0x2d0`
- `0x7b0`

## string_xrefs

- `0x319`: ` in NGenTaskLauncher`

## pseudocode

```c

```

## disassembly

```asm
0x2d0  ldarg.0
0x2d1  ldfld    valuetype NGenTaskLauncher.Architecture NGenTaskLauncher.TaskHandlerBase::architecture
0x2d6  stloc.2
0x2d7  ldloc.2
0x2d8  switch   loc_2EB, loc_2F3, loc_2FB
0x2e9  br.s     loc_303
0x2eb  ldstr    a32Bit// "32-bit "
0x2f0  stloc.0
0x2f1  br.s     loc_338
0x2f3  ldstr    a64Bit// "64-bit "
0x2f8  stloc.0
0x2f9  br.s     loc_338
0x2fb  ldstr    a64BitArm64// "64-bit Arm64 "
0x300  stloc.0
0x301  br.s     loc_338
0x303  ldstr    aUnexpectedArch// "Unexpected architecture "
0x308  ldarg.0
0x309  ldflda   valuetype NGenTaskLauncher.Architecture NGenTaskLauncher.TaskHandlerBase::architecture
0x30e  constrained. NGenTaskLauncher.Architecture
0x314  callvirt instance string [mscorlib]System.Object::ToString()
0x319  ldstr    aInNgentasklaun// " in NGenTaskLauncher"
0x31e  call     string [mscorlib]System.String::Concat(string, string, string)
0x323  stloc.1
0x324  ldc.i4.0
0x325  ldloc.1
0x326  ldc.i4.0
0x327  newarr   [mscorlib]System.Object
0x32c  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x331  ldloc.1
0x332  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x337  throw
0x338  ldloc.0
0x339  ldarg.0
0x33a  ldfld    bool NGenTaskLauncher.TaskHandlerBase::isCritical
0x33f  brtrue.s loc_348
0x341  ldsfld   string [mscorlib]System.String::Empty
0x346  br.s     loc_34D
0x348  ldstr    aCritical// "critical "
0x34d  ldstr    aTask// "task"
0x352  call     string [mscorlib]System.String::Concat(string, string, string)
0x357  ret
```
