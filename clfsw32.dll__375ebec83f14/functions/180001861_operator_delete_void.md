# operator delete(void *)

- ea: `0x180001861`
- end: `0x180001867`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001e20`
- `0x180001e50`
- `0x180001e90`
- `0x180001ec8`
- `0x180001fc8`
- `0x1800026e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001861`

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
0x180001861  jmp     cs:__imp_??3@YAXPEAX@Z
```
