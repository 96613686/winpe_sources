# __scrt_is_ucrt_dll_in_use

- ea: `0x18000355c`
- end: `0x180003568`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002cf8`
- `0x180002d38`
- `0x180002dd0`
- `0x180002e20`
- `0x180002eb4`
- `0x180002fe8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000355c  xor     eax, eax
0x18000355e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003564  setnz   al
0x180003567  retn
```
