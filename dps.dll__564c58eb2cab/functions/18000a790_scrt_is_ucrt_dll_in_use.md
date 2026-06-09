# __scrt_is_ucrt_dll_in_use

- ea: `0x18000a790`
- end: `0x18000a79c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000a108`
- `0x18000a148`
- `0x18000a1e0`
- `0x18000a230`
- `0x18000a2c4`
- `0x18000a3f8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000a790  xor     eax, eax
0x18000a792  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000a798  setnz   al
0x18000a79b  retn
```
