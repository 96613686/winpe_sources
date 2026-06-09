# __scrt_is_ucrt_dll_in_use

- ea: `0x180007ab8`
- end: `0x180007ac4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000740c`
- `0x18000744c`
- `0x1800074e4`
- `0x180007534`
- `0x1800075c8`
- `0x1800076fc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180007ab8  xor     eax, eax
0x180007aba  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180007ac0  setnz   al
0x180007ac3  retn
```
