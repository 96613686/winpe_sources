# __scrt_is_ucrt_dll_in_use

- ea: `0x180024a68`
- end: `0x180024a74`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180024244`
- `0x180024284`
- `0x18002431c`
- `0x18002436c`
- `0x180024400`
- `0x180024534`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180024a68  xor     eax, eax
0x180024a6a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180024a70  setnz   al
0x180024a73  retn
```
