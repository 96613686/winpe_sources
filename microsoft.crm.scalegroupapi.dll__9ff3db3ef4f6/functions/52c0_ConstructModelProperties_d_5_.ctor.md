# <ConstructModelProperties>d__5::.ctor

- ea: `0x52c0`
- end: `0x52d9`
- name: `<ConstructModelProperties>d__5::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3700`
- `0x5430`

## pseudocode

```c

```

## disassembly

```asm
0x52c0  ldarg.0
0x52c1  call     instance void [mscorlib]System.Object::.ctor()
0x52c6  ldarg.0
0x52c7  ldarg.1
0x52c8  stfld    int32 <ConstructModelProperties>d__5::<>1__state
0x52cd  ldarg.0
0x52ce  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x52d3  stfld    int32 <ConstructModelProperties>d__5::<>l__initialThreadId
0x52d8  ret
```
