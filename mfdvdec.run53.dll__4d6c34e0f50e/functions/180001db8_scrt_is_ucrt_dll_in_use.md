# __scrt_is_ucrt_dll_in_use

- ea: `0x180001db8`
- end: `0x180001dc4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016ac`
- `0x1800016ec`
- `0x180001784`
- `0x1800017d4`
- `0x180001868`
- `0x18000199c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001db8  xor     eax, eax
0x180001dba  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001dc0  setnz   al
0x180001dc3  retn
```
