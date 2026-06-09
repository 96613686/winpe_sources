# __scrt_is_ucrt_dll_in_use

- ea: `0x1800025b8`
- end: `0x1800025c4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d30`
- `0x180001d70`
- `0x180001e08`
- `0x180001e58`
- `0x180001eec`
- `0x180002020`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800025b8  xor     eax, eax
0x1800025ba  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800025c0  setnz   al
0x1800025c3  retn
```
