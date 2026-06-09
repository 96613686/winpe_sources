# __scrt_is_ucrt_dll_in_use

- ea: `0x1400038cc`
- end: `0x1400038d8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002fa8`
- `0x140003028`
- `0x14000315c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400038cc  xor     eax, eax
0x1400038ce  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400038d4  setnz   al
0x1400038d7  retn
```
