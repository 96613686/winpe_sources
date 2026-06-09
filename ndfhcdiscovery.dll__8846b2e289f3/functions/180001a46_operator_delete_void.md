# operator delete(void *)

- ea: `0x180001a46`
- end: `0x180001a4c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001410`
- `0x180001450`
- `0x180001b70`
- `0x180001f5c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001a46`

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
0x180001a46  jmp     cs:__imp_??3@YAXPEAX@Z
```
