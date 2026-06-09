# CConnection::_Close(void)

- ea: `0x180001c98`
- end: `0x180002837`
- name: `?_Close@CConnection@@QEAAJXZ`
- size: `2975`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `3`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180001900`
- `0x180050920`
- `0x1800672c0`

## callees

- `0x18000160c`
- `0x18000174c`
- `0x180001b10`
- `0x180001c98`
- `0x180002840`
- `0x18000f7c0`
- `0x180012824`
- `0x180026c74`
- `0x180026cc0`
- `0x18004c520`
- `0x180051340`
- `0x180057c10`
- `0x18005b724`
- `0x18005c76c`
- `0x180069aec`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cb374`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001ded`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001ded`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001ef1`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001ef1`
- `MSDART!UMSEnterCSWraper` at `0x180001cf3`
- `MSDART!UMSEnterCSWraper` at `0x180001d7f`
- `MSDART!UMSEnterCSWraper` at `0x180001cf3`
- `MSDART!UMSEnterCSWraper` at `0x180001d7f`
- `MSDART!MpHeapAlloc` at `0x180001e41`
- `MSDART!MpHeapAlloc` at `0x180001e41`
- `MSDART!MpHeapFree` at `0x180001f74`
- `MSDART!MpHeapFree` at `0x180002009`
- `MSDART!MpHeapFree` at `0x1800025d5`
- `MSDART!MpHeapFree` at `0x18000264a`
- `MSDART!MpHeapFree` at `0x180002667`
- `MSDART!MpHeapFree` at `0x180001f74`
- `MSDART!MpHeapFree` at `0x180002009`
- `MSDART!MpHeapFree` at `0x1800025d5`
- `MSDART!MpHeapFree` at `0x18000264a`
- `MSDART!MpHeapFree` at `0x180002667`
- `KERNEL32!CloseHandle` at `0x180001d31`
- `KERNEL32!CloseHandle` at `0x180001d31`
- `KERNEL32!GetCurrentThreadId` at `0x180001d0e`
- `KERNEL32!GetCurrentThreadId` at `0x180001d0e`
- `KERNEL32!LeaveCriticalSection` at `0x180001d69`
- `KERNEL32!LeaveCriticalSection` at `0x180001dc1`
- `KERNEL32!LeaveCriticalSection` at `0x180001d69`
- `KERNEL32!LeaveCriticalSection` at `0x180001dc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnection::_Close(struct IUnknown *this)
{
  struct IUnknown *v1; // rdi
  unsigned int v2; // r15d
  struct IUnknown *v3; // rsi
  int lpVtbl; // ebx
  struct IUnknownVtbl *v5; // rcx
  struct IUnknownVtbl *v6; // rcx
  unsigned int v7; // esi
  unsigned int i; // ebx
  struct IUnknownVtbl *v9; // rcx
  unsigned __int64 v10; // rsi
  CReaderWriterLock3AR *v11; // r13
  unsigned int Count; // eax
  unsigned int v13; // r12d
  int Element; // ebx
  _QWORD *v15; // r14
  _QWORD *v16; // rax
  CStdCollection *v17; // rdi
  size_t v18; // rax
  unsigned int BidObjectID; // eax
  __int64 v20; // rdx
  unsigned int v21; // r12d
  __int64 v22; // r13
  unsigned int n; // esi
  __int64 v24; // rdx
  unsigned int j; // ebx
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // r15d
  _QWORD *v29; // r14
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v33; // eax
  unsigned int v34; // r14d
  unsigned int v35; // eax
  unsigned int v36; // r15d
  unsigned int m; // r14d
  __int64 v38; // r13
  struct IUnknownVtbl *v39; // rcx
  struct IUnknownVtbl *v40; // rcx
  struct IUnknownVtbl *v41; // rcx
  struct IUnknownVtbl *v42; // rcx
  struct IUnknownVtbl *v43; // rcx
  struct IUnknownVtbl *v44; // rcx
  struct IUnknownVtbl *v45; // rcx
  struct IUnknownVtbl *v46; // rcx
  int v47; // eax
  unsigned int v48; // esi
  unsigned int v49; // eax
  unsigned int v50; // r15d
  unsigned int k; // r14d
  CCommand *v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // r9
  __int64 v55; // rcx
  struct IUnknownVtbl *v56; // r9
  int v57; // r8d
  unsigned int v58; // ecx
  ULONG (__stdcall *AddRef)(IUnknown *); // rdx
  struct IUnknownVtbl *v60; // r9
  int v61; // r8d
  unsigned int v62; // ecx
  ULONG (__stdcall *v63)(IUnknown *); // rdx
  __int64 v64; // r10
  __int64 v65; // rcx
  struct IUnknownVtbl *v66; // r9
  int ii; // r8d
  struct IUnknown *v68; // rax
  int v69; // r8d
  struct IUnknownVtbl *v70; // r9
  int jj; // r8d
  struct IUnknown *v72; // rax
  int v73; // r8d
  int v75; // [rsp+20h] [rbp-E0h]
  int v76; // [rsp+20h] [rbp-E0h]
  int v77; // [rsp+28h] [rbp-D8h]
  int v78; // [rsp+28h] [rbp-D8h]
  unsigned int v79; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v80; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v81; // [rsp+40h] [rbp-C0h] BYREF
  int v82; // [rsp+44h] [rbp-BCh] BYREF
  int v83; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v84; // [rsp+50h] [rbp-B0h]
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+60h] [rbp-A0h]
  CStdCollection *v87; // [rsp+68h] [rbp-98h]
  struct IUnknown *v88; // [rsp+70h] [rbp-90h]
  char v89[8]; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v90; // [rsp+88h] [rbp-78h]
  __int16 v91; // [rsp+98h] [rbp-68h]
  int *v92; // [rsp+A0h] [rbp-60h]
  int *v93; // [rsp+160h] [rbp+60h]
  int v94; // [rsp+170h] [rbp+70h]

  v1 = this;
  v88 = this;
  v2 = 0;
  v79 = 0;
  v83 = 0;
  v80 = 0;
  v82 = 0;
  v86 = 0;
  v3 = this + 150;
  UMSEnterCSWraper(&this[150]);
  if ( v1[131].lpVtbl )
  {
    lpVtbl = (int)v1[132].lpVtbl;
    if ( lpVtbl != GetCurrentThreadId() )
      WaitForMultipleObjectsWithMessageLoop(v1[131].lpVtbl);
    CloseHandle(v1[131].lpVtbl);
    v1[131].lpVtbl = 0;
  }
  v5 = v1[129].lpVtbl;
  if ( v5 )
    (*((void (__fastcall **)(struct IUnknownVtbl *))v5->QueryInterface + 25))(v5);
  v6 = v3->lpVtbl;
  --LODWORD(v6[2].QueryInterface);
  LeaveCriticalSection((LPCRITICAL_SECTION)&v6->AddRef);
  UMSEnterCSWraper(&v1[153]);
  BYTE1(v1[127].lpVtbl) = 0;
  v7 = (unsigned int)v1[128].lpVtbl;
  for ( i = 0; i < v7; ++i )
    ((void (__fastcall *)(struct IUnknown *))v1->lpVtbl[6].AddRef)(v1);
  v9 = v1[153].lpVtbl;
  --LODWORD(v9[2].QueryInterface);
  LeaveCriticalSection((LPCRITICAL_SECTION)&v9->AddRef);
  v87 = (CStdCollection *)&v1[68];
  v10 = 0;
  v84 = 0;
  v81 = 0;
  v11 = (CReaderWriterLock3AR *)&v1[77];
  CReaderWriterLock3AR::ReadLock((CReaderWriterLock3AR *)&v1[77]);
  Count = CStdCollection::GetCount((CStdCollection *)&v1[68]);
  v13 = Count;
  if ( Count )
  {
    Size = 0;
    Element = ULongLongMult(Count, 8u, &Size);
    LODWORD(v15) = 0;
    if ( !Element )
    {
      v16 = (_QWORD *)MpHeapAlloc(g_hHeapHandle, 10485760, Size);
      v15 = v16;
      if ( v16 )
      {
        memset_0(v16, 0, Size);
        if ( v13 )
        {
          v17 = v87;
          do
          {
            Size = 0;
            Element = CStdCollection::GetElement(v17, (unsigned int)v10, (struct CStdComObjectRoot **)&Size);
            v18 = Size;
            if ( Size )
              v18 = Size - 32;
            v15[v10] = v18;
            if ( v18
              && (*(_DWORD *)(v18 + 80)
               || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v15[v10] + 32LL) + 80LL))(v15[v10] + 32LL)) )
            {
              v15[v10] = 0;
            }
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < v13 );
          v1 = v88;
        }
        v10 = (unsigned __int64)v15;
        v84 = v15;
        v2 = v13;
        v81 = v13;
        LODWORD(v15) = v13;
      }
      else
      {
        Element = -2147024882;
      }
    }
  }
  else
  {
    LODWORD(v15) = 0;
    Element = 0;
  }
  CReaderWriterLock3AR::ReadUnlock(v11);
  if ( Element < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_30:
      v21 = v79;
LABEL_31:
      v22 = v80;
      goto LABEL_32;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
      v77 = 4039;
      v20 = 4135945;
LABEL_29:
      bidTraceW(
        off_18012A1C0[0],
        v20,
        L"<CConnection::_Close|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        Element,
        v77);
      goto LABEL_30;
    }
    v75 = 4039;
    v24 = 4135945;
    goto LABEL_37;
  }
  if ( (_DWORD)v15 )
  {
    for ( j = 0; j < v2; ++j )
    {
      v26 = *(_QWORD *)(v10 + 8LL * j);
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 200LL))(v26);
        v27 = *(_QWORD *)(v10 + 8LL * j) + 32LL;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 88LL))(v27);
      }
    }
    if ( v10 )
      MpHeapFree(g_hHeapHandle, v10);
    v10 = 0;
    v84 = 0;
  }
  Element = CopyCollection_CRecordset_((CCollectionList **)&v1[85], &v80, &v79);
  if ( Element < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_30;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
      v77 = 4064;
      v20 = 4161545;
      goto LABEL_29;
    }
    v75 = 4064;
    v24 = 4161545;
LABEL_37:
    bidTraceW(
      off_18012A1C0[0],
      v24,
      L"<CConnection::_Close|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)Element,
      v75);
    goto LABEL_30;
  }
  Element = 0;
  v21 = v79;
  if ( !v79 )
  {
LABEL_69:
    v33 = CopyCollection_CRecord_((CStdCollection *)&v1[96]);
    v34 = v33;
    if ( v33 < 0 )
    {
      Element = v33;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) == -1 )
        {
          bidTraceW(off_18012A1C0[0], 4185097, L"<CConnection::_Close|ADO|ERR> 0x%08x{HRESULT} line %d\n", v34, 4087);
        }
        else
        {
          v35 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
          bidTraceW(
            off_18012A1C0[0],
            4185097,
            L"<CConnection::_Close|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v35,
            Element,
            4087);
        }
      }
      goto LABEL_31;
    }
    v36 = v83;
    if ( !v83 )
    {
LABEL_89:
      v39 = v1[122].lpVtbl;
      if ( v39 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v39->QueryInterface + 2))(v39);
        v1[122].lpVtbl = 0;
      }
      v40 = v1[123].lpVtbl;
      if ( v40 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v40->QueryInterface + 2))(v40);
        v1[123].lpVtbl = 0;
      }
      v41 = v1[126].lpVtbl;
      if ( v41 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v41->QueryInterface + 2))(v41);
        v1[126].lpVtbl = 0;
      }
      v42 = v1[125].lpVtbl;
      if ( v42 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v42->QueryInterface + 2))(v42);
        v1[125].lpVtbl = 0;
      }
      v43 = v1[36].lpVtbl;
      if ( v43 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v43->QueryInterface + 2))(v43);
        v1[36].lpVtbl = 0;
      }
      v44 = v1[37].lpVtbl;
      if ( v44 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v44->QueryInterface + 2))(v44);
        v1[37].lpVtbl = 0;
      }
      v45 = v1[121].lpVtbl;
      if ( v45 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v45->QueryInterface + 2))(v45);
        v1[121].lpVtbl = 0;
      }
      BYTE4(v1[48].lpVtbl) = 0;
      BYTE6(v1[48].lpVtbl) = 0;
      LODWORD(v1[7].lpVtbl) = 1;
      v46 = v1[129].lpVtbl;
      if ( v46 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v46->QueryInterface + 2))(v46);
        v1[129].lpVtbl = 0;
      }
      v47 = CopyCollection_CCommand_((CStdCollection *)&v1[68]);
      v48 = v47;
      if ( v47 >= 0 )
      {
        v50 = v81;
        v10 = (unsigned __int64)v84;
        if ( v81 )
        {
          for ( k = 0; k < v50; ++k )
          {
            v52 = *(CCommand **)(v10 + 8LL * k);
            if ( v52 )
            {
              Element = CCommand::Close(v52);
              v53 = *(_QWORD *)(v10 + 8LL * k) + 32LL;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 88LL))(v53);
              if ( Element < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) == -1 )
                  {
                    bidTraceW(off_18012A1C0[0], 4244489, L"<CConnection::_Close|ADO|ERR>  line %d\n", 4145);
                  }
                  else
                  {
                    v54 = (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
                    bidTraceW(off_18012A1C0[0], 4244489, L"<CConnection::_Close|ADO|ERR> %u#, line %d\n", v54, 4145);
                  }
                }
                goto LABEL_30;
              }
            }
          }
          if ( v10 )
            MpHeapFree(g_hHeapHandle, v10);
          v10 = 0;
          v21 = v79;
        }
        LODWORD(v1[7].lpVtbl) = 0;
        HIDWORD(v1[64].lpVtbl) = 1;
        CStdCollection::DestroyList((CStdCollection *)&v1[54], 0);
        LODWORD(v1[155].lpVtbl) = -1;
        WORD2(v1[155].lpVtbl) = -1;
      }
      else
      {
        Element = v47;
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) == -1 )
          {
            bidTraceW(off_18012A1C0[0], 4233225, L"<CConnection::_Close|ADO|ERR> 0x%08x{HRESULT} line %d\n", v48, 4134);
          }
          else
          {
            v49 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
            bidTraceW(
              off_18012A1C0[0],
              4233225,
              L"<CConnection::_Close|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v49,
              Element,
              4134);
          }
        }
        v10 = (unsigned __int64)v84;
      }
      goto LABEL_31;
    }
    for ( m = 0; ; ++m )
    {
      if ( m >= v36 )
      {
        v21 = v79;
        goto LABEL_89;
      }
      v38 = v86;
      Element = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v86 + 8LL * m) + 224LL))(*(_QWORD *)(v86 + 8LL * m));
      if ( Element < 0 )
        break;
      Element = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v38 + 8LL * m) + 80LL))(
                  *(_QWORD *)(v38 + 8LL * m),
                  0);
      if ( Element < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_30;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
          v77 = 4095;
          v20 = 4193289;
          goto LABEL_29;
        }
        v75 = 4095;
        v24 = 4193289;
        goto LABEL_37;
      }
    }
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_30;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
      v77 = 4094;
      v20 = 4192265;
      goto LABEL_29;
    }
    v75 = 4094;
    v24 = 4192265;
    goto LABEL_37;
  }
  v28 = 0;
  v82 = 0;
  v22 = v80;
  while ( 1 )
  {
    if ( v28 >= v21 )
      goto LABEL_69;
    v29 = *(_QWORD **)(v22 + 8LL * v28);
    if ( !v29 )
      goto LABEL_58;
    Element = (*(__int64 (__fastcall **)(_QWORD))(*v29 + 720LL))(*(_QWORD *)(v22 + 8LL * v28));
    if ( Element < 0 )
      break;
    Element = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64))(*v29 + 696LL))(v29, 0, 1);
    if ( Element < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_32;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) != -1 )
      {
        v30 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
        v78 = 4075;
        v31 = 4172809;
LABEL_66:
        bidTraceW(
          off_18012A1C0[0],
          v31,
          L"<CConnection::_Close|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v30,
          Element,
          v78);
        goto LABEL_32;
      }
      v76 = 4075;
      v32 = 4172809;
      goto LABEL_68;
    }
    (*(void (__fastcall **)(_QWORD *))(v29[4] + 88LL))(v29 + 4);
LABEL_58:
    v82 = ++v28;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_32;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]) != -1 )
  {
    v30 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v1[32]);
    v78 = 4074;
    v31 = 4171785;
    goto LABEL_66;
  }
  v76 = 4074;
  v32 = 4171785;
LABEL_68:
  bidTraceW(
    off_18012A1C0[0],
    v32,
    L"<CConnection::_Close|ADO|ERR> 0x%08x{HRESULT} line %d\n",
    (unsigned int)Element,
    v76);
LABEL_32:
  if ( v10 )
    MpHeapFree(g_hHeapHandle, v10);
  if ( v22 )
  {
    for ( n = v82; n < v21; ++n )
    {
      v55 = *(_QWORD *)(v22 + 8LL * n);
      if ( v55 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v55 + 32) + 88LL))(v55 + 32);
    }
    MpHeapFree(g_hHeapHandle, v22);
  }
  if ( v86 )
    MpHeapFree(g_hHeapHandle, v86);
  v56 = v1[35].lpVtbl;
  v57 = 0;
  v58 = 0;
  if ( SLODWORD(v56->Release) > 0 )
  {
    do
    {
      AddRef = v56->AddRef;
      if ( SLODWORD(v56->Release) >= 2 )
        AddRef = (ULONG (__stdcall *)(IUnknown *))*((_QWORD *)AddRef + v58);
      if ( AddRef && *((_QWORD *)AddRef + 1) )
        ++v57;
      ++v58;
    }
    while ( (signed int)v58 < SLODWORD(v56->Release) );
    if ( v57 )
      goto LABEL_148;
  }
  v60 = v1[34].lpVtbl;
  v61 = 0;
  v62 = 0;
  if ( SLODWORD(v60->Release) > 0 )
  {
    do
    {
      v63 = v60->AddRef;
      if ( SLODWORD(v60->Release) >= 2 )
        v63 = (ULONG (__stdcall *)(IUnknown *))*((_QWORD *)v63 + v62);
      if ( v63 && *((_QWORD *)v63 + 1) )
        ++v61;
      ++v62;
    }
    while ( (signed int)v62 < SLODWORD(v60->Release) );
    if ( v61 )
    {
LABEL_148:
      CNfyContext::CNfyContext((CNfyContext *)v89, v1, 8, 0);
      v83 = ((Element >> 31) & 1) + 1;
      v82 = 0;
      v81 = 0;
      v91 = 16387;
      v92 = &v83;
      v93 = &v83;
      Element = 0;
      if ( !(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v1[34].lpVtbl)
        || (Element = CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                        v64,
                        &v82,
                        v89),
            Element >= 0) )
      {
        if ( (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(v1[35].lpVtbl) )
        {
          v90 = v1 + 1;
          v94 = 1;
          Element = CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                      v65,
                      &v81,
                      v89);
        }
      }
      v66 = v1[34].lpVtbl;
      for ( ii = 0; ii < SLODWORD(v66->Release); ii = v69 + 1 )
      {
        v68 = CADOComDynamicUnkArray::GetAt((CADOComDynamicUnkArray *)&v66->AddRef, ii);
        if ( v68 )
          LODWORD(v68[3].lpVtbl) = -1;
      }
      v70 = v1[35].lpVtbl;
      for ( jj = 0; jj < SLODWORD(v70->Release); jj = v73 + 1 )
      {
        v72 = CADOComDynamicUnkArray::GetAt((CADOComDynamicUnkArray *)&v70->AddRef, jj);
        if ( v72 )
          LODWORD(v72[3].lpVtbl) = -1;
      }
      CNfyContext::~CNfyContext((CNfyContext *)v89);
    }
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180001c98  push    rbp
0x180001c9a  push    rbx
0x180001c9b  push    rsi
0x180001c9c  push    rdi
0x180001c9d  push    r12
0x180001c9f  push    r13
0x180001ca1  push    r14
0x180001ca3  push    r15
0x180001ca5  lea     rbp, [rsp-0A8h]
0x180001cad  sub     rsp, 1A8h
0x180001cb4  mov     rax, cs:__security_cookie
0x180001cbb  xor     rax, rsp
0x180001cbe  mov     [rbp+0E0h+var_50], rax
0x180001cc5  mov     rdi, rcx
0x180001cc8  mov     [rsp+1E0h+var_170], rcx
0x180001ccd  xor     r15d, r15d
0x180001cd0  mov     [rsp+1E0h+var_1B0], r15d
0x180001cd5  mov     [rsp+1E0h+var_198], r15d
0x180001cda  mov     [rsp+1E0h+var_1A8], r15
0x180001cdf  mov     [rsp+1E0h+var_19C], r15d
0x180001ce4  mov     [rsp+1E0h+var_180], r15
0x180001ce9  lea     rsi, [rcx+4B0h]
0x180001cf0  mov     rcx, rsi
0x180001cf3  call    cs:__imp_UMSEnterCSWraper
0x180001cfa  nop     dword ptr [rax+rax+00h]
0x180001cff  cmp     [rdi+418h], r15
0x180001d06  jz      short loc_180001D44
0x180001d08  mov     ebx, [rdi+420h]
0x180001d0e  call    cs:__imp_GetCurrentThreadId
0x180001d15  nop     dword ptr [rax+rax+00h]
0x180001d1a  cmp     ebx, eax
0x180001d1c  jz      short loc_180001D2A
0x180001d1e  mov     rcx, [rdi+418h]; void *
0x180001d25  call    ?WaitForMultipleObjectsWithMessageLoop@@YAHPEAX@Z; WaitForMultipleObjectsWithMessageLoop(void *)
0x180001d2a  mov     rcx, [rdi+418h]; hObject
0x180001d31  call    cs:__imp_CloseHandle
0x180001d38  nop     dword ptr [rax+rax+00h]
0x180001d3d  mov     [rdi+418h], r15
0x180001d44  mov     rcx, [rdi+408h]
0x180001d4b  test    rcx, rcx
0x180001d4e  jz      short loc_180001D5F
0x180001d50  mov     rax, [rcx]
0x180001d53  mov     rax, [rax+0C8h]
0x180001d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d5f  mov     rcx, [rsi]
0x180001d62  dec     dword ptr [rcx+30h]
0x180001d65  add     rcx, 8; lpCriticalSection
0x180001d69  call    cs:__imp_LeaveCriticalSection
0x180001d70  nop     dword ptr [rax+rax+00h]
0x180001d75  lea     r14, [rdi+4C8h]
0x180001d7c  mov     rcx, r14
0x180001d7f  call    cs:__imp_UMSEnterCSWraper
0x180001d86  nop     dword ptr [rax+rax+00h]
0x180001d8b  mov     [rdi+3F9h], r15b
0x180001d92  mov     esi, [rdi+400h]
0x180001d98  mov     ebx, r15d
0x180001d9b  test    esi, esi
0x180001d9d  jz      short loc_180001DB7
0x180001d9f  mov     rax, [rdi]
0x180001da2  mov     rcx, rdi
0x180001da5  mov     rax, [rax+98h]
0x180001dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001db1  inc     ebx
0x180001db3  cmp     ebx, esi
0x180001db5  jb      short loc_180001D9F
0x180001db7  mov     rcx, [r14]
0x180001dba  dec     dword ptr [rcx+30h]
0x180001dbd  add     rcx, 8; lpCriticalSection
0x180001dc1  call    cs:__imp_LeaveCriticalSection
0x180001dc8  nop     dword ptr [rax+rax+00h]
0x180001dcd  lea     rbx, [rdi+220h]
0x180001dd4  mov     [rsp+1E0h+var_178], rbx
0x180001dd9  mov     rsi, r15
0x180001ddc  mov     [rsp+1E0h+var_190], r15
0x180001de1  mov     [rsp+1E0h+var_1A0], r15d
0x180001de6  lea     r13, [rbx+48h]
0x180001dea  mov     rcx, r13
0x180001ded  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x180001df4  nop     dword ptr [rax+rax+00h]
0x180001df9  mov     rcx, rbx; this
0x180001dfc  call    ?GetCount@CStdCollection@@UEAAKXZ; CStdCollection::GetCount(void)
0x180001e01  mov     r12d, eax
0x180001e04  test    eax, eax
0x180001e06  jz      loc_180001EE9
0x180001e0c  mov     [rsp+1E0h+Size], r15
0x180001e11  mov     ecx, r12d; unsigned __int64
0x180001e14  lea     r8, [rsp+1E0h+Size]; unsigned __int64 *
0x180001e19  mov     edx, 8; unsigned __int64
0x180001e1e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180001e23  mov     ebx, eax
0x180001e25  xor     r14d, r14d
0x180001e28  test    eax, eax
0x180001e2a  jnz     loc_180001EEE
0x180001e30  mov     r8, [rsp+1E0h+Size]
0x180001e35  mov     edx, 0A00000h
0x180001e3a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180001e41  call    cs:__imp_MpHeapAlloc
0x180001e48  nop     dword ptr [rax+rax+00h]
0x180001e4d  mov     r14, rax
0x180001e50  test    rax, rax
0x180001e53  jnz     short loc_180001E5F
0x180001e55  mov     ebx, 8007000Eh
0x180001e5a  jmp     loc_180001EEE
0x180001e5f  mov     r8, [rsp+1E0h+Size]; Size
0x180001e64  xor     edx, edx; Val
0x180001e66  mov     rcx, r14; void *
0x180001e69  call    memset_0
0x180001e6e  test    r12d, r12d
0x180001e71  jz      short loc_180001ED4
0x180001e73  mov     rdi, [rsp+1E0h+var_178]
0x180001e78  mov     [rsp+1E0h+Size], r15
0x180001e7d  lea     r8, [rsp+1E0h+Size]; struct CStdComObjectRoot **
0x180001e82  mov     edx, esi; unsigned __int64
0x180001e84  mov     rcx, rdi; this
0x180001e87  call    ?GetElement@CStdCollection@@QEAAJ_KPEAPEAVCStdComObjectRoot@@@Z; CStdCollection::GetElement(unsigned __int64,CStdComObjectRoot * *)
0x180001e8c  mov     ebx, eax
0x180001e8e  mov     rax, [rsp+1E0h+Size]
0x180001e93  test    rax, rax
0x180001e96  jz      short loc_180001E9C
0x180001e98  add     rax, 0FFFFFFFFFFFFFFE0h
0x180001e9c  mov     [r14+rsi*8], rax
0x180001ea0  test    rax, rax
0x180001ea3  jz      short loc_180001EC8
0x180001ea5  mov     eax, [rax+50h]
0x180001ea8  test    eax, eax
0x180001eaa  jnz     short loc_180001EC4
0x180001eac  mov     rcx, [r14+rsi*8]
0x180001eb0  add     rcx, 20h ; ' '
0x180001eb4  mov     rax, [rcx]
0x180001eb7  mov     rax, [rax+50h]
0x180001ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec0  test    eax, eax
0x180001ec2  jnz     short loc_180001EC8
0x180001ec4  mov     [r14+rsi*8], r15
0x180001ec8  inc     esi
0x180001eca  cmp     esi, r12d
0x180001ecd  jb      short loc_180001E78
0x180001ecf  mov     rdi, [rsp+1E0h+var_170]
0x180001ed4  mov     rsi, r14
0x180001ed7  mov     [rsp+1E0h+var_190], r14
0x180001edc  mov     r15d, r12d
0x180001edf  mov     [rsp+1E0h+var_1A0], r12d
0x180001ee4  mov     r14d, r12d
0x180001ee7  jmp     short loc_180001EEE
0x180001ee9  xor     r14d, r14d
0x180001eec  xor     ebx, ebx
0x180001eee  mov     rcx, r13
0x180001ef1  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x180001ef8  nop     dword ptr [rax+rax+00h]
0x180001efd  or      r12d, 0FFFFFFFFh
0x180001f01  xor     r13d, r13d
0x180001f04  test    ebx, ebx
0x180001f06  jns     loc_180001FB7
0x180001f0c  test    byte ptr cs:_bidGblFlags, 2
0x180001f13  jz      short loc_180001F58
0x180001f15  lea     r14, [rdi+100h]
0x180001f1c  mov     rcx, r14; this
0x180001f1f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180001f24  cmp     eax, r12d
0x180001f27  jz      short loc_180001F92
0x180001f29  mov     rcx, r14; this
0x180001f2c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180001f31  mov     [rsp+1E0h+var_1B8], 0FC7h
0x180001f39  mov     edx, 3F1C09h
0x180001f3e  lea     r8, aCconnectionClo_1; "<CConnection::_Close|ADO|ERR> %u#,0x%08"...
0x180001f45  mov     r9d, eax
0x180001f48  mov     [rsp+1E0h+var_1C0], ebx
0x180001f4c  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180001f53  call    _bidTraceW
0x180001f58  mov     r12d, [rsp+1E0h+var_1B0]
0x180001f5d  mov     r13, [rsp+1E0h+var_1A8]
0x180001f62  xor     r14d, r14d
0x180001f65  test    rsi, rsi
0x180001f68  jz      short loc_180001F80
0x180001f6a  mov     rdx, rsi
0x180001f6d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180001f74  call    cs:__imp_MpHeapFree
0x180001f7b  nop     dword ptr [rax+rax+00h]
0x180001f80  test    r13, r13
0x180001f83  jz      loc_180002656
0x180001f89  mov     esi, [rsp+1E0h+var_19C]
0x180001f8d  jmp     loc_18000263B
0x180001f92  mov     [rsp+1E0h+var_1C0], 0FC7h
0x180001f9a  mov     edx, 3F1C09h
0x180001f9f  lea     r8, aCconnectionClo_0; "<CConnection::_Close|ADO|ERR> 0x%08x{HR"...
0x180001fa6  mov     r9d, ebx
0x180001fa9  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180001fb0  call    _bidTraceW
0x180001fb5  jmp     short loc_180001F58
0x180001fb7  test    r14d, r14d
0x180001fba  jz      short loc_18000201D
0x180001fbc  mov     ebx, r13d
0x180001fbf  test    r15d, r15d
0x180001fc2  jz      short loc_180001FFA
0x180001fc4  mov     r14d, ebx
0x180001fc7  mov     rcx, [rsi+r14*8]
0x180001fcb  test    rcx, rcx
0x180001fce  jz      short loc_180001FF3
0x180001fd0  mov     rax, [rcx]
0x180001fd3  mov     rax, [rax+0C8h]
0x180001fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fdf  mov     rcx, [rsi+r14*8]
0x180001fe3  add     rcx, 20h ; ' '
0x180001fe7  mov     rax, [rcx]
0x180001fea  mov     rax, [rax+58h]
0x180001fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff3  inc     ebx
0x180001ff5  cmp     ebx, r15d
0x180001ff8  jb      short loc_180001FC4
0x180001ffa  test    rsi, rsi
0x180001ffd  jz      short loc_180002015
0x180001fff  mov     rdx, rsi
0x180002002  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180002009  call    cs:__imp_MpHeapFree
0x180002010  nop     dword ptr [rax+rax+00h]
0x180002015  mov     rsi, r13
0x180002018  mov     [rsp+1E0h+var_190], r13
0x18000201d  lea     rcx, [rdi+2A8h]; this
0x180002024  lea     r8, [rsp+1E0h+var_1B0]
0x180002029  lea     rdx, [rsp+1E0h+var_1A8]
0x18000202e  call    _CopyCollection_CRecordset_
0x180002033  mov     ebx, eax
0x180002035  test    eax, eax
0x180002037  jns     short loc_180002086
0x180002039  test    byte ptr cs:_bidGblFlags, 2
0x180002040  jz      loc_180001F58
0x180002046  lea     r14, [rdi+100h]
0x18000204d  mov     rcx, r14; this
0x180002050  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180002055  cmp     eax, r12d
0x180002058  jz      short loc_180002074
0x18000205a  mov     rcx, r14; this
0x18000205d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180002062  mov     [rsp+1E0h+var_1B8], 0FE0h
0x18000206a  mov     edx, 3F8009h
0x18000206f  jmp     loc_180001F3E
0x180002074  mov     [rsp+1E0h+var_1C0], 0FE0h
0x18000207c  mov     edx, 3F8009h
0x180002081  jmp     loc_180001F9F
0x180002086  mov     ebx, r13d
0x180002089  mov     r12d, [rsp+1E0h+var_1B0]
0x18000208e  test    r12d, r12d
0x180002091  jz      loc_1800021D1
0x180002097  mov     r15d, r13d
0x18000209a  mov     [rsp+1E0h+var_19C], r13d
0x18000209f  mov     r13, [rsp+1E0h+var_1A8]
0x1800020a4  cmp     r15d, r12d
0x1800020a7  jnb     loc_1800021CE
0x1800020ad  mov     eax, r15d
0x1800020b0  mov     r14, [r13+rax*8+0]
0x1800020b5  test    r14, r14
0x1800020b8  jz      short loc_180002100
0x1800020ba  mov     rax, [r14]
0x1800020bd  mov     rcx, r14
0x1800020c0  mov     rax, [rax+2D0h]
0x1800020c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cc  mov     ebx, eax
0x1800020ce  test    eax, eax
0x1800020d0  js      short loc_180002151
0x1800020d2  mov     rax, [r14]
0x1800020d5  xor     edx, edx
0x1800020d7  lea     r8d, [rdx+1]
0x1800020db  mov     rcx, r14
0x1800020de  mov     rax, [rax+2B8h]
0x1800020e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ea  mov     ebx, eax
0x1800020ec  test    eax, eax
0x1800020ee  js      short loc_18000210A
0x1800020f0  lea     rcx, [r14+20h]
0x1800020f4  mov     rax, [rcx]
0x1800020f7  mov     rax, [rax+58h]
0x1800020fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002100  inc     r15d
0x180002103  mov     [rsp+1E0h+var_19C], r15d
0x180002108  jmp     short loc_1800020A4
0x18000210a  test    byte ptr cs:_bidGblFlags, 2
0x180002111  jz      loc_180001F62
0x180002117  lea     r14, [rdi+100h]
0x18000211e  mov     rcx, r14; this
0x180002121  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180002126  cmp     eax, 0FFFFFFFFh
0x180002129  jz      short loc_180002142
0x18000212b  mov     rcx, r14; this
0x18000212e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180002133  mov     [rsp+1E0h+var_1B8], 0FEBh
0x18000213b  mov     edx, 3FAC09h
0x180002140  jmp     short loc_180002187
0x180002142  mov     [rsp+1E0h+var_1C0], 0FEBh
0x18000214a  mov     edx, 3FAC09h
0x18000214f  jmp     short loc_1800021B3
0x180002151  test    byte ptr cs:_bidGblFlags, 2
0x180002158  jz      loc_180001F62
0x18000215e  lea     r14, [rdi+100h]
0x180002165  mov     rcx, r14; this
0x180002168  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000216d  cmp     eax, 0FFFFFFFFh
0x180002170  jz      short loc_1800021A6
0x180002172  mov     rcx, r14; this
0x180002175  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000217a  mov     [rsp+1E0h+var_1B8], 0FEAh
  ... truncated ...
```
