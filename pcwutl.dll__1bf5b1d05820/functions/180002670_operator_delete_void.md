# operator delete(void *)

- ea: `0x180002670`
- end: `0x180002676`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001650`
- `0x180001680`
- `0x1800016c0`
- `0x1800016f8`
- `0x1800017f8`
- `0x1800027f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002670`

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
0x180002670  jmp     cs:__imp_??3@YAXPEAX@Z
```
