# __scrt_is_ucrt_dll_in_use

- ea: `0x18000db1c`
- end: `0x18000db28`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d0c4`
- `0x18000d104`
- `0x18000d19c`
- `0x18000d1ec`
- `0x18000d280`
- `0x18000d3b4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000db1c  xor     eax, eax
0x18000db1e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000db24  setnz   al
0x18000db27  retn
```
