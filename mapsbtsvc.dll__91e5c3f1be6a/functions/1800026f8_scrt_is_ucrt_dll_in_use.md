# __scrt_is_ucrt_dll_in_use

- ea: `0x1800026f8`
- end: `0x180002704`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ea0`
- `0x180001ee0`
- `0x180001f78`
- `0x180001fc8`
- `0x18000205c`
- `0x180002190`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800026f8  xor     eax, eax
0x1800026fa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002700  setnz   al
0x180002703  retn
```
