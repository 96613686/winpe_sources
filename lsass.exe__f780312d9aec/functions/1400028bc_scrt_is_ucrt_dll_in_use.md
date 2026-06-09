# __scrt_is_ucrt_dll_in_use

- ea: `0x1400028bc`
- end: `0x1400028c8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400020e4`
- `0x140002164`
- `0x140002298`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400028bc  xor     eax, eax
0x1400028be  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400028c4  setnz   al
0x1400028c7  retn
```
