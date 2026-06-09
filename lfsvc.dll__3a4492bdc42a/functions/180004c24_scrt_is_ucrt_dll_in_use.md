# __scrt_is_ucrt_dll_in_use

- ea: `0x180004c24`
- end: `0x180004c30`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004378`
- `0x1800043b8`
- `0x180004450`
- `0x1800044a0`
- `0x180004534`
- `0x180004668`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004c24  xor     eax, eax
0x180004c26  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004c2c  setnz   al
0x180004c2f  retn
```
