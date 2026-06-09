# __scrt_is_ucrt_dll_in_use

- ea: `0x1400031e4`
- end: `0x1400031f0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400029fc`
- `0x140002a7c`
- `0x140002bb0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400031e4  xor     eax, eax
0x1400031e6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400031ec  setnz   al
0x1400031ef  retn
```
