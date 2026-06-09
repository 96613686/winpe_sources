# __scrt_is_ucrt_dll_in_use

- ea: `0x18000241c`
- end: `0x180002428`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001c98`
- `0x180001cd8`
- `0x180001d70`
- `0x180001dc0`
- `0x180001e54`
- `0x180001f88`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000241c  xor     eax, eax
0x18000241e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002424  setnz   al
0x180002427  retn
```
