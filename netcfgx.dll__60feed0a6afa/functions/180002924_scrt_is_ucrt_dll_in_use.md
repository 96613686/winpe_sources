# __scrt_is_ucrt_dll_in_use

- ea: `0x180002924`
- end: `0x180002930`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002020`
- `0x180002060`
- `0x1800020f8`
- `0x180002148`
- `0x1800021dc`
- `0x180002310`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002924  xor     eax, eax
0x180002926  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000292c  setnz   al
0x18000292f  retn
```
