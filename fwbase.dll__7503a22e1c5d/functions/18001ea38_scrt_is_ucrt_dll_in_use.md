# __scrt_is_ucrt_dll_in_use

- ea: `0x18001ea38`
- end: `0x18001ea44`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001e1f4`
- `0x18001e234`
- `0x18001e2cc`
- `0x18001e31c`
- `0x18001e3b0`
- `0x18001e4e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18001ea38  xor     eax, eax
0x18001ea3a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001ea40  setnz   al
0x18001ea43  retn
```
