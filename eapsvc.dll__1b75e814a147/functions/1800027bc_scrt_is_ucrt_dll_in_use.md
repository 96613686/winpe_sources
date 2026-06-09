# __scrt_is_ucrt_dll_in_use

- ea: `0x1800027bc`
- end: `0x1800027c8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f84`
- `0x180001fc4`
- `0x18000205c`
- `0x1800020ac`
- `0x180002140`
- `0x180002274`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800027bc  xor     eax, eax
0x1800027be  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800027c4  setnz   al
0x1800027c7  retn
```
