# __scrt_is_ucrt_dll_in_use

- ea: `0x180002aa8`
- end: `0x180002ab4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002294`
- `0x1800022d4`
- `0x18000236c`
- `0x1800023bc`
- `0x180002450`
- `0x180002584`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002aa8  xor     eax, eax
0x180002aaa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002ab0  setnz   al
0x180002ab3  retn
```
