# __scrt_is_ucrt_dll_in_use

- ea: `0x1800025f4`
- end: `0x180002600`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001c7c`
- `0x180001cbc`
- `0x180001d54`
- `0x180001da4`
- `0x180001e38`
- `0x180001f6c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800025f4  xor     eax, eax
0x1800025f6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800025fc  setnz   al
0x1800025ff  retn
```
