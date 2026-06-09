# _dynamic_initializer_for__g_threadPoolManager__

- ea: `0x140001c20`
- end: `0x140001c2c`
- name: `_dynamic_initializer_for__g_threadPoolManager__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002380`

## pseudocode

```c
int dynamic_initializer_for__g_threadPoolManager__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_threadPoolManager__);
}

```

## disassembly

```asm
0x140001c20  lea     rcx, _dynamic_atexit_destructor_for__g_threadPoolManager__
0x140001c27  jmp     atexit
```
