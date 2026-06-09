# __scrt_is_ucrt_dll_in_use

- ea: `0x140001b54`
- end: `0x140001b60`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001390`
- `0x140001410`
- `0x140001544`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001b54  xor     eax, eax
0x140001b56  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001b5c  setnz   al
0x140001b5f  retn
```
