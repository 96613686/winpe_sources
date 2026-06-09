# _dynamic_initializer_for__vhWdsDll__

- ea: `0x140001f30`
- end: `0x140001f3c`
- name: `_dynamic_initializer_for__vhWdsDll__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025d4`

## pseudocode

```c
int dynamic_initializer_for__vhWdsDll__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__vhWdsDll__);
}

```

## disassembly

```asm
0x140001f30  lea     rcx, _dynamic_atexit_destructor_for__vhWdsDll__
0x140001f37  jmp     atexit
```
