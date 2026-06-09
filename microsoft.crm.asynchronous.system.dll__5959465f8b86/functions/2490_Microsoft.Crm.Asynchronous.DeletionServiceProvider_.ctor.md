# Microsoft.Crm.Asynchronous.DeletionServiceProvider::.ctor

- ea: `0x2490`
- end: `0x249e`
- name: `Microsoft.Crm.Asynchronous.DeletionServiceProvider::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2430`

## pseudocode

```c

```

## disassembly

```asm
0x2490  ldarg.0
0x2491  call     instance void [mscorlib]System.Object::.ctor()
0x2496  ldarg.0
0x2497  ldarg.1
0x2498  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.DeletionServiceProvider::_asyncEvent
0x249d  ret
```
