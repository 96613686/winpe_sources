# __scrt_is_ucrt_dll_in_use

- ea: `0x18001a310`
- end: `0x18001a31c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180019c28`
- `0x180019c68`
- `0x180019d00`
- `0x180019d50`
- `0x180019de4`
- `0x180019f18`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18001a310  xor     eax, eax
0x18001a312  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001a318  setnz   al
0x18001a31b  retn
```
