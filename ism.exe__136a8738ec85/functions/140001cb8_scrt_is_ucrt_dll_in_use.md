# __scrt_is_ucrt_dll_in_use

- ea: `0x140001cb8`
- end: `0x140001cc4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400014bc`
- `0x14000153c`
- `0x140001670`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001cb8  xor     eax, eax
0x140001cba  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001cc0  setnz   al
0x140001cc3  retn
```
