# __scrt_is_ucrt_dll_in_use

- ea: `0x140013cb0`
- end: `0x140013cbc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400134c8`
- `0x140013550`
- `0x140013674`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140013cb0  xor     eax, eax
0x140013cb2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140013cb8  setnz   al
0x140013cbb  retn
```
