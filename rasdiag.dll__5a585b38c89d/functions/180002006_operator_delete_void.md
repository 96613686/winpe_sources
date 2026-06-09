# operator delete(void *)

- ea: `0x180002006`
- end: `0x18000200c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001310`
- `0x180001340`
- `0x180001380`
- `0x1800013b8`
- `0x1800014b8`
- `0x180002110`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002006`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  __imp_??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180002006  jmp     cs:__imp_??3@YAXPEAX@Z
```
