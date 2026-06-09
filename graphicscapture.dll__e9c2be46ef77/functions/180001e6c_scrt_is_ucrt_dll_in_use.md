# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e6c`
- end: `0x180001e78`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000176c`
- `0x1800017ac`
- `0x180001844`
- `0x180001894`
- `0x180001928`
- `0x180001a5c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e6c  xor     eax, eax
0x180001e6e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e74  setnz   al
0x180001e77  retn
```
