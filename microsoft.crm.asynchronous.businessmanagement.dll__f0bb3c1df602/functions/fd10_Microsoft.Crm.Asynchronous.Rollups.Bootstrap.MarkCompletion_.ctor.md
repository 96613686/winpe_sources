# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::.ctor

- ea: `0xfd10`
- end: `0xfd20`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::.ctor`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xfe20`

## callees

- `0x100c0`
- `0x100f0`

## pseudocode

```c

```

## disassembly

```asm
0xfd10  ldarg.0
0xfd11  ldarg.2
0xfd12  ldarg.3
0xfd13  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::.ctor(int32 stepNumber, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0xfd18  ldarg.0
0xfd19  ldarg.1
0xfd1a  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::set_Process(class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation value)
0xfd1f  ret
```
