# operator delete(void *)

- ea: `0x1400026d9`
- end: `0x1400026df`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140002190`
- `0x1400021d0`
- `0x140002730`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400026d9`

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
0x1400026d9  jmp     cs:__imp_??3@YAXPEAX@Z
```
