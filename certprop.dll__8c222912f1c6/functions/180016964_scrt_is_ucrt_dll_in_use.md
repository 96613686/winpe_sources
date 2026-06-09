# __scrt_is_ucrt_dll_in_use

- ea: `0x180016964`
- end: `0x180016970`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180016254`
- `0x180016294`
- `0x18001632c`
- `0x18001637c`
- `0x180016410`
- `0x180016544`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180016964  xor     eax, eax
0x180016966  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001696c  setnz   al
0x18001696f  retn
```
