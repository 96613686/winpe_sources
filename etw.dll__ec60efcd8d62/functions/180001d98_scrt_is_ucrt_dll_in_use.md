# __scrt_is_ucrt_dll_in_use

- ea: `0x180001d98`
- end: `0x180001da4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000168c`
- `0x1800016cc`
- `0x180001764`
- `0x1800017b4`
- `0x180001848`
- `0x18000197c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001d98  xor     eax, eax
0x180001d9a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001da0  setnz   al
0x180001da3  retn
```
