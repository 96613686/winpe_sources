# operator delete(void *)

- ea: `0x180002726`
- end: `0x18000272c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001ee0`
- `0x180001f10`
- `0x180001f50`
- `0x180001f88`
- `0x180002088`
- `0x180002760`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002726`

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
0x180002726  jmp     cs:__imp_??3@YAXPEAX@Z
```
