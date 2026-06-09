# _dynamic_initializer_for__g_szCommandLine__

- ea: `0x140001090`
- end: `0x14000109c`
- name: `_dynamic_initializer_for__g_szCommandLine__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003570`

## pseudocode

```c
int dynamic_initializer_for__g_szCommandLine__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_szCommandLine__);
}

```

## disassembly

```asm
0x140001090  lea     rcx, _dynamic_atexit_destructor_for__g_szCommandLine__
0x140001097  jmp     atexit
```
