# __scrt_is_ucrt_dll_in_use

- ea: `0x180009ae8`
- end: `0x180009af4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000943c`
- `0x18000947c`
- `0x180009514`
- `0x180009564`
- `0x1800095f8`
- `0x18000972c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180009ae8  xor     eax, eax
0x180009aea  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180009af0  setnz   al
0x180009af3  retn
```
