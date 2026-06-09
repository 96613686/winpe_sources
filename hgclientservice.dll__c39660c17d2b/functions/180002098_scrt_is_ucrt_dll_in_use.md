# __scrt_is_ucrt_dll_in_use

- ea: `0x180002098`
- end: `0x1800020a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800017fc`
- `0x18000183c`
- `0x1800018d4`
- `0x180001924`
- `0x1800019b8`
- `0x180001aec`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002098  xor     eax, eax
0x18000209a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800020a0  setnz   al
0x1800020a3  retn
```
