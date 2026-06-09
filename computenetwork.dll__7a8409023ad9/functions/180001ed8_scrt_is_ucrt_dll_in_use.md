# __scrt_is_ucrt_dll_in_use

- ea: `0x180001ed8`
- end: `0x180001ee4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001624`
- `0x180001664`
- `0x1800016fc`
- `0x18000174c`
- `0x1800017e0`
- `0x180001914`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001ed8  xor     eax, eax
0x180001eda  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001ee0  setnz   al
0x180001ee3  retn
```
