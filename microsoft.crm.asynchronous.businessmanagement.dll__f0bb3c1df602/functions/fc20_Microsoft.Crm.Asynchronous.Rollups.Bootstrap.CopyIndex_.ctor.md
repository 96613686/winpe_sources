# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.CopyIndex::.ctor

- ea: `0xfc20`
- end: `0xfc38`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.CopyIndex::.ctor`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xfe20`

## callees

- `0xfc80`
- `0x100c0`
- `0x100f0`

## pseudocode

```c

```

## disassembly

```asm
0xfc20  ldarg.0
0xfc21  ldarg.2
0xfc22  ldarg.s  4
0xfc24  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::.ctor(int32 stepNumber, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0xfc29  ldarg.0
0xfc2a  ldarg.1
0xfc2b  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::set_Process(class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation value)
0xfc30  ldarg.0
0xfc31  ldarg.3
0xfc32  call     instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.CopyIndex::set_CopyType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.IndexCopyType value)
0xfc37  ret
```
