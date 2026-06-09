# operator delete(void *)

- ea: `0x180001a15`
- end: `0x180001a1b`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800011c0`
- `0x180001200`
- `0x180001a60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001a15`

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
0x180001a15  jmp     cs:__imp_??3@YAXPEAX@Z
```
