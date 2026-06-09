# SandboxHostBackgroundThreadActivity::.ctor

- ea: `0xc3b0`
- end: `0xc3be`
- name: `SandboxHostBackgroundThreadActivity::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0xc3b1`: `SandboxHostBackgroundThread`

## pseudocode

```c

```

## disassembly

```asm
0xc3b0  ldarg.0
0xc3b1  ldstr    aSandboxhostbac// "SandboxHostBackgroundThread"
0xc3b6  ldc.i4.1
0xc3b7  ldc.i4.1
0xc3b8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class SandboxHostBackgroundThreadActivity>::.ctor(string, bool, bool)
0xc3bd  ret
```
