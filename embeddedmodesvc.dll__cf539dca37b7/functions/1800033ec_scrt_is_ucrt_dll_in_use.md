# __scrt_is_ucrt_dll_in_use

- ea: `0x1800033ec`
- end: `0x1800033f8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002b34`
- `0x180002b74`
- `0x180002c0c`
- `0x180002c5c`
- `0x180002cf0`
- `0x180002e24`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800033ec  xor     eax, eax
0x1800033ee  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800033f4  setnz   al
0x1800033f7  retn
```
