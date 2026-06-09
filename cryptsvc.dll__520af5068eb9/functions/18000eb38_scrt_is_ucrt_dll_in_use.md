# __scrt_is_ucrt_dll_in_use

- ea: `0x18000eb38`
- end: `0x18000eb44`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000e41c`
- `0x18000e45c`
- `0x18000e4f4`
- `0x18000e544`
- `0x18000e5d8`
- `0x18000e70c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000eb38  xor     eax, eax
0x18000eb3a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000eb40  setnz   al
0x18000eb43  retn
```
