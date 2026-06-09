# __scrt_is_ucrt_dll_in_use

- ea: `0x180001bd0`
- end: `0x180001bdc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001548`
- `0x180001588`
- `0x180001620`
- `0x180001670`
- `0x180001704`
- `0x180001838`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001bd0  xor     eax, eax
0x180001bd2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001bd8  setnz   al
0x180001bdb  retn
```
