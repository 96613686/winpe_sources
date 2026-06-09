# __scrt_is_ucrt_dll_in_use

- ea: `0x180006cd8`
- end: `0x180006ce4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006448`
- `0x180006488`
- `0x180006520`
- `0x180006570`
- `0x180006604`
- `0x180006738`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180006cd8  xor     eax, eax
0x180006cda  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180006ce0  setnz   al
0x180006ce3  retn
```
