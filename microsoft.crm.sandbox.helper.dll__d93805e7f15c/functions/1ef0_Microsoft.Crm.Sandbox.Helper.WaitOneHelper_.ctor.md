# Microsoft.Crm.Sandbox.Helper.WaitOneHelper::.ctor

- ea: `0x1ef0`
- end: `0x1efe`
- name: `Microsoft.Crm.Sandbox.Helper.WaitOneHelper::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7b0`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  ldarg.0
0x1ef1  call     instance void [mscorlib]System.Object::.ctor()
0x1ef6  ldarg.0
0x1ef7  ldarg.1
0x1ef8  stfld    class [mscorlib]System.Threading.WaitHandle[] Microsoft.Crm.Sandbox.Helper.WaitOneHelper::_resetEvents
0x1efd  ret
```
