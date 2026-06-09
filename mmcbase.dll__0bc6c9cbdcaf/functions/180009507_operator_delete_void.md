# operator delete(void *)

- ea: `0x180009507`
- end: `0x18000950d`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800098b0`
- `0x1800098f0`
- `0x18000a140`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180009507`

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
0x180009507  jmp     cs:__imp_??3@YAXPEAX@Z
```
