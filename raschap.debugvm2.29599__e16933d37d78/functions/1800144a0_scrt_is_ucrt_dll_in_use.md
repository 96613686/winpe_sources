# __scrt_is_ucrt_dll_in_use

- ea: `0x1800144a0`
- end: `0x1800144ac`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180013bdc`
- `0x180013c1c`
- `0x180013cb4`
- `0x180013d04`
- `0x180013d98`
- `0x180013ecc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800144a0  xor     eax, eax
0x1800144a2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800144a8  setnz   al
0x1800144ab  retn
```
