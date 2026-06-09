# __scrt_is_ucrt_dll_in_use

- ea: `0x1800018a0`
- end: `0x1800018ac`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800011b4`
- `0x1800011f4`
- `0x18000128c`
- `0x1800012dc`
- `0x180001370`
- `0x1800014a4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800018a0  xor     eax, eax
0x1800018a2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800018a8  setnz   al
0x1800018ab  retn
```
