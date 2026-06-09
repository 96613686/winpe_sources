# _callnewh_0

- ea: `0x180002ba5`
- end: `0x180002bab`
- name: `_callnewh_0`
- size: `6`
- prototype: `int __cdecl(size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025b0`

## import_xrefs

- `msvcrt!_callnewh` at `0x180002ba5`

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
0x180002ba5  jmp     cs:__imp__callnewh
```
