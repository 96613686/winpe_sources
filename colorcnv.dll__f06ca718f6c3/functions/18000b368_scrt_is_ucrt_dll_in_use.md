# __scrt_is_ucrt_dll_in_use

- ea: `0x18000b368`
- end: `0x18000b374`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000ab54`
- `0x18000ab94`
- `0x18000ac2c`
- `0x18000ac7c`
- `0x18000ad10`
- `0x18000ae44`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000b368  xor     eax, eax
0x18000b36a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000b370  setnz   al
0x18000b373  retn
```
