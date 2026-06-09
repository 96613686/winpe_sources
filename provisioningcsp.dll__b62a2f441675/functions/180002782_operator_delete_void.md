# operator delete(void *)

- ea: `0x180002782`
- end: `0x180002788`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800030b0`
- `0x180037910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002782`

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
0x180002782  jmp     cs:__imp_??3@YAXPEAX@Z
```
