# _dynamic_initializer_for__all_SCURIs__

- ea: `0x180001420`
- end: `0x18000142c`
- name: `_dynamic_initializer_for__all_SCURIs__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002024`

## pseudocode

```c
int dynamic_initializer_for__all_SCURIs__()
{
  return atexit(dynamic_atexit_destructor_for__all_SCURIs__);
}

```

## disassembly

```asm
0x180001420  lea     rcx, _dynamic_atexit_destructor_for__all_SCURIs__
0x180001427  jmp     atexit
```
