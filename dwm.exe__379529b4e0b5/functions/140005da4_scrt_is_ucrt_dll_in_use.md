# __scrt_is_ucrt_dll_in_use

- ea: `0x140005da4`
- end: `0x140005db0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140005554`
- `0x1400055d4`
- `0x140005708`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140005da4  xor     eax, eax
0x140005da6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140005dac  setnz   al
0x140005daf  retn
```
