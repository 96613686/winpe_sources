# __scrt_is_ucrt_dll_in_use

- ea: `0x180002084`
- end: `0x180002090`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016f4`
- `0x180001734`
- `0x1800017cc`
- `0x18000181c`
- `0x1800018b0`
- `0x1800019e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002084  xor     eax, eax
0x180002086  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000208c  setnz   al
0x18000208f  retn
```
