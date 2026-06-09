# operator delete(void *)

- ea: `0x1400026f9`
- end: `0x1400026ff`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1400021b0`
- `0x1400021f0`
- `0x140002750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400026f9`

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
0x1400026f9  jmp     cs:__imp_??3@YAXPEAX@Z
```
