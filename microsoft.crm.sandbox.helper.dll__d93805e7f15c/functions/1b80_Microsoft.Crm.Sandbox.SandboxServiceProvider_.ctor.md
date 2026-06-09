# Microsoft.Crm.Sandbox.SandboxServiceProvider::.ctor

- ea: `0x1b80`
- end: `0x1b92`
- name: `Microsoft.Crm.Sandbox.SandboxServiceProvider::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1b80  ldarg.0
0x1b81  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::.ctor()
0x1b86  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxServiceProvider::_serviceProviderLookUp
0x1b8b  ldarg.0
0x1b8c  call     instance void [mscorlib]System.Object::.ctor()
0x1b91  ret
```
