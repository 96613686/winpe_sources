# Microsoft.Crm.Sandbox.SandboxTracingService::.ctor

- ea: `0x1de0`
- end: `0x1df3`
- name: `Microsoft.Crm.Sandbox.SandboxTracingService::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ba0`

## pseudocode

```c

```

## disassembly

```asm
0x1de0  ldarg.0
0x1de1  call     instance void [mscorlib]System.Object::.ctor()
0x1de6  ldarg.0
0x1de7  ldnull
0x1de8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1ded  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1df2  ret
```
