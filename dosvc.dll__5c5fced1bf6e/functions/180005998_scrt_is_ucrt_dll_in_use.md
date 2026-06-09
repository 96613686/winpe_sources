# __scrt_is_ucrt_dll_in_use

- ea: `0x180005998`
- end: `0x1800059a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005044`
- `0x180005084`
- `0x18000511c`
- `0x18000516c`
- `0x180005200`
- `0x180005334`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005998  xor     eax, eax
0x18000599a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800059a0  setnz   al
0x1800059a3  retn
```
