# __scrt_is_ucrt_dll_in_use

- ea: `0x18000c6c8`
- end: `0x18000c6d4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000be64`
- `0x18000bea4`
- `0x18000bf3c`
- `0x18000bf8c`
- `0x18000c020`
- `0x18000c154`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000c6c8  xor     eax, eax
0x18000c6ca  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000c6d0  setnz   al
0x18000c6d3  retn
```
