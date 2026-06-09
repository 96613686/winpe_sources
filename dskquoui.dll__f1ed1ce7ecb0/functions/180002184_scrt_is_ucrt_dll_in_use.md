# __scrt_is_ucrt_dll_in_use

- ea: `0x180002184`
- end: `0x180002190`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001610`
- `0x180001650`
- `0x1800016e8`
- `0x180001738`
- `0x1800017cc`
- `0x180001900`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002184  xor     eax, eax
0x180002186  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000218c  setnz   al
0x18000218f  retn
```
