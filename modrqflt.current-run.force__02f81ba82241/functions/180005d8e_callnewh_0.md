# _callnewh_0

- ea: `0x180005d8e`
- end: `0x180005d94`
- name: `_callnewh_0`
- size: `6`
- prototype: `int __cdecl(size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005860`

## import_xrefs

- `msvcrt!_callnewh` at `0x180005d8e`

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
0x180005d8e  jmp     cs:__imp__callnewh
```
