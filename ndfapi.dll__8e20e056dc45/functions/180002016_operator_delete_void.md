# operator delete(void *)

- ea: `0x180002016`
- end: `0x18000201c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001a50`
- `0x180001a90`
- `0x180002140`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002016`

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
0x180002016  jmp     cs:__imp_??3@YAXPEAX@Z
```
