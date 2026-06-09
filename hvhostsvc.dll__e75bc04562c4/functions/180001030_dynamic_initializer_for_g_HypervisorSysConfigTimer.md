# _dynamic_initializer_for__g_HypervisorSysConfigTimer__

- ea: `0x180001030`
- end: `0x18000103c`
- name: `_dynamic_initializer_for__g_HypervisorSysConfigTimer__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800024b0`

## pseudocode

```c
int dynamic_initializer_for__g_HypervisorSysConfigTimer__()
{
  return atexit(dynamic_atexit_destructor_for__g_HypervisorSysConfigTimer__);
}

```

## disassembly

```asm
0x180001030  lea     rcx, _dynamic_atexit_destructor_for__g_HypervisorSysConfigTimer__
0x180001037  jmp     atexit
```
