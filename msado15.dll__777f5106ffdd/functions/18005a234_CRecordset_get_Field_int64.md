# CRecordset::get_Field(__int64)

- ea: `0x18005a234`
- end: `0x18005a2c2`
- name: `?get_Field@CRecordset@@QEAAPEAVCRsetField@@_J@Z`
- size: `142`
- prototype: `struct CRsetField *(CRecordset *__hidden this, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180097d30`
- `0x180098ad0`
- `0x1800aed30`

## callees

- `0x18000bbc0`
- `0x180047a50`
- `0x18005a234`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18005a26c`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x18005a26c`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18005a29f`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x18005a29f`

## pseudocode

```c
struct CRsetField *__fastcall CRecordset::get_Field(CRecordset *this, unsigned __int64 a2)
{
  char *v2; // rbx
  CCollectionList **v4; // rcx
  bool v6; // al
  CCollectionList *v7; // rcx
  bool v8; // r9
  void *v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v4 = (CCollectionList **)((char *)this + 1584);
  v10 = 0;
  if ( *((_DWORD *)v4 + 21) == 1 )
    CStdCollection::Refresh(v4, 0, 1u);
  v6 = CReaderWriterLock3AR::ReadOrWriteLock((CRecordset *)((char *)this + 1656));
  v7 = (CCollectionList *)*((_QWORD *)this + 206);
  v8 = v6;
  if ( v7 )
  {
    CCollectionList::LookUpByIndex(v7, a2, &v10);
    v2 = (char *)v10;
  }
  CReaderWriterLock3AR::ReadOrWriteUnlock((CRecordset *)((char *)this + 1656), v8);
  if ( v2 )
    return (struct CRsetField *)(v2 - 8);
  else
    return 0;
}

```

## disassembly

```asm
0x18005a234  push    rbx
0x18005a236  push    rbp
0x18005a237  push    rsi
0x18005a238  push    rdi
0x18005a239  sub     rsp, 28h
0x18005a23d  xor     ebx, ebx
0x18005a23f  mov     rdi, rcx
0x18005a242  add     rcx, 630h; this
0x18005a249  mov     [rsp+48h+arg_0], rbx
0x18005a24e  mov     rbp, rdx
0x18005a251  lea     r8d, [rbx+1]; __int16
0x18005a255  cmp     [rcx+54h], r8d
0x18005a259  jnz     short loc_18005A262
0x18005a25b  xor     edx, edx; void *
0x18005a25d  call    ?Refresh@CStdCollection@@UEAAJPEAXF@Z; CStdCollection::Refresh(void *,short)
0x18005a262  lea     rsi, [rdi+678h]
0x18005a269  mov     rcx, rsi
0x18005a26c  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x18005a273  nop     dword ptr [rax+rax+00h]
0x18005a278  mov     rcx, [rdi+670h]; this
0x18005a27f  mov     r9b, al
0x18005a282  test    rcx, rcx
0x18005a285  jz      short loc_18005A299
0x18005a287  lea     r8, [rsp+48h+arg_0]; void **
0x18005a28c  mov     rdx, rbp; unsigned __int64
0x18005a28f  call    ?LookUpByIndex@CCollectionList@@QEAAJ_KPEAPEAX@Z; CCollectionList::LookUpByIndex(unsigned __int64,void * *)
0x18005a294  mov     rbx, [rsp+48h+arg_0]
0x18005a299  mov     dl, r9b
0x18005a29c  mov     rcx, rsi
0x18005a29f  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x18005a2a6  nop     dword ptr [rax+rax+00h]
0x18005a2ab  test    rbx, rbx
0x18005a2ae  jz      short loc_18005A2B6
0x18005a2b0  lea     rax, [rbx-8]
0x18005a2b4  jmp     short loc_18005A2B8
0x18005a2b6  xor     eax, eax
0x18005a2b8  add     rsp, 28h
0x18005a2bc  pop     rdi
0x18005a2bd  pop     rsi
0x18005a2be  pop     rbp
0x18005a2bf  pop     rbx
0x18005a2c0  retn
```
