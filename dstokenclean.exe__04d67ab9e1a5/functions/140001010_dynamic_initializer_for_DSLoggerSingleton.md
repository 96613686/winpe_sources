# _dynamic_initializer_for__DSLoggerSingleton__

- ea: `0x140001010`
- end: `0x14000101c`
- name: `_dynamic_initializer_for__DSLoggerSingleton__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400016dc`

## pseudocode

```c
int dynamic_initializer_for__DSLoggerSingleton__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__DSLoggerSingleton__);
}

```

## disassembly

```asm
0x140001010  lea     rcx, _dynamic_atexit_destructor_for__DSLoggerSingleton__
0x140001017  jmp     atexit
```
