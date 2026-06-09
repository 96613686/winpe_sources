# __scrt_is_ucrt_dll_in_use

- ea: `0x180005418`
- end: `0x180005424`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004d6c`
- `0x180004dac`
- `0x180004e44`
- `0x180004e94`
- `0x180004f28`
- `0x18000505c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005418  xor     eax, eax
0x18000541a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005420  setnz   al
0x180005423  retn
```
