# __scrt_is_ucrt_dll_in_use

- ea: `0x18000279c`
- end: `0x1800027a8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f50`
- `0x180001f90`
- `0x180002028`
- `0x180002078`
- `0x18000210c`
- `0x180002240`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000279c  xor     eax, eax
0x18000279e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800027a4  setnz   al
0x1800027a7  retn
```
