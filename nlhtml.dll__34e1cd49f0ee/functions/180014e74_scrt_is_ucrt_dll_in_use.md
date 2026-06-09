# __scrt_is_ucrt_dll_in_use

- ea: `0x180014e74`
- end: `0x180014e80`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180014198`
- `0x1800141d8`
- `0x180014270`
- `0x1800142c0`
- `0x180014354`
- `0x180014488`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180014e74  xor     eax, eax
0x180014e76  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180014e7c  setnz   al
0x180014e7f  retn
```
