# WelcomeMessage::.ctor_1

- ea: `0x650`
- end: `0x66c`
- name: `WelcomeMessage::.ctor_1`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x630`

## pseudocode

```c

```

## disassembly

```asm
0x650  ldarg.0
0x651  call     instance void [mscorlib]System.Object::.ctor()
0x656  ldarg.0
0x657  ldarg.1
0x658  stfld    string WelcomeMessage::<Title>k__BackingField
0x65d  ldarg.0
0x65e  ldarg.2
0x65f  stfld    string WelcomeMessage::<Version>k__BackingField
0x664  ldarg.0
0x665  ldarg.3
0x666  stfld    string WelcomeMessage::<Revision>k__BackingField
0x66b  ret
```
