# CRecordset::MoveAbsolute(__int64,unsigned __int64,uchar *,bool)

- ea: `0x180004de0`
- end: `0x180005a5e`
- name: `?MoveAbsolute@CRecordset@@AEAAJ_J_KPEAE_N@Z`
- size: `3198`
- prototype: `__int64 __usercall@<rax>(CRecordset *__hidden this@<rcx>, __int64@<rdx>, unsigned __int64@<r8>, unsigned __int8 *@<r9>, bool)`
- caller_count: `5`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180003fa0`
- `0x180006a34`
- `0x18000a320`
- `0x1800604c4`
- `0x1800b5d64`

## callees

- `0x180001514`
- `0x180004418`
- `0x180004de0`
- `0x180005a70`
- `0x180006610`
- `0x180006890`
- `0x18000a320`
- `0x18002a0f0`
- `0x18002cd84`
- `0x18003f430`
- `0x180041290`
- `0x180045760`
- `0x180050bc0`
- `0x180055ec4`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18000515b`
- `MSDART!MpHeapAlloc` at `0x18000519e`
- `MSDART!MpHeapAlloc` at `0x18000515b`
- `MSDART!MpHeapAlloc` at `0x18000519e`
- `MSDART!MpHeapFree` at `0x18000584d`
- `MSDART!MpHeapFree` at `0x18000589a`
- `MSDART!MpHeapFree` at `0x1800058cd`
- `MSDART!MpHeapFree` at `0x18000584d`
- `MSDART!MpHeapFree` at `0x18000589a`
- `MSDART!MpHeapFree` at `0x1800058cd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180005535`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180005535`

## string_xrefs

- `0x1800052f0`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180005373`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18000540e`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800054a2`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800055aa`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18000562c`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18000567e`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800057bf`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180005942`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180005a01`: `<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180005394`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x18000542f`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800054d1`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x18000569c`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800058e9`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180005967`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180005a1f`: `<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRecordset::MoveAbsolute(
        CRecordset *this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        bool a5)
{
  unsigned __int64 v8; // r15
  __int64 v9; // rbx
  _DWORD *v10; // rax
  unsigned __int64 v11; // r14
  int IRowset; // esi
  unsigned __int64 RecoveryHRow; // r14
  __int64 v15; // r15
  int v16; // eax
  _QWORD *v17; // r14
  unsigned __int64 v18; // rsi
  __int64 *v19; // rax
  bool v20; // r14
  unsigned __int64 v21; // r15
  int v22; // eax
  int v23; // eax
  unsigned __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // r14d
  int v28; // ecx
  char *v29; // r15
  void *v30; // rax
  char v31; // cl
  __int64 v32; // rax
  unsigned int v33; // eax
  __int64 (__fastcall *v34)(__int64, __int64, __int64, unsigned __int8 *, _QWORD, __int128 *, __int64 *); // rax
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned int BidObjectID; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v40; // rdx
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // r8
  unsigned int v47; // eax
  unsigned int v48; // eax
  bool *v49; // [rsp+20h] [rbp-61h]
  unsigned __int64 v50; // [rsp+28h] [rbp-59h]
  unsigned __int8 *v51; // [rsp+30h] [rbp-51h]
  struct IRowset *v52; // [rsp+50h] [rbp-31h] BYREF
  __int64 v53; // [rsp+58h] [rbp-29h] BYREF
  void *Src; // [rsp+60h] [rbp-21h]
  unsigned __int64 v55; // [rsp+68h] [rbp-19h]
  __int64 v56; // [rsp+70h] [rbp-11h]
  struct IRowset *v57; // [rsp+78h] [rbp-9h] BYREF
  __int128 v58; // [rsp+80h] [rbp-1h] BYREF
  __int64 v59; // [rsp+90h] [rbp+Fh]
  __int64 v60; // [rsp+E0h] [rbp+5Fh] BYREF
  unsigned __int64 v61; // [rsp+E8h] [rbp+67h]

  v61 = a2;
  v8 = 0;
  v55 = 0;
  v56 = 0;
  LOBYTE(v60) = 0;
  v9 = 0;
  v53 = 0;
  if ( *((_BYTE *)this + 1506) == 1 )
  {
    CRecordset::_MoveFirst(this, 0, 1);
    a2 = v61;
  }
  v10 = (_DWORD *)*((_QWORD *)this + 186);
  if ( v10 && *v10 == 1 )
  {
    v11 = *((_QWORD *)this + 93);
    LODWORD(v60) = 0;
    if ( a3 == 1 )
    {
      if ( *a4 == byBmkFirst )
      {
        IRowset = CRecordset::PositionInGroupFilter(this, a2, a5);
        if ( IRowset < 0 && (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(
              off_18012A208[0],
              10334217,
              L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              (unsigned int)IRowset,
              10092);
          }
          else
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(
              off_18012A208[0],
              10334217,
              L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              BidObjectID,
              IRowset,
              10092);
          }
        }
      }
      else
      {
        IRowset = 0;
        if ( *a4 == byBmkLast )
        {
          IRowset = CRecordset::PositionInGroupFilter(this, v11 + a2 - 1, a5);
          if ( IRowset < 0 && (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
            {
              bidTraceW(
                off_18012A208[0],
                10338313,
                L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)IRowset,
                10096);
            }
            else
            {
              v38 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              bidTraceW(
                off_18012A208[0],
                10338313,
                L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v38,
                IRowset,
                10096);
            }
          }
        }
      }
    }
    else
    {
      v52 = 0;
      IRowset = CRecordset::GetIRowset(this, &v52);
      if ( IRowset >= 0 )
      {
        while ( 1 )
        {
          if ( v8 >= v11 )
          {
            IRowset = -2147217906;
            goto LABEL_87;
          }
          v58 = 0;
          v59 = 0;
          if ( (int)CRecordset::GetBookmarkData(
                      this,
                      v52,
                      *(_QWORD *)(*((_QWORD *)this + 97) + 8 * v8),
                      (struct CBookmarkData *)&v58) >= 0 )
          {
            if ( !v9 )
            {
              IRowset = CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
                          (char *)this + 312,
                          &v53);
              if ( IRowset < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
                  {
                    LODWORD(v49) = 10114;
                    bidTraceW(
                      off_18012A208[0],
                      10356745,
                      L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                      (unsigned int)IRowset,
                      v49);
                  }
                  else
                  {
                    v43 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                    LODWORD(v50) = 10114;
                    LODWORD(v49) = IRowset;
                    bidTraceW(
                      off_18012A208[0],
                      10356745,
                      L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                      v43,
                      v49,
                      v50);
                  }
                }
                ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v52);
                v9 = v53;
                goto LABEL_8;
              }
              v9 = v53;
            }
            v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, _QWORD, __int128 *, __int64 *))(*(_QWORD *)v9 + 64LL);
            v35 = *(_QWORD *)(*((_QWORD *)this + 186) + 8LL);
            if ( *((_BYTE *)this + 1256) == 1 )
            {
              IRowset = v34(v9, v35, a3, a4, *((_QWORD *)&v58 + 1), (__int128 *)v58, &v60);
              if ( IRowset )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_87;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
                {
                  v36 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                  LODWORD(v50) = 10124;
                  LODWORD(v49) = IRowset;
                  bidTraceW(
                    off_18012A208[0],
                    10366985,
                    L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                    v36,
                    v49,
                    v50);
                  goto LABEL_87;
                }
                LODWORD(v49) = 10124;
                v40 = 10366985;
                goto LABEL_85;
              }
            }
            else
            {
              IRowset = v34(v9, v35, a3, a4, *((_QWORD *)&v58 + 1), &v58, &v60);
              if ( IRowset )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
                  {
                    LODWORD(v49) = 10141;
                    v40 = 10384393;
                    goto LABEL_85;
                  }
                  v41 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                  LODWORD(v50) = 10141;
                  LODWORD(v49) = IRowset;
                  bidTraceW(
                    off_18012A208[0],
                    10384393,
                    L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                    v41,
                    v49,
                    v50);
                }
                goto LABEL_87;
              }
            }
            if ( (_DWORD)v60 == 1 )
            {
              IRowset = CRecordset::PositionInGroupFilter(this, v8 + v61, a5);
              if ( IRowset >= 0 || (bidGblFlags & 2) == 0 )
                goto LABEL_87;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
              {
                v42 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                LODWORD(v50) = 10148;
                LODWORD(v49) = IRowset;
                bidTraceW(
                  off_18012A208[0],
                  10391561,
                  L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v42,
                  v49,
                  v50);
                goto LABEL_87;
              }
              LODWORD(v49) = 10148;
              v40 = 10391561;
LABEL_85:
              bidTraceW(
                off_18012A208[0],
                v40,
                L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)IRowset,
                v49);
              goto LABEL_87;
            }
          }
          else
          {
            SetErrorInfo(0, 0);
          }
          ++v8;
        }
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          LODWORD(v49) = 10102;
          v40 = 10344457;
          goto LABEL_85;
        }
        v39 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(
          off_18012A208[0],
          10344457,
          L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v39,
          IRowset,
          10102);
      }
LABEL_87:
      ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v52);
    }
    goto LABEL_8;
  }
  RecoveryHRow = CRecordset::GetRecoveryHRow(this);
  v52 = (struct IRowset *)RecoveryHRow;
  v15 = *((int *)this + 180);
  if ( (*((_DWORD *)this + 174) & 0x100) == 0 )
  {
    IRowset = CRecordset::ReleaseAffectedGroup(this, 0);
    if ( IRowset < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_147:
        CRecordset::ReleaseRecoveryHRow(this, RecoveryHRow);
        goto LABEL_8;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(
          off_18012A208[0],
          9834505,
          L"<CRecordset::PrepareForFetch|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)IRowset,
          9604);
      }
      else
      {
        v33 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(
          off_18012A208[0],
          9834505,
          L"<CRecordset::PrepareForFetch|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v33,
          IRowset,
          9604);
      }
LABEL_115:
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          LODWORD(v49) = 10024;
          bidTraceW(
            off_18012A208[0],
            10264585,
            L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)IRowset,
            v49);
        }
        else
        {
          v45 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v50) = 10024;
          LODWORD(v49) = IRowset;
          bidTraceW(
            off_18012A208[0],
            10264585,
            L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v45,
            v49,
            v50);
        }
      }
      goto LABEL_147;
    }
  }
  v16 = *((_DWORD *)this + 174);
  if ( (v16 & 0x100) == 0 || (v16 & 0x200) != 0 )
  {
    v17 = (_QWORD *)((char *)this + 736);
    IRowset = CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 736));
    *((_QWORD *)this + 93) = 0;
    if ( IRowset < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(
            off_18012A208[0],
            9841673,
            L"<CRecordset::PrepareForFetch|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)IRowset,
            9611);
        }
        else
        {
          v44 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(
            off_18012A208[0],
            9841673,
            L"<CRecordset::PrepareForFetch|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v44,
            IRowset,
            9611);
        }
      }
      goto LABEL_114;
    }
  }
  else
  {
    v17 = (_QWORD *)((char *)this + 736);
  }
  v18 = -v15;
  if ( v15 > 0 )
    v18 = v15;
  if ( v18 <= v17[3] )
  {
LABEL_17:
    v19 = v17 + 6;
    if ( !*((_BYTE *)v17 + 96) )
      v19 = v17 + 5;
    v56 = *v19;
    IRowset = 0;
    goto LABEL_20;
  }
  Src = 0;
  v28 = *(_DWORD *)(*v17 + 696LL);
  if ( (v28 & 0x100) == 0 || (v28 & 0x200) != 0 )
  {
    v29 = (char *)(v17 + 12);
    *((_BYTE *)v17 + 96) = 0;
  }
  else
  {
    v29 = (char *)(v17 + 12);
    *((_BYTE *)v17 + 96) = 1;
    if ( v17[1] )
    {
      Src = (void *)v17[5];
      v17[5] = 0;
    }
  }
  CRecordGroup::FreeRows((CRecordGroup *)v17);
  if ( v18 + 1 >= v18 && (v57 = (struct IRowset *)(8 * (v18 + 1)), is_mul_ok(8u, v18 + 1)) )
  {
    v30 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, 8 * (v18 + 1));
    v17[5] = v30;
    v31 = *v29;
    if ( v30 )
    {
      v17[3] = v18;
      if ( v31 )
      {
        v46 = v17[1];
        if ( v46 )
        {
          memcpy_0(v30, Src, 8 * v46);
          if ( Src )
            MpHeapFree(g_hHeapHandle, Src);
        }
      }
      if ( *v29 )
      {
        v32 = MpHeapAlloc(g_hHeapHandle, 10485760, v57);
        v17[6] = v32;
        if ( !v32 )
        {
          CRecordGroup::FreeRows((CRecordGroup *)v17);
          IRowset = -2147024882;
          goto LABEL_20;
        }
      }
      goto LABEL_17;
    }
    if ( v31 && v17[1] && Src )
      MpHeapFree(g_hHeapHandle, Src);
    IRowset = -2147024882;
  }
  else
  {
    if ( *v29 && v17[1] && Src )
      MpHeapFree(g_hHeapHandle, Src);
    IRowset = -2146824567;
  }
LABEL_20:
  if ( IRowset < 0 )
  {
LABEL_114:
    RecoveryHRow = (unsigned __int64)v52;
    goto LABEL_115;
  }
  v20 = a5;
  v21 = v61;
  while ( 1 )
  {
    if ( *((_DWORD *)this + 483) == 1 )
    {
      v24 = 0;
      v55 = 0;
      v23 = 265926;
      goto LABEL_27;
    }
    if ( !v9 )
    {
      IRowset = CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
                  (char *)this + 312,
                  &v53);
      if ( IRowset >= 0 )
      {
        v9 = v53;
        goto LABEL_24;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v47 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v50) = 10038;
          LODWORD(v49) = IRowset;
          bidTraceW(
            off_18012A208[0],
            10278921,
            L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v47,
            v49,
            v50);
          v9 = v53;
LABEL_146:
          CRecordset::RecoverPosition(this, (unsigned __int64)v52, v20);
          RecoveryHRow = 4294967167LL;
          goto LABEL_147;
        }
        LODWORD(v49) = 10038;
        bidTraceW(
          off_18012A208[0],
          10278921,
          L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)IRowset,
          v49);
      }
      v9 = v53;
      goto LABEL_146;
    }
LABEL_24:
    v22 = -*((_DWORD *)this + 180);
    if ( !v20 )
      v22 = *((_DWORD *)this + 180);
    v51 = (unsigned __int8 *)v22;
    v50 = v21;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, unsigned __int8 *))(*(_QWORD *)v9 + 72LL))(
            v9,
            0,
            *(_QWORD *)(*((_QWORD *)this + 186) + 8LL),
            a3,
            a4);
    v24 = v55;
LABEL_27:
    IRowset = CRecordset::ProcessFetch(this, v23, v24, v20, (bool *)&v60, v50, v51);
    if ( IRowset < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          LODWORD(v49) = 10054;
          bidTraceW(
            off_18012A208[0],
            10295305,
            L"<CRecordset::MoveAbsolute|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)IRowset,
            v49);
        }
        else
        {
          v48 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v50) = 10054;
          LODWORD(v49) = IRowset;
          bidTraceW(
            off_18012A208[0],
            10295305,
            L"<CRecordset::MoveAbsolute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v48,
            v49,
            v50);
        }
      }
      goto LABEL_146;
    }
    if ( !(_BYTE)v60 )
      break;
    LOBYTE(v60) = 0;
  }
  v57 = v52;
  if ( v52 == (struct IRowset *)4294967167LL )
    goto LABEL_8;
  v25 = 0;
  v60 = 0;
  v26 = *((_QWORD *)this + 141);
  if ( !v26 )
    goto LABEL_38;
  v27 = 0;
  if ( (*((_BYTE *)this + 1136) & 1) == 0 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 8LL))(*((_QWORD *)this + 141));
    v25 = *((_QWORD *)this + 141);
    goto LABEL_36;
  }
  if ( (_DWORD)v26 )
  {
    v60 = 0;
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 *))(**((_QWORD **)g_pStaticGlobals + 10) + 40LL))(
            *((_QWORD *)g_pStaticGlobals + 10),
            v26,
            &IID_IRowset,
            &v60);
    v25 = v60;
  }
  else
  {
LABEL_36:
    v60 = v25;
  }
  if ( v27 >= 0 )
  {
LABEL_38:
    (*(void (__fastcall **)(__int64, __int64, struct IRowset **, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v25 + 48LL))(
      v25,
      1,
      &v57,
      0,
      0,
      0);
    goto LABEL_39;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( `CRecordset::ReleaseRecoveryHRow'::`15'::_bidPtrSA_030_270[0] )
      bidTraceW(
        `CRecordset::ReleaseRecoveryHRow'::`15'::_bidSrcFileA[0],
        276480,
        `CRecordset::ReleaseRecoveryHRow'::`15'::_bidPtrSA_030_270[0],
        0);
LABEL_39:
    v25 = v60;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_8:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)IRowset;
}

```

## disassembly

```asm
0x180004de0  mov     [rsp-8+arg_10], rbx
0x180004de5  mov     [rsp-8+arg_8], rdx
0x180004dea  push    rbp
0x180004deb  push    rsi
0x180004dec  push    rdi
0x180004ded  push    r12
0x180004def  push    r13
0x180004df1  push    r14
0x180004df3  push    r15
0x180004df5  lea     rbp, [rsp-1Fh]
0x180004dfa  sub     rsp, 0A0h
0x180004e01  mov     r12, r9
0x180004e04  mov     r13, r8
0x180004e07  mov     rdi, rcx
0x180004e0a  xor     r15d, r15d
0x180004e0d  mov     [rbp+4Fh+var_68], r15
0x180004e11  mov     [rbp+4Fh+var_60], r15
0x180004e15  mov     byte ptr [rbp+4Fh+arg_0], r15b
0x180004e19  mov     ebx, r15d
0x180004e1c  mov     [rbp+4Fh+var_78], rbx
0x180004e20  cmp     byte ptr [rcx+5E2h], 1
0x180004e27  jz      loc_180005306
0x180004e2d  mov     rax, [rdi+5D0h]
0x180004e34  test    rax, rax
0x180004e37  jz      short loc_180004EA6
0x180004e39  cmp     dword ptr [rax], 1
0x180004e3c  jnz     short loc_180004EA6
0x180004e3e  mov     r14, [rdi+2E8h]
0x180004e45  mov     dword ptr [rbp+4Fh+arg_0], r15d
0x180004e49  cmp     r13, 1
0x180004e4d  jnz     loc_18000544C
0x180004e53  movzx   eax, byte ptr [r12]
0x180004e58  cmp     al, cs:?byBmkFirst@@3EA; uchar byBmkFirst
0x180004e5e  jz      loc_18000531C
0x180004e64  mov     esi, r15d
0x180004e67  cmp     al, cs:?byBmkLast@@3EA; uchar byBmkLast
0x180004e6d  jz      loc_1800053B1
0x180004e73  test    rbx, rbx
0x180004e76  jz      short loc_180004E88
0x180004e78  mov     rax, [rbx]
0x180004e7b  mov     rcx, rbx
0x180004e7e  mov     rax, [rax+10h]
0x180004e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e87  nop
0x180004e88  mov     eax, esi
0x180004e8a  mov     rbx, [rsp+0D0h+arg_10]
0x180004e92  add     rsp, 0A0h
0x180004e99  pop     r15
0x180004e9b  pop     r14
0x180004e9d  pop     r13
0x180004e9f  pop     r12
0x180004ea1  pop     rdi
0x180004ea2  pop     rsi
0x180004ea3  pop     rbp
0x180004ea4  retn
0x180004ea6  mov     rcx, rdi; this
0x180004ea9  call    ?GetRecoveryHRow@CRecordset@@AEAA_KXZ; CRecordset::GetRecoveryHRow(void)
0x180004eae  mov     r14, rax
0x180004eb1  mov     [rbp+4Fh+var_80], rax
0x180004eb5  movsxd  r15, dword ptr [rdi+2D0h]
0x180004ebc  test    dword ptr [rdi+2B8h], 100h
0x180004ec6  jz      loc_1800051C9
0x180004ecc  mov     eax, [rdi+2B8h]
0x180004ed2  bt      eax, 8
0x180004ed6  jb      loc_180005710
0x180004edc  lea     r14, [rdi+2E0h]
0x180004ee3  mov     rcx, r14; this
0x180004ee6  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x180004eeb  mov     esi, eax
0x180004eed  mov     qword ptr [rdi+2E8h], 0
0x180004ef8  test    eax, eax
0x180004efa  js      loc_180005726
0x180004f00  mov     rsi, r15
0x180004f03  neg     rsi
0x180004f06  cmovs   rsi, r15
0x180004f0a  cmp     rsi, [r14+18h]
0x180004f0e  ja      loc_1800050EB
0x180004f14  cmp     byte ptr [r14+60h], 0
0x180004f19  lea     rax, [r14+30h]
0x180004f1d  jz      loc_180005098
0x180004f23  mov     rax, [rax]
0x180004f26  mov     [rbp+4Fh+var_60], rax
0x180004f2a  xor     esi, esi
0x180004f2c  test    esi, esi
0x180004f2e  js      loc_180005777
0x180004f34  movzx   r14d, [rbp+4Fh+arg_20]
0x180004f39  mov     r15, [rbp+4Fh+arg_8]
0x180004f3d  cmp     dword ptr [rdi+78Ch], 1
0x180004f44  jz      loc_1800050DA
0x180004f4a  test    rbx, rbx
0x180004f4d  jz      loc_180004FDA
0x180004f53  mov     ecx, [rdi+2D0h]
0x180004f59  mov     rdx, [rbx]
0x180004f5c  mov     eax, ecx
0x180004f5e  neg     eax
0x180004f60  test    r14b, r14b
0x180004f63  cmovz   eax, ecx
0x180004f66  movsxd  rcx, eax
0x180004f69  mov     r8, [rdi+5D0h]
0x180004f70  mov     rax, [rdx+48h]
0x180004f74  lea     rdx, [rbp+4Fh+var_60]
0x180004f78  mov     [rsp+0D0h+var_90], rdx
0x180004f7d  lea     rdx, [rbp+4Fh+var_68]
0x180004f81  mov     [rsp+0D0h+var_98], rdx
0x180004f86  mov     [rsp+0D0h+var_A0], rcx; unsigned __int8 *
0x180004f8b  mov     [rsp+0D0h+var_A8], r15; unsigned __int64
0x180004f90  mov     [rsp+0D0h+var_B0], r12
0x180004f95  mov     r9, r13
0x180004f98  mov     r8, [r8+8]
0x180004f9c  xor     edx, edx
0x180004f9e  mov     rcx, rbx
0x180004fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa6  mov     r8, [rbp+4Fh+var_68]; unsigned __int64
0x180004faa  lea     rcx, [rbp+4Fh+arg_0]
0x180004fae  mov     [rsp+0D0h+var_B0], rcx; bool *
0x180004fb3  movzx   r9d, r14b; bool
0x180004fb7  mov     edx, eax; int
0x180004fb9  mov     rcx, rdi; this
0x180004fbc  call    ?ProcessFetch@CRecordset@@AEAAJJ_K_NPEA_N0PEAE@Z; CRecordset::ProcessFetch(long,unsigned __int64,bool,bool *,unsigned __int64,uchar *)
0x180004fc1  mov     esi, eax
0x180004fc3  test    eax, eax
0x180004fc5  js      loc_1800059C5
0x180004fcb  cmp     byte ptr [rbp+4Fh+arg_0], 0
0x180004fcf  jz      short loc_180004FFD
0x180004fd1  mov     byte ptr [rbp+4Fh+arg_0], 0
0x180004fd5  jmp     loc_180004F3D
0x180004fda  lea     rcx, [rdi+138h]
0x180004fe1  lea     rdx, [rbp+4Fh+var_78]
0x180004fe5  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x180004fea  mov     esi, eax
0x180004fec  test    eax, eax
0x180004fee  js      loc_180005906
0x180004ff4  mov     rbx, [rbp+4Fh+var_78]
0x180004ff8  jmp     loc_180004F53
0x180004ffd  mov     rdx, [rbp+4Fh+var_80]
0x180005001  mov     [rbp+4Fh+var_58], rdx
0x180005005  mov     eax, 0FFFFFF7Fh
0x18000500a  cmp     rdx, rax
0x18000500d  jz      loc_180004E73
0x180005013  xor     r8d, r8d
0x180005016  mov     ecx, r8d
0x180005019  mov     [rbp+4Fh+arg_0], rcx
0x18000501d  mov     rdx, [rdi+468h]
0x180005024  test    rdx, rdx
0x180005027  jz      short loc_18000505B
0x180005029  mov     r14d, r8d
0x18000502c  test    byte ptr [rdi+470h], 1
0x180005033  jnz     short loc_1800050A1
0x180005035  mov     rax, [rdx]
0x180005038  mov     rcx, rdx
0x18000503b  mov     rax, [rax+8]
0x18000503f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005044  mov     rcx, [rdi+468h]
0x18000504b  xor     r8d, r8d
0x18000504e  mov     [rbp+4Fh+arg_0], rcx
0x180005052  test    r14d, r14d
0x180005055  js      loc_180005988
0x18000505b  mov     rax, [rcx]
0x18000505e  mov     [rsp+0D0h+var_A8], r8
0x180005063  mov     [rsp+0D0h+var_B0], r8
0x180005068  xor     r9d, r9d
0x18000506b  lea     r8, [rbp+4Fh+var_58]
0x18000506f  mov     edx, 1
0x180005074  mov     rax, [rax+30h]
0x180005078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000507d  mov     rcx, [rbp+4Fh+arg_0]
0x180005081  test    rcx, rcx
0x180005084  jz      short loc_180005093
0x180005086  mov     rax, [rcx]
0x180005089  mov     rax, [rax+10h]
0x18000508d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005092  nop
0x180005093  jmp     loc_180004E73
0x180005098  lea     rax, [r14+28h]
0x18000509c  jmp     loc_180004F23
0x1800050a1  test    edx, edx
0x1800050a3  jz      short loc_18000504E
0x1800050a5  mov     [rbp+4Fh+arg_0], r8
0x1800050a9  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800050b0  mov     rcx, [rax+50h]
0x1800050b4  mov     rax, [rcx]
0x1800050b7  lea     r9, [rbp+4Fh+arg_0]
0x1800050bb  lea     r8, IID_IRowset
0x1800050c2  mov     rax, [rax+28h]
0x1800050c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050cb  mov     r14d, eax
0x1800050ce  mov     rcx, [rbp+4Fh+arg_0]
0x1800050d2  xor     r8d, r8d
0x1800050d5  jmp     loc_180005052
0x1800050da  xor     r8d, r8d
0x1800050dd  mov     [rbp+4Fh+var_68], r8
0x1800050e1  mov     eax, 40EC6h
0x1800050e6  jmp     loc_180004FAA
0x1800050eb  mov     [rbp+4Fh+Src], 0
0x1800050f3  mov     rax, [r14]
0x1800050f6  mov     ecx, [rax+2B8h]
0x1800050fc  bt      ecx, 8
0x180005100  jb      loc_1800057FD
0x180005106  lea     r15, [r14+60h]
0x18000510a  mov     byte ptr [r15], 0
0x18000510e  mov     rcx, r14; this
0x180005111  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x180005116  lea     rax, [rsi+1]
0x18000511a  cmp     rax, rsi
0x18000511d  jnb     short loc_180005133
0x18000511f  cmp     byte ptr [r15], 0
0x180005123  jnz     loc_1800058AB
0x180005129  mov     esi, 800A0E89h
0x18000512e  jmp     loc_180004F2C
0x180005133  mov     [rbp+4Fh+var_58], 0
0x18000513b  mov     ecx, 8
0x180005140  mul     rcx
0x180005143  mov     [rbp+4Fh+var_58], rax
0x180005147  test    rdx, rdx
0x18000514a  jnz     short loc_18000511F
0x18000514c  mov     r8, rax
0x18000514f  mov     edx, 0A00000h
0x180005154  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000515b  call    cs:__imp_MpHeapAlloc
0x180005162  nop     dword ptr [rax+rax+00h]
0x180005167  mov     [r14+28h], rax
0x18000516b  movzx   ecx, byte ptr [r15]
0x18000516f  test    rax, rax
0x180005172  jz      loc_18000582F
0x180005178  mov     [r14+18h], rsi
0x18000517c  test    cl, cl
0x18000517e  jnz     loc_180005863
0x180005184  cmp     byte ptr [r15], 0
0x180005188  jz      loc_180004F14
0x18000518e  mov     r8, [rbp+4Fh+var_58]
0x180005192  mov     edx, 0A00000h
0x180005197  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000519e  call    cs:__imp_MpHeapAlloc
0x1800051a5  nop     dword ptr [rax+rax+00h]
0x1800051aa  mov     [r14+30h], rax
0x1800051ae  test    rax, rax
0x1800051b1  jnz     loc_180004F14
0x1800051b7  mov     rcx, r14; this
0x1800051ba  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x1800051bf  mov     esi, 8007000Eh
0x1800051c4  jmp     loc_180004F2C
0x1800051c9  xor     edx, edx; bool
0x1800051cb  mov     rcx, rdi; this
0x1800051ce  call    ?ReleaseAffectedGroup@CRecordset@@AEAAJ_N@Z; CRecordset::ReleaseAffectedGroup(bool)
0x1800051d3  mov     esi, eax
0x1800051d5  test    eax, eax
0x1800051d7  jns     loc_180004ECC
0x1800051dd  test    byte ptr cs:_bidGblFlags, 2
0x1800051e4  jz      loc_180005A4D
0x1800051ea  lea     rcx, [rdi+618h]; this
0x1800051f1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800051f6  cmp     eax, 0FFFFFFFFh
0x1800051f9  jz      loc_1800056EB
0x1800051ff  lea     rcx, [rdi+618h]; this
0x180005206  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000520b  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180005212  mov     dword ptr [rsp+0D0h+var_A8], 2584h
0x18000521a  mov     dword ptr [rsp+0D0h+var_B0], esi
0x18000521e  mov     r9d, eax
0x180005221  lea     r8, aCrecordsetPrep_0; "<CRecordset::PrepareForFetch|ADO|ERR> %"...
0x180005228  mov     edx, 961009h
0x18000522d  call    _bidTraceW
0x180005232  jmp     loc_18000577B
0x180005237  test    rbx, rbx
0x18000523a  jnz     short loc_18000525A
0x18000523c  lea     rcx, [rdi+138h]
0x180005243  lea     rdx, [rbp+4Fh+var_78]
0x180005247  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x18000524c  mov     esi, eax
0x18000524e  test    eax, eax
0x180005250  js      loc_180005642
0x180005256  mov     rbx, [rbp+4Fh+var_78]
0x18000525a  mov     rax, [rbx]
0x18000525d  mov     rdx, [rdi+5D0h]
0x180005264  lea     rcx, [rbp+4Fh+arg_0]
0x180005268  mov     r9, r12
0x18000526b  mov     r8, r13
0x18000526e  mov     rax, [rax+40h]
0x180005272  mov     rdx, [rdx+8]
0x180005276  mov     [rsp+0D0h+var_A0], rcx
0x18000527b  cmp     byte ptr [rdi+4E8h], 1
0x180005282  jnz     loc_180005546
0x180005288  mov     rcx, qword ptr [rbp+4Fh+var_50]
0x18000528c  mov     [rsp+0D0h+var_A8], rcx
0x180005291  mov     rcx, qword ptr [rbp+4Fh+var_50+8]
0x180005295  mov     [rsp+0D0h+var_B0], rcx
0x18000529a  mov     rcx, rbx
0x18000529d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a2  mov     esi, eax
0x1800052a4  test    eax, eax
0x1800052a6  jz      loc_1800055C0
0x1800052ac  test    byte ptr cs:_bidGblFlags, 2
0x1800052b3  jz      loc_1800054EE
0x1800052b9  lea     rcx, [rdi+618h]; this
0x1800052c0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800052c5  cmp     eax, 0FFFFFFFFh
0x1800052c8  jz      loc_1800056C7
0x1800052ce  lea     rcx, [rdi+618h]; this
0x1800052d5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800052da  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
  ... truncated ...
```
