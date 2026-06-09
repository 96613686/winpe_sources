# __scrt_is_ucrt_dll_in_use

- ea: `0x180002278`
- end: `0x180002284`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001bcc`
- `0x180001c0c`
- `0x180001ca4`
- `0x180001cf4`
- `0x180001d88`
- `0x180001ebc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002278  xor     eax, eax
0x18000227a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002280  setnz   al
0x180002283  retn
```
