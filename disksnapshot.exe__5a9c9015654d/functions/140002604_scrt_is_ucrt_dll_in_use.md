# __scrt_is_ucrt_dll_in_use

- ea: `0x140002604`
- end: `0x140002610`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002060`
- `0x1400020e0`
- `0x140002214`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002604  xor     eax, eax
0x140002606  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14000260c  setnz   al
0x14000260f  retn
```
