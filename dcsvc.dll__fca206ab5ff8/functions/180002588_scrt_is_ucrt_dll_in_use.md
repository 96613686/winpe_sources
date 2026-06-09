# __scrt_is_ucrt_dll_in_use

- ea: `0x180002588`
- end: `0x180002594`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d4c`
- `0x180001d8c`
- `0x180001e24`
- `0x180001e74`
- `0x180001f08`
- `0x18000203c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002588  xor     eax, eax
0x18000258a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002590  setnz   al
0x180002593  retn
```
