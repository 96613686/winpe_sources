# __scrt_is_ucrt_dll_in_use

- ea: `0x180001d48`
- end: `0x180001d54`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000163c`
- `0x18000167c`
- `0x180001714`
- `0x180001764`
- `0x1800017f8`
- `0x18000192c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001d48  xor     eax, eax
0x180001d4a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001d50  setnz   al
0x180001d53  retn
```
