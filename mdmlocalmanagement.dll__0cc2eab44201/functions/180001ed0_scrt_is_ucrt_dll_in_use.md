# __scrt_is_ucrt_dll_in_use

- ea: `0x180001ed0`
- end: `0x180001edc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001684`
- `0x1800016c4`
- `0x18000175c`
- `0x1800017ac`
- `0x180001840`
- `0x180001974`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001ed0  xor     eax, eax
0x180001ed2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001ed8  setnz   al
0x180001edb  retn
```
