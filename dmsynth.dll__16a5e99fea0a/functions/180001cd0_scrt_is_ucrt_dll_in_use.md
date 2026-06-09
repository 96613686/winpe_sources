# __scrt_is_ucrt_dll_in_use

- ea: `0x180001cd0`
- end: `0x180001cdc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001648`
- `0x180001688`
- `0x180001720`
- `0x180001770`
- `0x180001804`
- `0x180001938`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001cd0  xor     eax, eax
0x180001cd2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001cd8  setnz   al
0x180001cdb  retn
```
