# __scrt_is_ucrt_dll_in_use

- ea: `0x140002b9c`
- end: `0x140002ba8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002384`
- `0x140002404`
- `0x140002538`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002b9c  xor     eax, eax
0x140002b9e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002ba4  setnz   al
0x140002ba7  retn
```
