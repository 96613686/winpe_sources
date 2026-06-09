# CObject::operator delete(void *)

- ea: `0x1800141e0`
- end: `0x1800141e7`
- name: `??3CObject@@SAXPEAX@Z`
- size: `7`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18001bffd`
- `0x18001c225`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800141e0`

## pseudocode

```c
// attributes: thunk
void __fastcall CObject::operator delete(void *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x1800141e0  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
