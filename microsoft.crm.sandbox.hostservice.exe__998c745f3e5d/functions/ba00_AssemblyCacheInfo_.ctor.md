# AssemblyCacheInfo::.ctor

- ea: `0xba00`
- end: `0xba15`
- name: `AssemblyCacheInfo::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x2c00`

## pseudocode

```c

```

## disassembly

```asm
0xba00  ldarg.0
0xba01  call     instance void [mscorlib]System.Object::.ctor()
0xba06  ldarg.0
0xba07  ldarg.1
0xba08  stfld    string AssemblyCacheInfo::_assemblyFileName
0xba0d  ldarg.0
0xba0e  ldarg.2
0xba0f  stfld    int64 AssemblyCacheInfo::_assemblySize
0xba14  ret
```
