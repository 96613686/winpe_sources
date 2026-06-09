# ScanHostWorkersThreadActivity::.ctor

- ea: `0xc3d0`
- end: `0xc3de`
- name: `ScanHostWorkersThreadActivity::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0xc3d1`: `ScanWorkersThread`

## pseudocode

```c

```

## disassembly

```asm
0xc3d0  ldarg.0
0xc3d1  ldstr    aScanworkersthr// "ScanWorkersThread"
0xc3d6  ldc.i4.1
0xc3d7  ldc.i4.1
0xc3d8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class ScanHostWorkersThreadActivity>::.ctor(string, bool, bool)
0xc3dd  ret
```
