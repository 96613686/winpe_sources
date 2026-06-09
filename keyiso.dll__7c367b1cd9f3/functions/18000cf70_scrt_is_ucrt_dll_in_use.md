# __scrt_is_ucrt_dll_in_use

- ea: `0x18000cf70`
- end: `0x18000cf7c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000c7f4`
- `0x18000c834`
- `0x18000c8cc`
- `0x18000c91c`
- `0x18000c9b0`
- `0x18000cae4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000cf70  xor     eax, eax
0x18000cf72  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000cf78  setnz   al
0x18000cf7b  retn
```
