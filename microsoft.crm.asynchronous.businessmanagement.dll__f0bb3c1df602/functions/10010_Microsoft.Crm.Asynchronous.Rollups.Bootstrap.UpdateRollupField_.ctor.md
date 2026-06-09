# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::.ctor

- ea: `0x10010`
- end: `0x10020`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::.ctor`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

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
0x10010  ldarg.0
0x10011  ldarg.2
0x10012  ldarg.3
0x10013  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::.ctor(int32 stepNumber, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0x10018  ldarg.0
0x10019  ldarg.1
0x1001a  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::set_Process(class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation value)
0x1001f  ret
```
