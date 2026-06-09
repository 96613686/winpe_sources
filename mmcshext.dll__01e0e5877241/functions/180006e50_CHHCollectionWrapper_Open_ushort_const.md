# CHHCollectionWrapper::Open(ushort const *)

- ea: `0x180006e50`
- end: `0x180006e6c`
- name: `?Open@CHHCollectionWrapper@@UEAAJPEBG@Z`
- size: `28`
- prototype: `__int64 __fastcall(CHHCollectionWrapper *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `hhsetup!?Open@CCollection@@QEAAKPEBG@Z` at `0x180006e58`
- `hhsetup!?Open@CCollection@@QEAAKPEBG@Z` at `0x180006e58`

## pseudocode

```c
__int64 __fastcall CHHCollectionWrapper::Open(CHHCollectionWrapper *this, const unsigned __int16 *a2)
{
  return CCollection::Open((CHHCollectionWrapper *)((char *)this + 16), a2) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180006e50  sub     rsp, 28h
0x180006e54  add     rcx, 10h
0x180006e58  call    cs:__imp_?Open@CCollection@@QEAAKPEBG@Z; CCollection::Open(ushort const *)
0x180006e5e  neg     eax
0x180006e60  sbb     eax, eax
0x180006e62  and     eax, 80004005h
0x180006e67  add     rsp, 28h
0x180006e6b  retn
```
