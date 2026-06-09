# operator delete(void *)

- ea: `0x180003161`
- end: `0x180003167`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002a60`
- `0x180002aa0`
- `0x180003600`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003161`

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
0x180003161  jmp     cs:__imp_??3@YAXPEAX@Z
```
