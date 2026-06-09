# _dynamic_atexit_destructor_for__g_HypervisorSysConfigTimer__

- ea: `0x180009770`
- end: `0x18000977c`
- name: `_dynamic_atexit_destructor_for__g_HypervisorSysConfigTimer__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800082fc`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_HypervisorSysConfigTimer__()
{
  HvSysConfigTimer::~HvSysConfigTimer((HvSysConfigTimer *)&g_HypervisorSysConfigTimer);
}

```

## disassembly

```asm
0x180009770  lea     rcx, ?g_HypervisorSysConfigTimer@@3VHvSysConfigTimer@@A; this
0x180009777  jmp     ??1HvSysConfigTimer@@QEAA@XZ; HvSysConfigTimer::~HvSysConfigTimer(void)
```
