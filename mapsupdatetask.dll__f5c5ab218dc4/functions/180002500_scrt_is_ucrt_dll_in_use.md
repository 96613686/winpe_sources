# __scrt_is_ucrt_dll_in_use

- ea: `0x180002500`
- end: `0x18000250c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001c48`
- `0x180001c88`
- `0x180001d20`
- `0x180001d70`
- `0x180001e04`
- `0x180001f38`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002500  xor     eax, eax
0x180002502  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002508  setnz   al
0x18000250b  retn
```
