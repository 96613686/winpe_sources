# __scrt_is_ucrt_dll_in_use

- ea: `0x180002538`
- end: `0x180002544`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e38`
- `0x180001e78`
- `0x180001f10`
- `0x180001f60`
- `0x180001ff4`
- `0x180002128`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002538  xor     eax, eax
0x18000253a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002540  setnz   al
0x180002543  retn
```
