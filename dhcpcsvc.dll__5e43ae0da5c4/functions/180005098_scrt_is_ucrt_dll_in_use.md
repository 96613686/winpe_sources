# __scrt_is_ucrt_dll_in_use

- ea: `0x180005098`
- end: `0x1800050a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800049ec`
- `0x180004a2c`
- `0x180004ac4`
- `0x180004b14`
- `0x180004ba8`
- `0x180004cdc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005098  xor     eax, eax
0x18000509a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800050a0  setnz   al
0x1800050a3  retn
```
