# __scrt_is_ucrt_dll_in_use

- ea: `0x140001e14`
- end: `0x140001e20`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001524`
- `0x1400015a4`
- `0x1400016d8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001e14  xor     eax, eax
0x140001e16  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001e1c  setnz   al
0x140001e1f  retn
```
