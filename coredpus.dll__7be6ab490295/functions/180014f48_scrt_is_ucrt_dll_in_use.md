# __scrt_is_ucrt_dll_in_use

- ea: `0x180014f48`
- end: `0x180014f54`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800147f8`
- `0x180014838`
- `0x1800148d0`
- `0x180014920`
- `0x1800149b4`
- `0x180014ae8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180014f48  xor     eax, eax
0x180014f4a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180014f50  setnz   al
0x180014f53  retn
```
