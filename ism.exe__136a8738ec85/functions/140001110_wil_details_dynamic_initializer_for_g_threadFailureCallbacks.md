# wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__

- ea: `0x140001110`
- end: `0x14000111c`
- name: `wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000170c`

## pseudocode

```c
int wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__()
{
  return atexit((void (__cdecl *)())wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__);
}

```

## disassembly

```asm
0x140001110  lea     rcx, wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks__
0x140001117  jmp     atexit
```
