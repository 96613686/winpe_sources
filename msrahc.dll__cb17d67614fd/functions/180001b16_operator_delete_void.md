# operator delete[](void *)

- ea: `0x180001b16`
- end: `0x180001b1c`
- name: `??_V@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800020c0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180001b16`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *a1)
{
  __imp_??_V@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180001b16  jmp     cs:__imp_??_V@YAXPEAX@Z
```
