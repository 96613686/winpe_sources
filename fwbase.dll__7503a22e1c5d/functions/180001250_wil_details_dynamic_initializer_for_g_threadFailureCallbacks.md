# wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__

- ea: `0x180001250`
- end: `0x18000125c`
- name: `wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001e580`

## pseudocode

```c
int wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__()
{
  return atexit(wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__);
}

```

## disassembly

```asm
0x180001250  lea     rcx, wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks__
0x180001257  jmp     atexit
```
