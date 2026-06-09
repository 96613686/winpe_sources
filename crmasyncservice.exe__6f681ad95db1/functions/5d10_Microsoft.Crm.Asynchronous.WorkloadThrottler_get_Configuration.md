# Microsoft.Crm.Asynchronous.WorkloadThrottler::get_Configuration

- ea: `0x5d10`
- end: `0x5d17`
- name: `Microsoft.Crm.Asynchronous.WorkloadThrottler::get_Configuration`
- size: `7`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x53c0`
- `0x54c0`
- `0x5710`
- `0x57f0`
- `0x5bd0`
- `0x5e00`
- `0x5ed0`
- `0x5fa0`
- `0x60e0`
- `0x6150`
- `0x62c0`

## pseudocode

```c

```

## disassembly

```asm
0x5d10  ldarg.0
0x5d11  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration Microsoft.Crm.Asynchronous.WorkloadThrottler::<Configuration>k__BackingField
0x5d16  ret
```
