# CQdefProperties::Refresh(void *,short,bool)

- ea: `0x180086470`
- end: `0x180086f24`
- name: `?Refresh@CQdefProperties@@UEAAJPEAXF_N@Z`
- size: `2740`
- prototype: `__int64 __fastcall(CQdefProperties *__hidden this, void *, __int16, bool)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x180009240`
- `0x18000c670`
- `0x18000d0e0`
- `0x18000f7c0`
- `0x18001a820`
- `0x180020e20`
- `0x180027790`
- `0x180047610`
- `0x180048990`
- `0x1800530f0`
- `0x180054098`
- `0x1800657d0`
- `0x18006a22c`
- `0x180083c40`
- `0x180086470`
- `0x1800c8f34`
- `0x1800c930c`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800864e4`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800864e4`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180086ee4`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180086ee4`
- `MSDART!MpHeapAlloc` at `0x1800865bf`
- `MSDART!MpHeapAlloc` at `0x18008674a`
- `MSDART!MpHeapAlloc` at `0x1800865bf`
- `MSDART!MpHeapAlloc` at `0x18008674a`
- `OLEAUT32!__imp_SysFreeString` at `0x180086b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180086b2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQdefProperties::Refresh(CQdefProperties *this, void *a2, unsigned __int16 a3, char a4)
{
  unsigned __int16 v5; // r14
  CStdCollection *v7; // rsi
  unsigned int v8; // r12d
  unsigned int v9; // ebx
  unsigned int BidObjectID; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rax
  void *v15; // rdi
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // eax
  char *v23; // r15
  CPropSetRefInfo *v24; // rcx
  void *v25; // r14
  CPropSetRefInfo *v26; // rcx
  __int64 v27; // rcx
  int v28; // r15d
  void *v29; // rcx
  CStdCollection *v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rdx
  int v36; // [rsp+20h] [rbp-49h]
  int v37; // [rsp+20h] [rbp-49h]
  int v38; // [rsp+20h] [rbp-49h]
  void *v39; // [rsp+30h] [rbp-39h] BYREF
  char *v40; // [rsp+38h] [rbp-31h]
  __int64 v41; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 v42; // [rsp+48h] [rbp-21h]
  BSTR bstrString; // [rsp+50h] [rbp-19h] BYREF
  char v44; // [rsp+58h] [rbp-11h]
  _BYTE v45[32]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v46; // [rsp+80h] [rbp+17h]
  int v47; // [rsp+88h] [rbp+1Fh]
  void *v48; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int16 v49; // [rsp+E0h] [rbp+77h]
  int FirstInfo; // [rsp+E8h] [rbp+7Fh] BYREF

  v49 = a3;
  v5 = a3;
  v7 = (CQdefProperties *)((char *)this + 16);
  v46 = ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v45);
  v8 = 0;
  v41 = 0;
  bstrString = 0;
  v44 = 6;
  v48 = 0;
  if ( !a4 && !*((_DWORD *)this + 25) )
  {
    v9 = 0;
    goto LABEL_128;
  }
  CReaderWriterLock3AR::WriteLock((CQdefProperties *)((char *)this + 88));
  FirstInfo = (*(__int64 (__fastcall **)(CStdCollection *, _QWORD))(*(_QWORD *)v7 + 280LL))(v7, v5);
  if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_127;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v36 = 5701;
      v11 = 5837833;
LABEL_8:
      bidTraceW(off_18012A1E0[0], v11, L"<CQdefProperties::Refresh|ADO|ERR> %u#, line %d\n", BidObjectID, v36);
      goto LABEL_127;
    }
    v12 = 5701;
    v13 = 5837833;
    goto LABEL_10;
  }
  if ( (unsigned int)CContext::IsStatusFalse((CContext *)v45) )
  {
    if ( !*((_QWORD *)this + 10) )
    {
      v14 = MpHeapAlloc(g_hHeapHandle, 10485760, 48);
      v15 = (void *)v14;
      v42 = v14;
      if ( v14 )
      {
        *(_DWORD *)v14 = 0;
        *(_QWORD *)(v14 + 8) = 0;
        *(_DWORD *)(v14 + 16) = 0;
        *(_DWORD *)(v14 + 24) = 0;
        *(_QWORD *)(v14 + 32) = 0;
        *(_DWORD *)(v14 + 40) = 0;
        *(_BYTE *)(v14 + 44) = 0;
      }
      else
      {
        v15 = 0;
      }
      if ( (unsigned int)CContext::MemFailed((CContext *)v45, v15) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_127;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
          v36 = 5711;
          v11 = 5848073;
          goto LABEL_8;
        }
        v12 = 5711;
        v13 = 5848073;
LABEL_10:
        bidTraceW(off_18012A1E0[0], v13, L"<CQdefProperties::Refresh|ADO|ERR>  line %d\n", v12);
        goto LABEL_127;
      }
      v16 = (*(__int64 (__fastcall **)(CStdCollection *))(*(_QWORD *)v7 + 360LL))(v7);
      FirstInfo = CCollectionList::Reserve((CCollectionList *)v15, v16);
      if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_125;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
        {
          v17 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
          v37 = 5712;
          v18 = 5849097;
LABEL_25:
          bidTraceW(off_18012A1E0[0], v18, L"<CQdefProperties::Refresh|ADO|ERR> %u#, line %d\n", v17, v37);
          goto LABEL_125;
        }
        v19 = 5712;
        v20 = 5849097;
        goto LABEL_124;
      }
      *((_QWORD *)this + 10) = v15;
    }
    if ( *((_BYTE *)this + 112) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_127;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
        v36 = 5716;
        v11 = 5853193;
        goto LABEL_8;
      }
      v12 = 5716;
      v13 = 5853193;
      goto LABEL_10;
    }
  }
  v21 = MpHeapAlloc(g_hHeapHandle, 10485760, 48);
  v15 = (void *)v21;
  v42 = v21;
  if ( v21 )
  {
    *(_DWORD *)v21 = 0;
    *(_QWORD *)(v21 + 8) = 0;
    *(_DWORD *)(v21 + 16) = 0;
    *(_DWORD *)(v21 + 24) = 0;
    *(_QWORD *)(v21 + 32) = 0;
    *(_DWORD *)(v21 + 40) = 0;
    *(_BYTE *)(v21 + 44) = 0;
  }
  else
  {
    v15 = 0;
  }
  if ( (unsigned int)CContext::MemFailed((CContext *)v45, v15) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_127;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v36 = 5720;
      v11 = 5857289;
      goto LABEL_8;
    }
    v12 = 5720;
    v13 = 5857289;
    goto LABEL_10;
  }
  v22 = (*(__int64 (__fastcall **)(CStdCollection *))(*(_QWORD *)v7 + 360LL))(v7);
  FirstInfo = CCollectionList::Reserve((CCollectionList *)v15, v22);
  if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_125;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
    {
      v17 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v37 = 5721;
      v18 = 5858313;
      goto LABEL_25;
    }
    v19 = 5721;
    v20 = 5858313;
LABEL_124:
    bidTraceW(off_18012A1E0[0], v20, L"<CQdefProperties::Refresh|ADO|ERR>  line %d\n", v19);
    goto LABEL_125;
  }
  v23 = 0;
  v40 = 0;
  v42 = (*(unsigned int (__fastcall **)(CStdCollection *))(*(_QWORD *)v7 + 248LL))(v7);
LABEL_47:
  if ( v8 >= 2 )
  {
    CStdCollection::DestroyList(v7, 0);
    *((_QWORD *)this + 10) = v15;
    (*(void (__fastcall **)(CStdCollection *))(*(_QWORD *)v7 + 368LL))(v7);
    *((_BYTE *)this + 112) = a4;
    goto LABEL_127;
  }
  v39 = 0;
  if ( !v8 )
  {
    v24 = (CPropSetRefInfo *)*((_QWORD *)this + 13);
    if ( v24 )
    {
      CPropSetRefInfo::`vector deleting destructor'(v24, 1u);
      *((_QWORD *)this + 13) = 0;
    }
    FirstInfo = CQdefProperties::GetFirstInfo(this, v5, &v39, &DBPROPSET_ROWSETALL);
    if ( !(unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
    {
      v25 = v39;
      *((_QWORD *)this + 13) = v39;
      goto LABEL_57;
    }
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_125;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
    {
      v17 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v37 = 5736;
      v18 = 5873673;
      goto LABEL_25;
    }
    v19 = 5736;
    v20 = 5873673;
    goto LABEL_124;
  }
  v26 = (CPropSetRefInfo *)*((_QWORD *)this + 15);
  if ( v26 )
  {
    CPropSetRefInfo::`vector deleting destructor'(v26, 1u);
    *((_QWORD *)this + 15) = 0;
  }
  FirstInfo = CQdefProperties::GetFirstInfo(this, v5, &v39, &DBPROPSET_STREAMALL);
  if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_125;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
    {
      v17 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v37 = 5747;
      v18 = 5884937;
      goto LABEL_25;
    }
    v19 = 5747;
    v20 = 5884937;
    goto LABEL_124;
  }
  v25 = v39;
  *((_QWORD *)this + 15) = v39;
  while ( 1 )
  {
LABEL_57:
    if ( (unsigned int)CContext::IsStatusFalse((CContext *)v45) )
    {
      ++v8;
      v5 = v49;
      goto LABEL_47;
    }
    v48 = 0;
    FirstInfo = (*(__int64 (__fastcall **)(CStdCollection *, void *, __int64 *))(*(_QWORD *)v7 + 296LL))(v7, v25, &v41);
    if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_119;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
      {
        v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
        v38 = 5757;
        v32 = 5895177;
        goto LABEL_116;
      }
      v33 = 5757;
      v34 = 5895177;
      goto LABEL_118;
    }
    CSysString::operator=(&bstrString, v41);
    v27 = *((_QWORD *)this + 10);
    if ( v27 )
    {
      FirstInfo = CCollectionMap::LookUp(
                    (CCollectionMap *)(v27 + 24),
                    (unsigned __int16 *const)((unsigned __int64)bstrString & -(__int64)((v44 & 4) != 0)),
                    (unsigned __int64 *)&v48);
      if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_119;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) == -1 )
        {
          v33 = 5764;
          v34 = 5902345;
          goto LABEL_118;
        }
        v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
        v38 = 5764;
        v32 = 5902345;
LABEL_116:
        bidTraceW(off_18012A1E0[0], v32, L"<CQdefProperties::Refresh|ADO|ERR> %u#, line %d\n", v31, v38);
        goto LABEL_119;
      }
    }
    if ( !a4 )
      goto LABEL_78;
    if ( !*((_QWORD *)this + 10) || (unsigned int)CContext::IsStatusFalse((CContext *)v45) )
    {
      v28 = 0;
    }
    else
    {
      v28 = 1;
      v29 = v48;
      if ( (unsigned __int64)v48 > v42 )
        goto LABEL_69;
    }
    FirstInfo = (*(__int64 (__fastcall **)(CStdCollection *, void *, _QWORD, void **))(*(_QWORD *)v7 + 304LL))(
                  v7,
                  v25,
                  0,
                  &v48);
    if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_119;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
      {
        v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
        v38 = 5770;
        v32 = 5908489;
        goto LABEL_116;
      }
      v33 = 5770;
      v34 = 5908489;
      goto LABEL_118;
    }
    (*(void (__fastcall **)(CStdCollection *, void *))(*(_QWORD *)v7 + 344LL))(v7, v48);
    v29 = v48;
LABEL_69:
    if ( !v29 )
    {
      v23 = v40;
LABEL_78:
      v40 = ++v23;
      FirstInfo = CCollectionList::AppendNew((CCollectionList *)v15, (const struct CSysString *)&bstrString, v23);
      if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_119;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
        {
          v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
          v38 = 5795;
          v32 = 5934089;
          goto LABEL_116;
        }
        v33 = 5795;
        v34 = 5934089;
        goto LABEL_118;
      }
      goto LABEL_79;
    }
    v30 = (CStdCollection *)*((_QWORD *)v7 + 4);
    if ( v7 == v30 )
      v30 = 0;
    (*(void (__fastcall **)(void *, CStdCollection *))(*(_QWORD *)v29 + 152LL))(v29, v30);
    FirstInfo = (*(__int64 (__fastcall **)(CStdCollection *, void *, void *))(*(_QWORD *)v7 + 312LL))(v7, v25, v48);
    if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
      break;
    if ( v28 )
    {
      FirstInfo = CCollectionList::DeleteByKey(*((CCollectionList **)this + 10), (const struct CSysString *)&bstrString);
      if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_119;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) == -1 )
        {
          v33 = 5788;
          v34 = 5926921;
          goto LABEL_118;
        }
        v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
        v38 = 5788;
        v32 = 5926921;
        goto LABEL_116;
      }
    }
    FirstInfo = CCollectionList::AppendNew((CCollectionList *)v15, (const struct CSysString *)&bstrString, v48);
    if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_119;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) == -1 )
      {
        v33 = 5791;
        v34 = 5929993;
        goto LABEL_118;
      }
      v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v38 = 5791;
      v32 = 5929993;
      goto LABEL_116;
    }
    v23 = v40;
LABEL_79:
    SysFreeString(bstrString);
    bstrString = 0;
    FirstInfo = (*(__int64 (__fastcall **)(CStdCollection *, void *, _QWORD))(*(_QWORD *)v7 + 320LL))(v7, v25, v49);
    if ( (unsigned int)CContext::Failed((CContext *)v45, &FirstInfo) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_119;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) == -1 )
      {
        v33 = 5801;
        v34 = 5940233;
        goto LABEL_118;
      }
      v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
      v38 = 5801;
      v32 = 5940233;
      goto LABEL_116;
    }
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_119;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16)) != -1 )
  {
    v31 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 16));
    v38 = 5783;
    v32 = 5921801;
    goto LABEL_116;
  }
  v33 = 5783;
  v34 = 5921801;
LABEL_118:
  bidTraceW(off_18012A1E0[0], v34, L"<CQdefProperties::Refresh|ADO|ERR>  line %d\n", v33);
LABEL_119:
  *((_BYTE *)this + 112) = 0;
LABEL_125:
  CStdCollection::DestroyList(v7, (struct CCollectionList *)v15);
LABEL_127:
  *((_DWORD *)this + 25) = v47 < 0;
  CReaderWriterLock3AR::WriteUnlock((CQdefProperties *)((char *)this + 88));
  v9 = v47;
LABEL_128:
  CSysString::~CSysString((CSysString *)&bstrString);
  CContext::~CContext((CContext *)v45);
  return v9;
}

```

## disassembly

```asm
0x180086470  mov     [rsp-8+arg_8], rbx
0x180086475  mov     [rsp-8+arg_10], r8w
0x18008647b  push    rbp
0x18008647c  push    rsi
0x18008647d  push    rdi
0x18008647e  push    r12
0x180086480  push    r13
0x180086482  push    r14
0x180086484  push    r15
0x180086486  lea     rbp, [rsp-27h]
0x18008648b  sub     rsp, 90h
0x180086492  mov     r13b, r9b
0x180086495  movzx   r14d, r8w
0x180086499  mov     rbx, rcx
0x18008649c  lea     rsi, [rcx+10h]
0x1800864a0  mov     rax, rcx
0x1800864a3  neg     rax
0x1800864a6  sbb     rdx, rdx
0x1800864a9  and     rdx, rsi
0x1800864ac  mov     [rbp+57h+var_40], rdx
0x1800864b0  lea     rcx, [rbp+57h+var_60]; this
0x1800864b4  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800864b9  nop
0x1800864ba  xor     r12d, r12d
0x1800864bd  mov     [rbp+57h+var_80], r12
0x1800864c1  mov     [rbp+57h+bstrString], r12
0x1800864c5  mov     [rbp+57h+var_68], 6
0x1800864c9  mov     [rbp+57h+arg_0], r12
0x1800864cd  test    r13b, r13b
0x1800864d0  jnz     short loc_1800864E0
0x1800864d2  cmp     [rbx+64h], r12d
0x1800864d6  jnz     short loc_1800864E0
0x1800864d8  mov     ebx, r12d
0x1800864db  jmp     loc_180086EF3
0x1800864e0  lea     rcx, [rbx+58h]
0x1800864e4  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x1800864eb  nop     dword ptr [rax+rax+00h]
0x1800864f0  mov     rax, [rsi]
0x1800864f3  movzx   edx, r14w
0x1800864f7  mov     rcx, rsi
0x1800864fa  mov     rax, [rax+118h]
0x180086501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086506  mov     [rbp+57h+arg_18], eax
0x180086509  lea     rdx, [rbp+57h+arg_18]; int *
0x18008650d  lea     rcx, [rbp+57h+var_60]; this
0x180086511  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180086516  test    eax, eax
0x180086518  jz      short loc_18008658F
0x18008651a  test    byte ptr cs:_bidGblFlags, 2
0x180086521  jz      loc_180086ED5
0x180086527  mov     rcx, [rbx+80h]; this
0x18008652e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086533  cmp     eax, 0FFFFFFFFh
0x180086536  jz      short loc_18008656C
0x180086538  mov     rcx, [rbx+80h]; this
0x18008653f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086544  mov     [rsp+0C0h+var_A0], 1645h
0x18008654c  mov     edx, 591409h
0x180086551  lea     r8, aCqdefpropertie_11; "<CQdefProperties::Refresh|ADO|ERR> %u#,"...
0x180086558  mov     r9d, eax
0x18008655b  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180086562  call    _bidTraceW
0x180086567  jmp     loc_180086ED5
0x18008656c  mov     r9d, 1645h
0x180086572  mov     edx, 591409h
0x180086577  lea     r8, aCqdefpropertie_0; "<CQdefProperties::Refresh|ADO|ERR>  lin"...
0x18008657e  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180086585  call    _bidTraceW
0x18008658a  jmp     loc_180086ED5
0x18008658f  lea     rcx, [rbp+57h+var_60]; this
0x180086593  call    ?IsStatusFalse@CContext@@QEAAHXZ; CContext::IsStatusFalse(void)
0x180086598  mov     r15d, 30h ; '0'
0x18008659e  test    eax, eax
0x1800865a0  jz      loc_18008673B
0x1800865a6  cmp     [rbx+50h], r12
0x1800865aa  jnz     loc_1800866E9
0x1800865b0  mov     r8d, r15d
0x1800865b3  mov     edx, 0A00000h
0x1800865b8  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800865bf  call    cs:__imp_MpHeapAlloc
0x1800865c6  nop     dword ptr [rax+rax+00h]
0x1800865cb  mov     rdi, rax
0x1800865ce  mov     [rbp+57h+var_78], rax
0x1800865d2  test    rax, rax
0x1800865d5  jz      short loc_1800865F4
0x1800865d7  mov     [rax], r12d
0x1800865da  mov     [rax+8], r12
0x1800865de  mov     [rax+10h], r12d
0x1800865e2  mov     [rax+18h], r12d
0x1800865e6  mov     [rax+20h], r12
0x1800865ea  mov     [rax+28h], r12d
0x1800865ee  mov     [rax+2Ch], r12b
0x1800865f2  jmp     short loc_1800865F7
0x1800865f4  mov     rdi, r12
0x1800865f7  mov     rdx, rdi; void *
0x1800865fa  lea     rcx, [rbp+57h+var_60]; this
0x1800865fe  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x180086603  test    eax, eax
0x180086605  jz      short loc_180086653
0x180086607  test    byte ptr cs:_bidGblFlags, 2
0x18008660e  jz      loc_180086ED5
0x180086614  mov     rcx, [rbx+80h]; this
0x18008661b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086620  cmp     eax, 0FFFFFFFFh
0x180086623  jz      short loc_180086643
0x180086625  mov     rcx, [rbx+80h]; this
0x18008662c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086631  mov     [rsp+0C0h+var_A0], 164Fh
0x180086639  mov     edx, 593C09h
0x18008663e  jmp     loc_180086551
0x180086643  mov     r9d, 164Fh
0x180086649  mov     edx, 593C09h
0x18008664e  jmp     loc_180086577
0x180086653  mov     rax, [rsi]
0x180086656  mov     rcx, rsi
0x180086659  mov     rax, [rax+168h]
0x180086660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086665  mov     edx, eax; unsigned int
0x180086667  mov     rcx, rdi; this
0x18008666a  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x18008666f  mov     [rbp+57h+arg_18], eax
0x180086672  lea     rdx, [rbp+57h+arg_18]; int *
0x180086676  lea     rcx, [rbp+57h+var_60]; this
0x18008667a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008667f  test    eax, eax
0x180086681  jz      short loc_1800866E5
0x180086683  test    byte ptr cs:_bidGblFlags, 2
0x18008668a  jz      loc_180086EA4
0x180086690  mov     rcx, [rbx+80h]; this
0x180086697  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008669c  cmp     eax, 0FFFFFFFFh
0x18008669f  jz      short loc_1800866D5
0x1800866a1  mov     rcx, [rbx+80h]; this
0x1800866a8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800866ad  mov     [rsp+0C0h+var_A0], 1650h
0x1800866b5  mov     edx, 594009h
0x1800866ba  lea     r8, aCqdefpropertie_11; "<CQdefProperties::Refresh|ADO|ERR> %u#,"...
0x1800866c1  mov     r9d, eax
0x1800866c4  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800866cb  call    _bidTraceW
0x1800866d0  jmp     loc_180086EA4
0x1800866d5  mov     r9d, 1650h
0x1800866db  mov     edx, 594009h
0x1800866e0  jmp     loc_180086E91
0x1800866e5  mov     [rbx+50h], rdi
0x1800866e9  cmp     [rbx+70h], r12b
0x1800866ed  jz      short loc_18008673B
0x1800866ef  test    byte ptr cs:_bidGblFlags, 2
0x1800866f6  jz      loc_180086ED5
0x1800866fc  mov     rcx, [rbx+80h]; this
0x180086703  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086708  cmp     eax, 0FFFFFFFFh
0x18008670b  jz      short loc_18008672B
0x18008670d  mov     rcx, [rbx+80h]; this
0x180086714  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086719  mov     [rsp+0C0h+var_A0], 1654h
0x180086721  mov     edx, 595009h
0x180086726  jmp     loc_180086551
0x18008672b  mov     r9d, 1654h
0x180086731  mov     edx, 595009h
0x180086736  jmp     loc_180086577
0x18008673b  mov     r8, r15
0x18008673e  mov     edx, 0A00000h
0x180086743  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18008674a  call    cs:__imp_MpHeapAlloc
0x180086751  nop     dword ptr [rax+rax+00h]
0x180086756  mov     rdi, rax
0x180086759  mov     [rbp+57h+var_78], rax
0x18008675d  test    rax, rax
0x180086760  jz      short loc_18008677F
0x180086762  mov     [rax], r12d
0x180086765  mov     [rax+8], r12
0x180086769  mov     [rax+10h], r12d
0x18008676d  mov     [rax+18h], r12d
0x180086771  mov     [rax+20h], r12
0x180086775  mov     [rax+28h], r12d
0x180086779  mov     [rax+2Ch], r12b
0x18008677d  jmp     short loc_180086782
0x18008677f  mov     rdi, r12
0x180086782  mov     rdx, rdi; void *
0x180086785  lea     rcx, [rbp+57h+var_60]; this
0x180086789  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x18008678e  test    eax, eax
0x180086790  jz      short loc_1800867DE
0x180086792  test    byte ptr cs:_bidGblFlags, 2
0x180086799  jz      loc_180086ED5
0x18008679f  mov     rcx, [rbx+80h]; this
0x1800867a6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800867ab  cmp     eax, 0FFFFFFFFh
0x1800867ae  jz      short loc_1800867CE
0x1800867b0  mov     rcx, [rbx+80h]; this
0x1800867b7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800867bc  mov     [rsp+0C0h+var_A0], 1658h
0x1800867c4  mov     edx, 596009h
0x1800867c9  jmp     loc_180086551
0x1800867ce  mov     r9d, 1658h
0x1800867d4  mov     edx, 596009h
0x1800867d9  jmp     loc_180086577
0x1800867de  mov     rax, [rsi]
0x1800867e1  mov     rcx, rsi
0x1800867e4  mov     rax, [rax+168h]
0x1800867eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800867f0  mov     edx, eax; unsigned int
0x1800867f2  mov     rcx, rdi; this
0x1800867f5  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800867fa  mov     [rbp+57h+arg_18], eax
0x1800867fd  lea     rdx, [rbp+57h+arg_18]; int *
0x180086801  lea     rcx, [rbp+57h+var_60]; this
0x180086805  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008680a  test    eax, eax
0x18008680c  jz      short loc_18008685A
0x18008680e  test    byte ptr cs:_bidGblFlags, 2
0x180086815  jz      loc_180086EA4
0x18008681b  mov     rcx, [rbx+80h]; this
0x180086822  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086827  cmp     eax, 0FFFFFFFFh
0x18008682a  jz      short loc_18008684A
0x18008682c  mov     rcx, [rbx+80h]; this
0x180086833  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180086838  mov     [rsp+0C0h+var_A0], 1659h
0x180086840  mov     edx, 596409h
0x180086845  jmp     loc_1800866BA
0x18008684a  mov     r9d, 1659h
0x180086850  mov     edx, 596409h
0x180086855  jmp     loc_180086E91
0x18008685a  mov     r15, r12
0x18008685d  mov     [rbp+57h+var_88], r12
0x180086861  mov     rax, [rsi]
0x180086864  mov     rcx, rsi
0x180086867  mov     rax, [rax+0F8h]
0x18008686e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086873  mov     eax, eax
0x180086875  mov     [rbp+57h+var_78], rax
0x180086879  cmp     r12d, 2
0x18008687d  jnb     loc_180086EB1
0x180086883  mov     [rbp+57h+var_90], 0
0x18008688b  test    r12d, r12d
0x18008688e  jnz     short loc_1800868E4
0x180086890  mov     rcx, [rbx+68h]; this
0x180086894  test    rcx, rcx
0x180086897  jz      short loc_1800868AB
0x180086899  lea     edx, [r12+1]; unsigned int
0x18008689e  call    ??_ECPropSetRefInfo@@UEAAPEAXI@Z; CPropSetRefInfo::`vector deleting destructor'(uint)
0x1800868a3  mov     qword ptr [rbx+68h], 0
0x1800868ab  lea     r9, DBPROPSET_ROWSETALL; struct _GUID *
0x1800868b2  lea     r8, [rbp+57h+var_90]; void **
0x1800868b6  movzx   edx, r14w; __int16
0x1800868ba  mov     rcx, rbx; this
0x1800868bd  call    ?GetFirstInfo@CQdefProperties@@QEAAJFPEAPEAXAEBU_GUID@@@Z; CQdefProperties::GetFirstInfo(short,void * *,_GUID const &)
0x1800868c2  mov     [rbp+57h+arg_18], eax
0x1800868c5  lea     rdx, [rbp+57h+arg_18]; int *
0x1800868c9  lea     rcx, [rbp+57h+var_60]; this
0x1800868cd  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800868d2  test    eax, eax
0x1800868d4  jnz     loc_180086BC1
0x1800868da  mov     r14, [rbp+57h+var_90]
0x1800868de  mov     [rbx+68h], r14
0x1800868e2  jmp     short loc_180086936
0x1800868e4  mov     rcx, [rbx+78h]; this
0x1800868e8  test    rcx, rcx
0x1800868eb  jz      short loc_1800868FF
0x1800868ed  mov     edx, 1; unsigned int
0x1800868f2  call    ??_ECPropSetRefInfo@@UEAAPEAXI@Z; CPropSetRefInfo::`vector deleting destructor'(uint)
0x1800868f7  mov     qword ptr [rbx+78h], 0
0x1800868ff  lea     r9, DBPROPSET_STREAMALL; struct _GUID *
0x180086906  lea     r8, [rbp+57h+var_90]; void **
0x18008690a  movzx   edx, r14w; __int16
0x18008690e  mov     rcx, rbx; this
0x180086911  call    ?GetFirstInfo@CQdefProperties@@QEAAJFPEAPEAXAEBU_GUID@@@Z; CQdefProperties::GetFirstInfo(short,void * *,_GUID const &)
0x180086916  mov     [rbp+57h+arg_18], eax
0x180086919  lea     rdx, [rbp+57h+arg_18]; int *
0x18008691d  lea     rcx, [rbp+57h+var_60]; this
0x180086921  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180086926  test    eax, eax
0x180086928  jnz     loc_180086E4E
0x18008692e  mov     r14, [rbp+57h+var_90]
0x180086932  mov     [rbx+78h], r14
0x180086936  lea     rcx, [rbp+57h+var_60]; this
0x18008693a  call    ?IsStatusFalse@CContext@@QEAAHXZ; CContext::IsStatusFalse(void)
0x18008693f  test    eax, eax
0x180086941  jnz     loc_180086BB4
0x180086947  mov     [rbp+57h+arg_0], 0
0x18008694f  mov     rax, [rsi]
0x180086952  lea     r8, [rbp+57h+var_80]
0x180086956  mov     rdx, r14
0x180086959  mov     rcx, rsi
0x18008695c  mov     rax, [rax+128h]
0x180086963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086968  mov     [rbp+57h+arg_18], eax
0x18008696b  lea     rdx, [rbp+57h+arg_18]; int *
0x18008696f  lea     rcx, [rbp+57h+var_60]; this
0x180086973  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180086978  test    eax, eax
0x18008697a  jnz     loc_180086DDF
0x180086980  mov     rdx, [rbp+57h+var_80]
0x180086984  lea     rcx, [rbp+57h+bstrString]
0x180086988  call    ??4CSysString@@QEAAAEBV0@QEAG@Z; CSysString::operator=(ushort * const)
0x18008698d  mov     rcx, [rbx+50h]
0x180086991  test    rcx, rcx
0x180086994  jz      short loc_1800869C9
  ... truncated ...
```
