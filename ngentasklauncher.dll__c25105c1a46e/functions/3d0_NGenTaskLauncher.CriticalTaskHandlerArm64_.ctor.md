# NGenTaskLauncher.CriticalTaskHandlerArm64::.ctor

- ea: `0x3d0`
- end: `0x3d9`
- name: `NGenTaskLauncher.CriticalTaskHandlerArm64::.ctor`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x20`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  ldarg.0
0x3d1  ldc.i4.1
0x3d2  ldc.i4.2
0x3d3  call     instance void NGenTaskLauncher.TaskHandlerBase::.ctor(bool isCritical, valuetype NGenTaskLauncher.Architecture architecture)
0x3d8  ret
```
