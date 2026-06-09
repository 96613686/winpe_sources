# _callnewh_0

- ea: `0x1800019be`
- end: `0x1800019c4`
- name: `_callnewh_0`
- size: `6`
- prototype: `int __cdecl(size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001490`

## import_xrefs

- `msvcrt!_callnewh` at `0x1800019be`

## pseudocode

```c
// attributes: thunk
int __cdecl callnewh_0(size_t Size)
{
  return _callnewh(Size);
}

```

## disassembly

```asm
0x1800019be  jmp     cs:__imp__callnewh
```
