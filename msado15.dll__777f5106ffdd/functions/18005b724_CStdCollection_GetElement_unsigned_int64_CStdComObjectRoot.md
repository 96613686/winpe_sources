# CStdCollection::GetElement(unsigned __int64,CStdComObjectRoot * *)

- ea: `0x18005b724`
- end: `0x18005b787`
- name: `?GetElement@CStdCollection@@QEAAJ_KPEAPEAVCStdComObjectRoot@@@Z`
- size: `99`
- prototype: `int(CStdCollection *__hidden this, unsigned __int64, struct CStdComObjectRoot **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000160c`
- `0x18000174c`
- `0x180001c98`
- `0x18009cfa0`
- `0x18009e460`
- `0x1800a8670`

## callees

- `0x180047a50`
- `0x18005b724`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18005b741`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18005b741`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18005b76d`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18005b76d`

## pseudocode

```c
__int64 __fastcall CStdCollection::GetElement(CStdCollection *this, unsigned __int64 a2, struct CStdComObjectRoot **a3)
{
  unsigned int v6; // edi
  bool v7; // al
  CCollectionList *v8; // rcx
  bool v9; // r9

  v6 = 1;
  v7 = CReaderWriterLock3AR::ReadOrWriteLock((CStdCollection *)((char *)this + 72));
  v8 = (CCollectionList *)*((_QWORD *)this + 8);
  v9 = v7;
  if ( v8 )
    v6 = CCollectionList::LookUpByIndex(v8, a2, (void **)a3);
  CReaderWriterLock3AR::ReadOrWriteUnlock((CStdCollection *)((char *)this + 72), v9);
  return v6;
}

```

## disassembly

```asm
0x18005b724  push    rbx
0x18005b726  push    rbp
0x18005b727  push    rsi
0x18005b728  push    rdi
0x18005b729  push    r14
0x18005b72b  sub     rsp, 20h
0x18005b72f  mov     rbx, rcx
0x18005b732  mov     rbp, r8
0x18005b735  add     rcx, 48h ; 'H'
0x18005b739  mov     r14, rdx
0x18005b73c  mov     edi, 1
0x18005b741  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x18005b748  nop     dword ptr [rax+rax+00h]
0x18005b74d  mov     rcx, [rbx+40h]; this
0x18005b751  mov     r9b, al
0x18005b754  test    rcx, rcx
0x18005b757  jz      short loc_18005B766
0x18005b759  mov     r8, rbp; void **
0x18005b75c  mov     rdx, r14; unsigned __int64
0x18005b75f  call    ?LookUpByIndex@CCollectionList@@QEAAJ_KPEAPEAX@Z; CCollectionList::LookUpByIndex(unsigned __int64,void * *)
0x18005b764  mov     edi, eax
0x18005b766  mov     dl, r9b
0x18005b769  lea     rcx, [rbx+48h]
0x18005b76d  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x18005b774  nop     dword ptr [rax+rax+00h]
0x18005b779  mov     eax, edi
0x18005b77b  add     rsp, 20h
0x18005b77f  pop     r14
0x18005b781  pop     rdi
0x18005b782  pop     rsi
0x18005b783  pop     rbp
0x18005b784  pop     rbx
0x18005b785  retn
```
