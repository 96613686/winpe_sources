# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c90`
- end: `0x180001c9c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001608`
- `0x180001648`
- `0x1800016e0`
- `0x180001730`
- `0x1800017c4`
- `0x1800018f8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c90  xor     eax, eax
0x180001c92  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c98  setnz   al
0x180001c9b  retn
```
