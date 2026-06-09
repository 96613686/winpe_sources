# operator delete(void *)

- ea: `0x180001ebd`
- end: `0x180001ec3`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800014a0`
- `0x1800014e0`
- `0x180001f70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001ebd`

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
0x180001ebd  jmp     cs:__imp_??3@YAXPEAX@Z
```
