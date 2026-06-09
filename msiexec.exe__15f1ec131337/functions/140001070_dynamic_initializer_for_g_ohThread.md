# _dynamic_initializer_for__g_ohThread__

- ea: `0x140001070`
- end: `0x14000107c`
- name: `_dynamic_initializer_for__g_ohThread__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003570`

## pseudocode

```c
int dynamic_initializer_for__g_ohThread__()
{
  return atexit(dynamic_atexit_destructor_for__g_ohThread__);
}

```

## disassembly

```asm
0x140001070  lea     rcx, _dynamic_atexit_destructor_for__g_ohThread__
0x140001077  jmp     atexit
```
