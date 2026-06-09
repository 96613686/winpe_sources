# NGenTaskLauncher.CriticalTaskHandler32::.ctor

- ea: `0x410`
- end: `0x419`
- name: `NGenTaskLauncher.CriticalTaskHandler32::.ctor`
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
0x410  ldarg.0
0x411  ldc.i4.1
0x412  ldc.i4.0
0x413  call     instance void NGenTaskLauncher.TaskHandlerBase::.ctor(bool isCritical, valuetype NGenTaskLauncher.Architecture architecture)
0x418  ret
```
