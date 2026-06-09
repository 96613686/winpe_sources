# CParameters::GetParameter(unsigned __int64,CParameter * *)

- ea: `0x180059f4c`
- end: `0x18005a08c`
- name: `?GetParameter@CParameters@@QEAAJ_KPEAPEAVCParameter@@@Z`
- size: `320`
- prototype: `int(CParameters *__hidden this, unsigned __int64, struct CParameter **)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180012f70`
- `0x1800145d0`
- `0x18004ca30`
- `0x18005410c`
- `0x180054710`
- `0x180056554`
- `0x18005a3d4`
- `0x18006cfc0`

## callees

- `0x180047a50`
- `0x180059f4c`
- `0x18006a22c`
- `0x1800c8f34`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180059f73`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180059f73`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180059fa6`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180059fa6`

## pseudocode

```c
__int64 __fastcall CParameters::GetParameter(CParameters *this, unsigned __int64 a2, struct CParameter **a3)
{
  char *v3; // rbx
  unsigned int v7; // edi
  bool v8; // al
  CCollectionList *v9; // rcx
  bool v10; // r9
  unsigned int v11; // eax
  unsigned int BidObjectID; // eax
  unsigned int v13; // eax
  struct CParameter *v15; // rax
  __int64 v16; // [rsp+20h] [rbp-48h]
  void *v17; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v17 = 0;
  *a3 = 0;
  v7 = 1;
  v8 = CReaderWriterLock3AR::ReadOrWriteLock((CParameters *)((char *)this + 96));
  v9 = (CCollectionList *)*((_QWORD *)this + 11);
  v10 = v8;
  if ( v9 )
  {
    v11 = CCollectionList::LookUpByIndex(v9, a2, &v17);
    v3 = (char *)v17;
    v7 = v11;
  }
  CReaderWriterLock3AR::ReadOrWriteUnlock((CParameters *)((char *)this + 96), v10);
  if ( v7 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
      {
        bidTraceW(off_18012A1D0[0], 3698697, L"<CParameters::GetParameter|ADO|ERR> 0x%08x{HRESULT} line %d\n", v7, 3612);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
        bidTraceW(
          off_18012A1D0[0],
          3698697,
          L"<CParameters::GetParameter|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          v7,
          3612);
      }
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_18012A448[0] )
      {
        v13 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
        LODWORD(v16) = -2147024809;
        bidTraceW(off_18012A1D0[0], 3707904, off_18012A448[0], v13, v16);
      }
    }
    return 2147942487LL;
  }
  else
  {
    if ( v3 )
      v15 = (struct CParameter *)(v3 - 24);
    else
      v15 = 0;
    *a3 = v15;
    return 0;
  }
}

```

## disassembly

```asm
0x180059f4c  push    rbx
0x180059f4e  push    rbp
0x180059f4f  push    rsi
0x180059f50  push    rdi
0x180059f51  push    r14
0x180059f53  push    r15
0x180059f55  sub     rsp, 38h
0x180059f59  xor     ebx, ebx
0x180059f5b  mov     rsi, rcx
0x180059f5e  add     rcx, 60h ; '`'
0x180059f62  mov     [rsp+68h+arg_0], rbx
0x180059f67  mov     r14, r8
0x180059f6a  mov     [r8], rbx
0x180059f6d  mov     r15, rdx
0x180059f70  lea     edi, [rbx+1]
0x180059f73  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x180059f7a  nop     dword ptr [rax+rax+00h]
0x180059f7f  mov     rcx, [rsi+58h]; this
0x180059f83  mov     r9b, al
0x180059f86  test    rcx, rcx
0x180059f89  jz      short loc_180059F9F
0x180059f8b  lea     r8, [rsp+68h+arg_0]; void **
0x180059f90  mov     rdx, r15; unsigned __int64
0x180059f93  call    ?LookUpByIndex@CCollectionList@@QEAAJ_KPEAPEAX@Z; CCollectionList::LookUpByIndex(unsigned __int64,void * *)
0x180059f98  mov     rbx, [rsp+68h+arg_0]
0x180059f9d  mov     edi, eax
0x180059f9f  mov     dl, r9b
0x180059fa2  lea     rcx, [rsi+60h]
0x180059fa6  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x180059fad  nop     dword ptr [rax+rax+00h]
0x180059fb2  test    edi, edi
0x180059fb4  jz      loc_18005A06C
0x180059fba  test    byte ptr cs:_bidGblFlags, 2
0x180059fc1  jz      short loc_18005A026
0x180059fc3  lea     rcx, [rsi+70h]; this
0x180059fc7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180059fcc  cmp     eax, 0FFFFFFFFh
0x180059fcf  jz      short loc_18005A003
0x180059fd1  lea     rcx, [rsi+70h]; this
0x180059fd5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180059fda  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180059fe1  lea     r8, aCparametersGet_2; "<CParameters::GetParameter|ADO|ERR> %u#"...
0x180059fe8  mov     r9d, eax
0x180059feb  mov     [rsp+68h+var_40], 0E1Ch
0x180059ff3  mov     edx, 387009h
0x180059ff8  mov     dword ptr [rsp+68h+var_48], edi
0x180059ffc  call    _bidTraceW
0x18005a001  jmp     short loc_18005A026
0x18005a003  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005a00a  lea     r8, aCparametersGet_4; "<CParameters::GetParameter|ADO|ERR> 0x%"...
0x18005a011  mov     r9d, edi
0x18005a014  mov     dword ptr [rsp+68h+var_48], 0E1Ch
0x18005a01c  mov     edx, 387009h
0x18005a021  call    _bidTraceW
0x18005a026  test    byte ptr cs:_bidGblFlags, 2
0x18005a02d  mov     ebx, 80070057h
0x18005a032  jz      short loc_18005A068
0x18005a034  mov     rax, cs:off_18012A448; "<CParameters::GetParameter|API|ADO|RET>"...
0x18005a03b  test    rax, rax
0x18005a03e  jz      short loc_18005A068
0x18005a040  lea     rcx, [rsi+70h]; this
0x18005a044  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005a049  mov     r8, cs:off_18012A448; "<CParameters::GetParameter|API|ADO|RET>"...
0x18005a050  mov     r9d, eax
0x18005a053  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005a05a  mov     edx, 389400h
0x18005a05f  mov     dword ptr [rsp+68h+var_48], ebx
0x18005a063  call    _bidTraceW
0x18005a068  mov     eax, ebx
0x18005a06a  jmp     short loc_18005A07E
0x18005a06c  test    rbx, rbx
0x18005a06f  jz      short loc_18005A077
0x18005a071  lea     rax, [rbx-18h]
0x18005a075  jmp     short loc_18005A079
0x18005a077  xor     eax, eax
0x18005a079  mov     [r14], rax
0x18005a07c  xor     eax, eax
0x18005a07e  add     rsp, 38h
0x18005a082  pop     r15
0x18005a084  pop     r14
0x18005a086  pop     rdi
0x18005a087  pop     rsi
0x18005a088  pop     rbp
0x18005a089  pop     rbx
0x18005a08a  retn
```
