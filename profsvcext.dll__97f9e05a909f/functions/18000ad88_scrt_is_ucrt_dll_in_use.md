# __scrt_is_ucrt_dll_in_use

- ea: `0x18000ad88`
- end: `0x18000ad94`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000a544`
- `0x18000a584`
- `0x18000a61c`
- `0x18000a66c`
- `0x18000a700`
- `0x18000a834`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000ad88  xor     eax, eax
0x18000ad8a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000ad90  setnz   al
0x18000ad93  retn
```
