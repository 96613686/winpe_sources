# CRecordset::IdentifiersToFieldList(unsigned __int64,tagVARIANT * const,CRsetField * * * const)

- ea: `0x180056260`
- end: `0x180056522`
- name: `?IdentifiersToFieldList@CRecordset@@AEAAJ_KQEAUtagVARIANT@@QEAPEAPEAVCRsetField@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, unsigned __int64, struct tagVARIANT *const, struct CRsetField ***const)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180002990`
- `0x18001cc80`
- `0x18002e050`

## callees

- `0x180009240`
- `0x18000bbc0`
- `0x180011530`
- `0x180020e20`
- `0x180027790`
- `0x180042a04`
- `0x180047a50`
- `0x180056260`
- `0x18006a22c`
- `0x1800b8590`
- `0x1800c8f34`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180056416`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180056416`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180056447`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180056447`
- `MSDART!MpHeapAlloc` at `0x1800562c5`
- `MSDART!MpHeapAlloc` at `0x1800562c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::IdentifiersToFieldList(
        CCollectionList **this,
        unsigned __int64 a2,
        struct tagVARIANT *const a3,
        struct CRsetField ***const a4)
{
  __int64 v8; // rax
  struct CRsetField **v9; // rax
  unsigned int BidObjectID; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned __int64 i; // rdi
  struct CRsetField *v15; // rsi
  bool v16; // r9
  CCollectionList *v17; // rcx
  unsigned int v18; // ebx
  int v20; // [rsp+20h] [rbp-49h]
  struct tagVARIANT v21; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp+7h]
  unsigned int v24; // [rsp+78h] [rbp+Fh]
  void *v25; // [rsp+D0h] [rbp+67h] BYREF

  v23 = (unsigned __int64)(this + 4) & -(__int64)(this != 0);
  CContext::Init((CContext *)v22);
  v8 = 8 * a2;
  if ( !is_mul_ok(a2, 8u) )
    v8 = -1;
  v9 = (struct CRsetField **)MpHeapAlloc(g_hHeapHandle, 10485760, v8);
  *a4 = v9;
  if ( v9
    || (LODWORD(v25) = -2147024882, !(unsigned int)CContext::FailedPushWarning((CContext *)v22, (const int *)&v25)) )
  {
    for ( i = 0; i < a2; ++i )
    {
      if ( a3 )
      {
        v21 = a3[i];
        LODWORD(v25) = CRecordset::get_Field((CRecordset *)this, &v21, &(*a4)[i]);
        if ( (unsigned int)CContext::Failed((CContext *)v22, (const int *)&v25) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_32;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 195)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 195));
            v20 = 11911;
            v11 = 12196873;
            goto LABEL_8;
          }
          v12 = 11911;
          v13 = 12196873;
          goto LABEL_31;
        }
      }
      else
      {
        v15 = 0;
        v25 = 0;
        if ( *((_DWORD *)this + 417) == 1 )
          CStdCollection::Refresh(this + 198, 0, 1u);
        v16 = CReaderWriterLock3AR::ReadOrWriteLock((CReaderWriterLock3AR *)(this + 207));
        v17 = this[206];
        if ( v17 )
        {
          CCollectionList::LookUpByIndex(v17, i, &v25);
          v15 = (struct CRsetField *)v25;
        }
        CReaderWriterLock3AR::ReadOrWriteUnlock((CReaderWriterLock3AR *)(this + 207), v16);
        if ( v15 )
          v15 = (struct CRsetField *)((char *)v15 - 8);
        (*a4)[i] = v15;
        if ( !v15 )
        {
          LODWORD(v25) = -2146825287;
          if ( (unsigned int)CContext::FailedPushWarning((CContext *)v22, (const int *)&v25) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_32;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 195)) != -1 )
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 195));
              v20 = 11915;
              v11 = 12200969;
              goto LABEL_8;
            }
            v12 = 11915;
            v13 = 12200969;
            goto LABEL_31;
          }
        }
      }
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 195)) == -1 )
      {
        v12 = 11903;
        v13 = 12188681;
LABEL_31:
        bidTraceW(off_18012A208[0], v13, L"<CRecordset::IdentifiersToFieldList|ADO|ERR>  line %d\n", v12);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 195));
        v20 = 11903;
        v11 = 12188681;
LABEL_8:
        bidTraceW(
          off_18012A208[0],
          v11,
          L"<CRecordset::IdentifiersToFieldList|ADO|ERR> %u#, line %d\n",
          BidObjectID,
          v20);
      }
    }
LABEL_32:
    if ( *a4 )
    {
      operator delete(*a4);
      *a4 = 0;
    }
  }
  v18 = v24;
  CContext::~CContext((CContext *)v22);
  return v18;
}

```

## disassembly

```asm
0x180056260  push    rbp
0x180056262  push    rbx
0x180056263  push    rsi
0x180056264  push    rdi
0x180056265  push    r12
0x180056267  push    r13
0x180056269  push    r14
0x18005626b  push    r15
0x18005626d  lea     rbp, [rsp-1Fh]
0x180056272  sub     rsp, 88h
0x180056279  mov     r14, r9
0x18005627c  mov     r12, r8
0x18005627f  mov     r13, rdx
0x180056282  mov     rbx, rcx
0x180056285  mov     rax, rcx
0x180056288  lea     r11, [rcx+20h]
0x18005628c  neg     rax
0x18005628f  sbb     r10, r10
0x180056292  and     r10, r11
0x180056295  mov     [rbp+57h+var_50], r10
0x180056299  lea     rcx, [rbp+57h+var_70]; this
0x18005629d  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800562a2  nop
0x1800562a3  mov     eax, 8
0x1800562a8  mul     r13
0x1800562ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800562b2  cmovb   rax, rcx
0x1800562b6  mov     r8, rax
0x1800562b9  mov     edx, 0A00000h
0x1800562be  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800562c5  call    cs:__imp_MpHeapAlloc
0x1800562cc  nop     dword ptr [rax+rax+00h]
0x1800562d1  mov     [r14], rax
0x1800562d4  test    rax, rax
0x1800562d7  jnz     short loc_180056353
0x1800562d9  mov     dword ptr [rbp+57h+arg_0], 8007000Eh
0x1800562e0  lea     rdx, [rbp+57h+arg_0]; int *
0x1800562e4  lea     rcx, [rbp+57h+var_70]; this
0x1800562e8  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x1800562ed  test    eax, eax
0x1800562ef  jz      short loc_180056353
0x1800562f1  test    byte ptr cs:_bidGblFlags, 2
0x1800562f8  jz      loc_1800564EB
0x1800562fe  lea     rcx, [rbx+618h]; this
0x180056305  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005630a  cmp     eax, 0FFFFFFFFh
0x18005630d  jz      short loc_180056343
0x18005630f  lea     rcx, [rbx+618h]; this
0x180056316  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005631b  mov     [rsp+0C0h+var_A0], 2E7Fh
0x180056323  mov     edx, 0B9FC09h
0x180056328  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005632f  mov     r9d, eax
0x180056332  lea     r8, aCrecordsetIden_0; "<CRecordset::IdentifiersToFieldList|ADO"...
0x180056339  call    _bidTraceW
0x18005633e  jmp     loc_1800564EB
0x180056343  mov     r9d, 2E7Fh
0x180056349  mov     edx, 0B9FC09h
0x18005634e  jmp     loc_1800564D8
0x180056353  xor     edi, edi
0x180056355  cmp     rdi, r13
0x180056358  jnb     loc_1800564FF
0x18005635e  test    r12, r12
0x180056361  jz      loc_1800563EB
0x180056367  lea     rax, [rdi+rdi*2]
0x18005636b  movups  xmm0, xmmword ptr [r12+rax*8]
0x180056370  movaps  xmmword ptr [rbp+57h+var_90], xmm0
0x180056374  movsd   xmm1, qword ptr [r12+rax*8+10h]
0x18005637b  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x180056380  mov     rax, [r14]
0x180056383  lea     r8, [rax+rdi*8]; struct CRsetField **
0x180056387  lea     rdx, [rbp+57h+var_90]; struct tagVARIANT
0x18005638b  mov     rcx, rbx; this
0x18005638e  call    ?get_Field@CRecordset@@QEAAJUtagVARIANT@@PEAPEAVCRsetField@@@Z; CRecordset::get_Field(tagVARIANT,CRsetField * *)
0x180056393  mov     dword ptr [rbp+57h+arg_0], eax
0x180056396  lea     rdx, [rbp+57h+arg_0]; int *
0x18005639a  lea     rcx, [rbp+57h+var_70]; this
0x18005639e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800563a3  test    eax, eax
0x1800563a5  jz      loc_180056480
0x1800563ab  test    byte ptr cs:_bidGblFlags, 2
0x1800563b2  jz      loc_1800564EB
0x1800563b8  lea     rcx, [rbx+618h]; this
0x1800563bf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800563c4  cmp     eax, 0FFFFFFFFh
0x1800563c7  jz      loc_180056488
0x1800563cd  lea     rcx, [rbx+618h]; this
0x1800563d4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800563d9  mov     [rsp+0C0h+var_A0], 2E87h
0x1800563e1  mov     edx, 0BA1C09h
0x1800563e6  jmp     loc_180056328
0x1800563eb  xor     esi, esi
0x1800563ed  mov     [rbp+57h+arg_0], rsi
0x1800563f1  cmp     dword ptr [rbx+684h], 1
0x1800563f8  jnz     short loc_18005640C
0x1800563fa  lea     r8d, [rsi+1]; __int16
0x1800563fe  lea     rcx, [rbx+630h]; this
0x180056405  xor     edx, edx; void *
0x180056407  call    ?Refresh@CStdCollection@@UEAAJPEAXF@Z; CStdCollection::Refresh(void *,short)
0x18005640c  lea     r15, [rbx+678h]
0x180056413  mov     rcx, r15
0x180056416  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x18005641d  nop     dword ptr [rax+rax+00h]
0x180056422  mov     r9b, al
0x180056425  mov     rcx, [rbx+670h]; this
0x18005642c  test    rcx, rcx
0x18005642f  jz      short loc_180056441
0x180056431  lea     r8, [rbp+57h+arg_0]; void **
0x180056435  mov     rdx, rdi; unsigned __int64
0x180056438  call    ?LookUpByIndex@CCollectionList@@QEAAJ_KPEAPEAX@Z; CCollectionList::LookUpByIndex(unsigned __int64,void * *)
0x18005643d  mov     rsi, [rbp+57h+arg_0]
0x180056441  mov     dl, r9b
0x180056444  mov     rcx, r15
0x180056447  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x18005644e  nop     dword ptr [rax+rax+00h]
0x180056453  test    rsi, rsi
0x180056456  jz      short loc_18005645C
0x180056458  add     rsi, 0FFFFFFFFFFFFFFF8h
0x18005645c  mov     rax, [r14]
0x18005645f  mov     [rax+rdi*8], rsi
0x180056463  test    rsi, rsi
0x180056466  jnz     short loc_180056480
0x180056468  mov     dword ptr [rbp+57h+arg_0], 800A0BB9h
0x18005646f  lea     rdx, [rbp+57h+arg_0]; int *
0x180056473  lea     rcx, [rbp+57h+var_70]; this
0x180056477  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18005647c  test    eax, eax
0x18005647e  jnz     short loc_180056495
0x180056480  inc     rdi
0x180056483  jmp     loc_180056355
0x180056488  mov     r9d, 2E87h
0x18005648e  mov     edx, 0BA1C09h
0x180056493  jmp     short loc_1800564D8
0x180056495  test    byte ptr cs:_bidGblFlags, 2
0x18005649c  jz      short loc_1800564EB
0x18005649e  lea     rcx, [rbx+618h]; this
0x1800564a5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800564aa  cmp     eax, 0FFFFFFFFh
0x1800564ad  jz      short loc_1800564CD
0x1800564af  lea     rcx, [rbx+618h]; this
0x1800564b6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800564bb  mov     [rsp+0C0h+var_A0], 2E8Bh
0x1800564c3  mov     edx, 0BA2C09h
0x1800564c8  jmp     loc_180056328
0x1800564cd  mov     r9d, 2E8Bh
0x1800564d3  mov     edx, 0BA2C09h
0x1800564d8  lea     r8, aCrecordsetIden; "<CRecordset::IdentifiersToFieldList|ADO"...
0x1800564df  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800564e6  call    _bidTraceW
0x1800564eb  mov     rcx, [r14]; void *
0x1800564ee  test    rcx, rcx
0x1800564f1  jz      short loc_1800564FF
0x1800564f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800564f8  mov     qword ptr [r14], 0
0x1800564ff  mov     ebx, [rbp+57h+var_48]
0x180056502  lea     rcx, [rbp+57h+var_70]; this
0x180056506  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x18005650b  mov     eax, ebx
0x18005650d  add     rsp, 88h
0x180056514  pop     r15
0x180056516  pop     r14
0x180056518  pop     r13
0x18005651a  pop     r12
0x18005651c  pop     rdi
0x18005651d  pop     rsi
0x18005651e  pop     rbx
0x18005651f  pop     rbp
0x180056520  retn
```
