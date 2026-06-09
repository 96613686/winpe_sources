# _dynamic_initializer_for__s_configuration__

- ea: `0x1800012a0`
- end: `0x1800012ac`
- name: `_dynamic_initializer_for__s_configuration__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001b88`

## pseudocode

```c
int dynamic_initializer_for__s_configuration__()
{
  return atexit(dynamic_atexit_destructor_for__s_configuration__);
}

```

## disassembly

```asm
0x1800012a0  lea     rcx, _dynamic_atexit_destructor_for__s_configuration__
0x1800012a7  jmp     atexit
```
