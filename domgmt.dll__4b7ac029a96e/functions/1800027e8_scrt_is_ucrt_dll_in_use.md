# __scrt_is_ucrt_dll_in_use

- ea: `0x1800027e8`
- end: `0x1800027f4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001bc4`
- `0x180001c04`
- `0x180001c9c`
- `0x180001cec`
- `0x180001d80`
- `0x180001eb4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800027e8  xor     eax, eax
0x1800027ea  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800027f0  setnz   al
0x1800027f3  retn
```
