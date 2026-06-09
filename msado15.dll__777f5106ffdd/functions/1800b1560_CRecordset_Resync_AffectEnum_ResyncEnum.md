# CRecordset::Resync(AffectEnum,ResyncEnum)

- ea: `0x1800b1560`
- end: `0x1800b1e9d`
- name: `?Resync@CRecordset@@UEAAJW4AffectEnum@@W4ResyncEnum@@@Z`
- size: `2365`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, enum AffectEnum, enum ResyncEnum)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800734f0`

## callees

- `0x180001514`
- `0x1800098a0`
- `0x180020e20`
- `0x180028d48`
- `0x180031760`
- `0x180032710`
- `0x18003d270`
- `0x18003f430`
- `0x180042a04`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x180057bdc`
- `0x18005a3a0`
- `0x18006a22c`
- `0x1800975f4`
- `0x180097848`
- `0x1800b1560`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800b1ddd`
- `ole32!CoTaskMemFree` at `0x1800b1df2`
- `ole32!CoTaskMemFree` at `0x1800b1ddd`
- `ole32!CoTaskMemFree` at `0x1800b1df2`

## pseudocode

```c
__int64 __fastcall CRecordset::Resync(CRecordset *this, unsigned int a2, enum ResyncEnum a3, const char *a4)
{
  unsigned int BidObjectID; // eax
  bool v8; // zf
  __int64 v9; // rsi
  BOOL v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  BOOL v15; // eax
  unsigned __int64 *v16; // r15
  unsigned int v17; // eax
  __int64 v18; // rdx
  int v19; // ebx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  int v27[2]; // [rsp+20h] [rbp-69h]
  int v28[2]; // [rsp+28h] [rbp-61h]
  int v29[2]; // [rsp+28h] [rbp-61h]
  LPVOID pv; // [rsp+50h] [rbp-39h] BYREF
  unsigned int *v31; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int64 v32; // [rsp+60h] [rbp-29h] BYREF
  __int64 v33; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v35[40]; // [rsp+78h] [rbp-11h] BYREF
  int v36; // [rsp+A0h] [rbp+17h]
  __int64 v37; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v38; // [rsp+108h] [rbp+7Fh] BYREF

  v33 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ACB0[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    bidScopeEnterW(&v33, off_18012ACB0[0], BidObjectID, a2, a3);
  }
  CXLockContext::CXLockContext(
    (CXLockContext *)v35,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 38) + 8LL),
    a4);
  v31 = 0;
  v8 = (*((_BYTE *)this + 568) & 4) == 0;
  v9 = 1;
  v32 = 0;
  pv = 0;
  v34 = 0;
  if ( v8 )
  {
    v37 = 0;
    if ( (int)CRsetOptionalInterface<IRowsetRefresh,&_GUID const IID_IRowsetRefresh>::GetInterface(
                (char *)this + 552,
                &v37) < 0 )
    {
      v10 = 0;
    }
    else
    {
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v10 = 1;
    }
  }
  else
  {
    v10 = *((_QWORD *)this + 70) != 0;
  }
  if ( (unsigned int)CContext::FailIfClosed((CContext *)v35, *((_DWORD *)this + 315)) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_105;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v12 = 13500425;
      v27[0] = 13184;
LABEL_15:
      bidTraceW(off_18012A208[0], v12, L"<CRecordset::Resync|ADO|ERR> %u#, line %d\n", v11, *(_QWORD *)v27);
      goto LABEL_105;
    }
    v13 = 13184;
    v14 = 13500425;
    goto LABEL_17;
  }
  if ( v10 )
    goto LABEL_119;
  if ( (*((_BYTE *)this + 472) & 4) != 0 )
  {
    v15 = *((_QWORD *)this + 58) != 0;
  }
  else
  {
    v37 = 0;
    if ( (int)CRsetOptionalInterface<IRowsetResynch,&_GUID const IID_IRowsetResynch>::GetInterface(
                (char *)this + 456,
                &v37) < 0 )
    {
      v15 = 0;
    }
    else
    {
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v15 = 1;
    }
  }
  LODWORD(v37) = !v15 ? 0x800A0CB3 : 0;
  if ( !(unsigned int)CContext::FailedDescription((CContext *)v35, (const int *)&v37, 0x272Au) )
  {
LABEL_119:
    if ( (unsigned int)CContext::ArgFailed((CContext *)v35, a2 - 1 <= 3) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_105;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v12 = 13512713;
        v27[0] = 13196;
        goto LABEL_15;
      }
      v13 = 13196;
      v14 = 13512713;
      goto LABEL_17;
    }
    if ( (unsigned int)CContext::ArgFailed((CContext *)v35, (unsigned int)(a3 - 1) <= 1) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_105;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v12 = 13514761;
        v27[0] = 13198;
        goto LABEL_15;
      }
      v13 = 13198;
      v14 = 13514761;
      goto LABEL_17;
    }
    if ( a3 == adResyncUnderlyingValues && (unsigned int)CContext::FeatureFailed((CContext *)v35, v10) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_105;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v12 = 13518857;
        v27[0] = 13202;
        goto LABEL_15;
      }
      v13 = 13202;
      v14 = 13518857;
      goto LABEL_17;
    }
    LODWORD(v37) = (*(__int64 (__fastcall **)(CRecordset *))(*(_QWORD *)this + 752LL))(this);
    if ( (unsigned int)CContext::Failed((CContext *)v35, (const int *)&v37) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_105;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v12 = 13521929;
        v27[0] = 13205;
        goto LABEL_15;
      }
      v13 = 13205;
      v14 = 13521929;
      goto LABEL_17;
    }
    if ( a2 == 1 )
    {
      LODWORD(v37) = CRecordset::GetDeferredHRow(this, &v34);
      if ( (unsigned int)CContext::Failed((CContext *)v35, (const int *)&v37) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_105;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v12 = 13528073;
          v27[0] = 13211;
          goto LABEL_15;
        }
        v13 = 13211;
        v14 = 13528073;
        goto LABEL_17;
      }
      v16 = &v34;
    }
    else
    {
      if ( a2 == 2 )
      {
        if ( (unsigned int)CContext::OpFailed((CContext *)v35, **((_DWORD **)this + 186) == 1) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_105;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v12 = 13534217;
            v27[0] = 13217;
            goto LABEL_15;
          }
          v13 = 13217;
          v14 = 13534217;
        }
        else
        {
          v9 = *((_QWORD *)this + 93);
          v16 = (unsigned __int64 *)*((_QWORD *)this + 97);
          if ( !(unsigned int)CContext::OpFailed((CContext *)v35, v9 != 0) )
            goto LABEL_71;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_105;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v12 = 13540361;
            v27[0] = 13223;
            goto LABEL_15;
          }
          v13 = 13223;
          v14 = 13540361;
        }
LABEL_17:
        bidTraceW(off_18012A208[0], v14, L"<CRecordset::Resync|ADO|ERR>  line %d\n", v13);
        goto LABEL_105;
      }
      v9 = 0;
      v16 = 0;
    }
LABEL_71:
    v38 = 0;
    if ( v10 )
    {
      LODWORD(v37) = CRsetOptionalInterface<IRowsetRefresh,&_GUID const IID_IRowsetRefresh>::GetInterface(
                       (char *)this + 552,
                       &v38);
      if ( (unsigned int)CContext::Failed((CContext *)v35, (const int *)&v37) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 13552649, L"<CRecordset::Resync|ADO|ERR>  line %d\n", 13235);
          }
          else
          {
            v17 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v27[0] = 13235;
            bidTraceW(off_18012A208[0], 13552649, L"<CRecordset::Resync|ADO|ERR> %u#, line %d\n", v17, *(_QWORD *)v27);
          }
        }
LABEL_77:
        ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v38);
        goto LABEL_105;
      }
      if ( a2 == 4 || v9 )
        v18 = 0;
      else
        v18 = *(_QWORD *)(*((_QWORD *)this + 186) + 8LL);
      v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int64 *, bool, unsigned __int64 *, LPVOID *, unsigned int **))(*(_QWORD *)v38 + 24LL))(
              v38,
              v18,
              v9,
              v16,
              a3 == adResyncAllValues,
              &v32,
              &pv,
              &v31);
      if ( v19 < 0 && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          v27[0] = 13247;
          bidTraceW(
            off_18012A208[0],
            13564937,
            L"<CRecordset::Resync|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)v19,
            *(_QWORD *)v27);
        }
        else
        {
          v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v28[0] = 13247;
          v27[0] = v19;
          bidTraceW(
            off_18012A208[0],
            13564937,
            L"<CRecordset::Resync|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v20,
            *(_QWORD *)v27,
            *(_QWORD *)v28);
        }
      }
    }
    else
    {
      LODWORD(v37) = CRsetOptionalInterface<IRowsetResynch,&_GUID const IID_IRowsetResynch>::GetInterface(
                       (char *)this + 456,
                       &v38);
      if ( (unsigned int)CContext::Failed((CContext *)v35, (const int *)&v37) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 13570057, L"<CRecordset::Resync|ADO|ERR>  line %d\n", 13252);
          }
          else
          {
            v21 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v27[0] = 13252;
            bidTraceW(off_18012A208[0], 13570057, L"<CRecordset::Resync|ADO|ERR> %u#, line %d\n", v21, *(_QWORD *)v27);
          }
        }
        goto LABEL_77;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64 *, unsigned __int64 *, LPVOID *, unsigned int **))(*(_QWORD *)v38 + 32LL))(
              v38,
              v9,
              v16,
              &v32,
              &pv,
              &v31);
      if ( v19 < 0 && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          v27[0] = 13262;
          bidTraceW(
            off_18012A208[0],
            13580297,
            L"<CRecordset::Resync|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)v19,
            *(_QWORD *)v27);
        }
        else
        {
          v22 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v29[0] = 13262;
          v27[0] = v19;
          bidTraceW(
            off_18012A208[0],
            13580297,
            L"<CRecordset::Resync|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v22,
            *(_QWORD *)v27,
            *(_QWORD *)v29);
        }
      }
    }
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v38);
    if ( v19 == 265946 )
      v19 = -2147217887;
    LODWORD(v37) = v19;
    CContext::FailedPushWarning((CContext *)v35, (const int *)&v37);
    if ( !v19 || v19 == -2147217887 )
    {
      CRecordset::ReleaseAffectedGroup(this, 0);
      LODWORD(v37) = CRecordset::DefineAffectedGroup(this, v32, (unsigned __int64 *const)pv, v31, v9 != 0, 1);
      if ( (int)v37 < 0 )
        CContext::Failed((CContext *)v35, (const int *)&v37);
    }
    goto LABEL_105;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v12 = 13505545;
      v27[0] = 13189;
      goto LABEL_15;
    }
    v13 = 13189;
    v14 = 13505545;
    goto LABEL_17;
  }
LABEL_105:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v31 )
    CoTaskMemFree(v31);
  if ( (bidGblFlags & 2) != 0 && off_18012A7C8[0] )
  {
    v23 = v36;
    v24 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    v27[0] = v23;
    bidTraceW(off_18012A208[0], 13608960, off_18012A7C8[0], v24, *(_QWORD *)v27);
  }
  if ( (bidGblFlags & 4) != 0 && v33 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v33);
  v25 = v36;
  CXLockContext::~CXLockContext((CXLockContext *)v35);
  return v25;
}

```

## disassembly

```asm
0x1800b1560  mov     [rsp-8+arg_8], rbx
0x1800b1565  push    rbp
0x1800b1566  push    rsi
0x1800b1567  push    rdi
0x1800b1568  push    r12
0x1800b156a  push    r13
0x1800b156c  push    r14
0x1800b156e  push    r15
0x1800b1570  lea     rbp, [rsp-27h]
0x1800b1575  sub     rsp, 0B0h
0x1800b157c  test    byte ptr cs:_bidGblFlags, 4
0x1800b1583  mov     r13d, r8d
0x1800b1586  mov     r14d, edx
0x1800b1589  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFFh
0x1800b1591  mov     rdi, rcx
0x1800b1594  jz      short loc_1800B15C9
0x1800b1596  mov     rax, cs:off_18012ACB0; "<CRecordset::Resync|API|ADO> %u#, Affec"...
0x1800b159d  test    rax, rax
0x1800b15a0  jz      short loc_1800B15C9
0x1800b15a2  add     rcx, 618h; this
0x1800b15a9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b15ae  mov     rdx, cs:off_18012ACB0; "<CRecordset::Resync|API|ADO> %u#, Affec"...
0x1800b15b5  lea     rcx, [rbp+57h+var_78]
0x1800b15b9  mov     r9d, r14d
0x1800b15bc  mov     [rsp+0E0h+var_C0], r13d
0x1800b15c1  mov     r8d, eax
0x1800b15c4  call    _bidScopeEnterW
0x1800b15c9  mov     r8, [rdi+130h]
0x1800b15d0  lea     rcx, [rdi+20h]
0x1800b15d4  add     r8, 8; struct CCriticalSection **
0x1800b15d8  mov     rax, rdi
0x1800b15db  neg     rax
0x1800b15de  sbb     rdx, rdx
0x1800b15e1  and     rdx, rcx; struct CStdComObjectRoot *
0x1800b15e4  lea     rcx, [rbp+57h+var_68]; this
0x1800b15e8  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800b15ed  lea     r12, [rdi+228h]
0x1800b15f4  mov     [rbp+57h+var_88], 0
0x1800b15fc  test    byte ptr [r12+10h], 4
0x1800b1602  mov     esi, 1
0x1800b1607  mov     [rbp+57h+var_80], 0
0x1800b160f  mov     [rbp+57h+pv], 0
0x1800b1617  mov     [rbp+57h+var_70], 0
0x1800b161f  jz      short loc_1800B162D
0x1800b1621  xor     ebx, ebx
0x1800b1623  cmp     [r12+8], rbx
0x1800b1628  setnz   bl
0x1800b162b  jmp     short loc_1800B1660
0x1800b162d  lea     rdx, [rbp+57h+arg_0]
0x1800b1631  mov     [rbp+57h+arg_0], 0
0x1800b1639  mov     rcx, r12
0x1800b163c  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetRefresh@@$1?IID_IRowsetRefresh@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetRefresh@@@Z; CRsetOptionalInterface<IRowsetRefresh,&_GUID const IID_IRowsetRefresh>::GetInterface(IRowsetRefresh * *)
0x1800b1641  test    eax, eax
0x1800b1643  js      short loc_1800B165E
0x1800b1645  mov     rcx, [rbp+57h+arg_0]
0x1800b1649  test    rcx, rcx
0x1800b164c  jz      short loc_1800B165A
0x1800b164e  mov     rax, [rcx]
0x1800b1651  mov     rax, [rax+10h]
0x1800b1655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b165a  mov     ebx, esi
0x1800b165c  jmp     short loc_1800B1660
0x1800b165e  xor     ebx, ebx
0x1800b1660  mov     edx, [rdi+4ECh]; int
0x1800b1666  lea     rcx, [rbp+57h+var_68]; this
0x1800b166a  call    ?FailIfClosed@CContext@@QEAAHH@Z; CContext::FailIfClosed(int)
0x1800b166f  test    eax, eax
0x1800b1671  jz      short loc_1800B16E7
0x1800b1673  test    byte ptr cs:_bidGblFlags, 2
0x1800b167a  jz      loc_1800B1DD4
0x1800b1680  lea     rbx, [rdi+618h]
0x1800b1687  mov     rcx, rbx; this
0x1800b168a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b168f  cmp     eax, 0FFFFFFFFh
0x1800b1692  jz      short loc_1800B16C4
0x1800b1694  mov     rcx, rbx; this
0x1800b1697  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b169c  mov     edx, 0CE0009h
0x1800b16a1  mov     [rsp+0E0h+var_C0], 3380h
0x1800b16a9  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b16b0  lea     r8, aCrecordsetResy_3; "<CRecordset::Resync|ADO|ERR> %u#, line "...
0x1800b16b7  mov     r9d, eax
0x1800b16ba  call    _bidTraceW
0x1800b16bf  jmp     loc_1800B1DD4
0x1800b16c4  mov     r9d, 3380h
0x1800b16ca  mov     edx, 0CE0009h
0x1800b16cf  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b16d6  lea     r8, aCrecordsetResy_0; "<CRecordset::Resync|ADO|ERR>  line %d\n"
0x1800b16dd  call    _bidTraceW
0x1800b16e2  jmp     loc_1800B1DD4
0x1800b16e7  test    ebx, ebx
0x1800b16e9  jnz     loc_1800B17A7
0x1800b16ef  lea     rcx, [rdi+1C8h]
0x1800b16f6  test    byte ptr [rcx+10h], 4
0x1800b16fa  jz      short loc_1800B1707
0x1800b16fc  xor     eax, eax
0x1800b16fe  cmp     [rcx+8], rax
0x1800b1702  setnz   al
0x1800b1705  jmp     short loc_1800B1737
0x1800b1707  lea     rdx, [rbp+57h+arg_0]
0x1800b170b  mov     [rbp+57h+arg_0], 0
0x1800b1713  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetResynch@@$1?IID_IRowsetResynch@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetResynch@@@Z; CRsetOptionalInterface<IRowsetResynch,&_GUID const IID_IRowsetResynch>::GetInterface(IRowsetResynch * *)
0x1800b1718  test    eax, eax
0x1800b171a  js      short loc_1800B1735
0x1800b171c  mov     rcx, [rbp+57h+arg_0]
0x1800b1720  test    rcx, rcx
0x1800b1723  jz      short loc_1800B1731
0x1800b1725  mov     rax, [rcx]
0x1800b1728  mov     rax, [rax+10h]
0x1800b172c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1731  mov     eax, esi
0x1800b1733  jmp     short loc_1800B1737
0x1800b1735  xor     eax, eax
0x1800b1737  neg     eax
0x1800b1739  lea     rdx, [rbp+57h+arg_0]; int *
0x1800b173d  mov     r8d, 272Ah; unsigned int
0x1800b1743  lea     rcx, [rbp+57h+var_68]; this
0x1800b1747  sbb     eax, eax
0x1800b1749  not     eax
0x1800b174b  and     eax, 800A0CB3h
0x1800b1750  mov     dword ptr [rbp+57h+arg_0], eax
0x1800b1753  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800b1758  test    eax, eax
0x1800b175a  jz      short loc_1800B17A7
0x1800b175c  test    byte ptr cs:_bidGblFlags, 2
0x1800b1763  jz      loc_1800B1DD4
0x1800b1769  lea     rbx, [rdi+618h]
0x1800b1770  mov     rcx, rbx; this
0x1800b1773  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b1778  cmp     eax, 0FFFFFFFFh
0x1800b177b  jz      short loc_1800B1797
0x1800b177d  mov     rcx, rbx; this
0x1800b1780  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b1785  mov     edx, 0CE1409h
0x1800b178a  mov     [rsp+0E0h+var_C0], 3385h
0x1800b1792  jmp     loc_1800B16A9
0x1800b1797  mov     r9d, 3385h
0x1800b179d  mov     edx, 0CE1409h
0x1800b17a2  jmp     loc_1800B16CF
0x1800b17a7  xor     edx, edx
0x1800b17a9  lea     eax, [r14-1]
0x1800b17ad  cmp     eax, 3
0x1800b17b0  lea     rcx, [rbp+57h+var_68]; this
0x1800b17b4  setbe   dl; int
0x1800b17b7  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800b17bc  test    eax, eax
0x1800b17be  jz      short loc_1800B180B
0x1800b17c0  test    byte ptr cs:_bidGblFlags, 2
0x1800b17c7  jz      loc_1800B1DD4
0x1800b17cd  lea     rbx, [rdi+618h]
0x1800b17d4  mov     rcx, rbx; this
0x1800b17d7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b17dc  cmp     eax, 0FFFFFFFFh
0x1800b17df  jz      short loc_1800B17FB
0x1800b17e1  mov     rcx, rbx; this
0x1800b17e4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b17e9  mov     edx, 0CE3009h
0x1800b17ee  mov     [rsp+0E0h+var_C0], 338Ch
0x1800b17f6  jmp     loc_1800B16A9
0x1800b17fb  mov     r9d, 338Ch
0x1800b1801  mov     edx, 0CE3009h
0x1800b1806  jmp     loc_1800B16CF
0x1800b180b  xor     edx, edx
0x1800b180d  lea     eax, [r13-1]
0x1800b1811  cmp     eax, esi
0x1800b1813  lea     rcx, [rbp+57h+var_68]; this
0x1800b1817  setbe   dl; int
0x1800b181a  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800b181f  test    eax, eax
0x1800b1821  jz      short loc_1800B186E
0x1800b1823  test    byte ptr cs:_bidGblFlags, 2
0x1800b182a  jz      loc_1800B1DD4
0x1800b1830  lea     rbx, [rdi+618h]
0x1800b1837  mov     rcx, rbx; this
0x1800b183a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b183f  cmp     eax, 0FFFFFFFFh
0x1800b1842  jz      short loc_1800B185E
0x1800b1844  mov     rcx, rbx; this
0x1800b1847  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b184c  mov     edx, 0CE3809h
0x1800b1851  mov     [rsp+0E0h+var_C0], 338Eh
0x1800b1859  jmp     loc_1800B16A9
0x1800b185e  mov     r9d, 338Eh
0x1800b1864  mov     edx, 0CE3809h
0x1800b1869  jmp     loc_1800B16CF
0x1800b186e  cmp     r13d, esi
0x1800b1871  jnz     short loc_1800B18CD
0x1800b1873  mov     edx, ebx; int
0x1800b1875  lea     rcx, [rbp+57h+var_68]; this
0x1800b1879  call    ?FeatureFailed@CContext@@QEAAHH@Z; CContext::FeatureFailed(int)
0x1800b187e  test    eax, eax
0x1800b1880  jz      short loc_1800B18CD
0x1800b1882  test    byte ptr cs:_bidGblFlags, 2
0x1800b1889  jz      loc_1800B1DD4
0x1800b188f  lea     rbx, [rdi+618h]
0x1800b1896  mov     rcx, rbx; this
0x1800b1899  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b189e  cmp     eax, 0FFFFFFFFh
0x1800b18a1  jz      short loc_1800B18BD
0x1800b18a3  mov     rcx, rbx; this
0x1800b18a6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b18ab  mov     edx, 0CE4809h
0x1800b18b0  mov     [rsp+0E0h+var_C0], 3392h
0x1800b18b8  jmp     loc_1800B16A9
0x1800b18bd  mov     r9d, 3392h
0x1800b18c3  mov     edx, 0CE4809h
0x1800b18c8  jmp     loc_1800B16CF
0x1800b18cd  mov     rax, [rdi]
0x1800b18d0  mov     rcx, rdi
0x1800b18d3  mov     rax, [rax+2F0h]
0x1800b18da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18df  lea     rdx, [rbp+57h+arg_0]; int *
0x1800b18e3  mov     dword ptr [rbp+57h+arg_0], eax
0x1800b18e6  lea     rcx, [rbp+57h+var_68]; this
0x1800b18ea  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b18ef  test    eax, eax
0x1800b18f1  jz      short loc_1800B193E
0x1800b18f3  test    byte ptr cs:_bidGblFlags, 2
0x1800b18fa  jz      loc_1800B1DD4
0x1800b1900  lea     rbx, [rdi+618h]
0x1800b1907  mov     rcx, rbx; this
0x1800b190a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b190f  cmp     eax, 0FFFFFFFFh
0x1800b1912  jz      short loc_1800B192E
0x1800b1914  mov     rcx, rbx; this
0x1800b1917  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b191c  mov     edx, 0CE5409h
0x1800b1921  mov     [rsp+0E0h+var_C0], 3395h
0x1800b1929  jmp     loc_1800B16A9
0x1800b192e  mov     r9d, 3395h
0x1800b1934  mov     edx, 0CE5409h
0x1800b1939  jmp     loc_1800B16CF
0x1800b193e  cmp     r14d, esi
0x1800b1941  jnz     short loc_1800B19B7
0x1800b1943  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x1800b1947  mov     rcx, rdi; this
0x1800b194a  call    ?GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z; CRecordset::GetDeferredHRow(unsigned __int64 *)
0x1800b194f  lea     rdx, [rbp+57h+arg_0]; int *
0x1800b1953  mov     dword ptr [rbp+57h+arg_0], eax
0x1800b1956  lea     rcx, [rbp+57h+var_68]; this
0x1800b195a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b195f  test    eax, eax
0x1800b1961  jz      short loc_1800B19AE
0x1800b1963  test    byte ptr cs:_bidGblFlags, 2
0x1800b196a  jz      loc_1800B1DD4
0x1800b1970  lea     rbx, [rdi+618h]
0x1800b1977  mov     rcx, rbx; this
0x1800b197a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b197f  cmp     eax, 0FFFFFFFFh
0x1800b1982  jz      short loc_1800B199E
0x1800b1984  mov     rcx, rbx; this
0x1800b1987  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b198c  mov     edx, 0CE6C09h
0x1800b1991  mov     [rsp+0E0h+var_C0], 339Bh
0x1800b1999  jmp     loc_1800B16A9
0x1800b199e  mov     r9d, 339Bh
0x1800b19a4  mov     edx, 0CE6C09h
0x1800b19a9  jmp     loc_1800B16CF
0x1800b19ae  lea     r15, [rbp+57h+var_70]
0x1800b19b2  jmp     loc_1800B1A9A
0x1800b19b7  cmp     r14d, 2
0x1800b19bb  jnz     loc_1800B1A95
0x1800b19c1  mov     rax, [rdi+5D0h]
0x1800b19c8  lea     rcx, [rbp+57h+var_68]; this
0x1800b19cc  xor     edx, edx
0x1800b19ce  cmp     [rax], esi
0x1800b19d0  setz    dl; int
0x1800b19d3  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x1800b19d8  test    eax, eax
0x1800b19da  jz      short loc_1800B1A27
0x1800b19dc  test    byte ptr cs:_bidGblFlags, r14b
0x1800b19e3  jz      loc_1800B1DD4
0x1800b19e9  lea     rbx, [rdi+618h]
0x1800b19f0  mov     rcx, rbx; this
0x1800b19f3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b19f8  cmp     eax, 0FFFFFFFFh
0x1800b19fb  jz      short loc_1800B1A17
0x1800b19fd  mov     rcx, rbx; this
0x1800b1a00  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b1a05  mov     edx, 0CE8409h
0x1800b1a0a  mov     [rsp+0E0h+var_C0], 33A1h
0x1800b1a12  jmp     loc_1800B16A9
0x1800b1a17  mov     r9d, 33A1h
0x1800b1a1d  mov     edx, 0CE8409h
0x1800b1a22  jmp     loc_1800B16CF
0x1800b1a27  mov     rsi, [rdi+2E8h]
0x1800b1a2e  lea     rcx, [rbp+57h+var_68]; this
0x1800b1a32  mov     r15, [rdi+308h]
0x1800b1a39  xor     edx, edx
0x1800b1a3b  test    rsi, rsi
0x1800b1a3e  setnz   dl; int
0x1800b1a41  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x1800b1a46  test    eax, eax
0x1800b1a48  jz      short loc_1800B1A9A
0x1800b1a4a  test    byte ptr cs:_bidGblFlags, 2
0x1800b1a51  jz      loc_1800B1DD4
0x1800b1a57  lea     rbx, [rdi+618h]
0x1800b1a5e  mov     rcx, rbx; this
0x1800b1a61  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b1a66  cmp     eax, 0FFFFFFFFh
  ... truncated ...
```
