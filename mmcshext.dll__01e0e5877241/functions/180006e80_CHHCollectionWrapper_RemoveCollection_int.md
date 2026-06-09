# CHHCollectionWrapper::RemoveCollection(int)

- ea: `0x180006e80`
- end: `0x180006e95`
- name: `?RemoveCollection@CHHCollectionWrapper@@UEAAJH@Z`
- size: `21`
- prototype: `__int64 __fastcall(CHHCollectionWrapper *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `hhsetup!?RemoveCollection@CCollection@@QEAAKH@Z` at `0x180006e88`
- `hhsetup!?RemoveCollection@CCollection@@QEAAKH@Z` at `0x180006e88`

## pseudocode

```c
__int64 __fastcall CHHCollectionWrapper::RemoveCollection(CHHCollectionWrapper *this, int a2)
{
  CCollection::RemoveCollection((CHHCollectionWrapper *)((char *)this + 16), a2);
  return 0;
}

```

## disassembly

```asm
0x180006e80  sub     rsp, 28h
0x180006e84  add     rcx, 10h
0x180006e88  call    cs:__imp_?RemoveCollection@CCollection@@QEAAKH@Z; CCollection::RemoveCollection(int)
0x180006e8e  xor     eax, eax
0x180006e90  add     rsp, 28h
0x180006e94  retn
```
