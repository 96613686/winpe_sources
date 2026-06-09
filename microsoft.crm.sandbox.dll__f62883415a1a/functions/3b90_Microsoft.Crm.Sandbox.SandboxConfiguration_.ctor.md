# Microsoft.Crm.Sandbox.SandboxConfiguration::.ctor

- ea: `0x3b90`
- end: `0x3ba2`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::.ctor`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe20`
- `0x5630`
- `0x8180`

## pseudocode

```c

```

## disassembly

```asm
0x3b90  ldarg.0
0x3b91  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::.ctor()
0x3b96  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3b9b  ldarg.0
0x3b9c  call     instance void [mscorlib]System.Object::.ctor()
0x3ba1  ret
```
