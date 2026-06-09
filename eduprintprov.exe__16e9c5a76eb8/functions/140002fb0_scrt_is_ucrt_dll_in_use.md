# __scrt_is_ucrt_dll_in_use

- ea: `0x140002fb0`
- end: `0x140002fbc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002674`
- `0x1400026f4`
- `0x140002828`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002fb0  xor     eax, eax
0x140002fb2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002fb8  setnz   al
0x140002fbb  retn
```
