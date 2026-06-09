# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c98`
- end: `0x180001ca4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001484`
- `0x1800014c4`
- `0x18000155c`
- `0x1800015ac`
- `0x180001640`
- `0x180001774`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c98  xor     eax, eax
0x180001c9a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001ca0  setnz   al
0x180001ca3  retn
```
