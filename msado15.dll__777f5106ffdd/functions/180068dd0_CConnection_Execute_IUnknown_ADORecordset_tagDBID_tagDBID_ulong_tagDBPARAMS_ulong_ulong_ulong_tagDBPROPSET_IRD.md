# CConnection::Execute(IUnknown *,_ADORecordset *,tagDBID *,tagDBID *,ulong,tagDBPARAMS *,ulong,ulong,ulong,tagDBPROPSET *,IRDSServiceProperties *,__int64 *,IMultipleResults * *,IUnknown * *)

- ea: `0x180068dd0`
- end: `0x1800697c9`
- name: `?Execute@CConnection@@UEAAJPEAUIUnknown@@PEAU_ADORecordset@@PEAUtagDBID@@2KPEAUtagDBPARAMS@@KKKPEAUtagDBPROPSET@@PEAUIRDSServiceProperties@@PEA_JPEAPEAUIMultipleResults@@PEAPEAU2@@Z`
- size: `2553`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct IUnknown *, struct _ADORecordset *, struct tagDBID *, struct tagDBID *, unsigned int, struct tagDBPARAMS *, unsigned int, unsigned int, unsigned int, struct tagDBPROPSET *, struct IRDSServiceProperties *, struct IUnknown *, struct IMultipleResults **pperrinfo, struct IUnknown **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180056190`
- `0x180068dd0`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800c9850`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180068e01`
- `KERNEL32!TlsGetValue` at `0x180068e01`
- `ole32!CoCreateInstance` at `0x1800692d0`
- `ole32!CoCreateInstance` at `0x1800692d0`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180068f40`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180068f40`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180068f59`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180068f59`

## pseudocode

```c
__int64 __fastcall CConnection::Execute(
        CConnection *this,
        struct IUnknown *a2,
        struct _ADORecordset *a3,
        struct tagDBID *a4,
        struct tagDBID *a5,
        __int16 a6,
        struct tagDBPARAMS *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        struct tagDBPROPSET *a11,
        struct IRDSServiceProperties *a12,
        struct IUnknown *a13,
        struct IMultipleResults **pperrinfo,
        struct IUnknown **a15)
{
  LPVOID Value; // rax
  struct IMultipleResults **v18; // r12
  LPVOID v19; // r13
  struct IUnknown *v20; // r15
  GUID *v21; // r14
  struct IUnknownVtbl *lpVtbl; // rcx
  ULONG (__stdcall *AddRef)(IUnknown *); // r10
  CConnection *v24; // rcx
  HRESULT FxRowset; // ebx
  unsigned int BidObjectID; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  CConnection *v29; // rcx
  struct IUnknown *v30; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r10
  __int64 v32; // rcx
  GUID *v33; // rax
  int v34; // eax
  unsigned int v35; // esi
  __int64 v36; // r9
  unsigned int v37; // eax
  wchar_t *v38; // r8
  __int64 v39; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  struct IUnknown *v42; // [rsp+28h] [rbp-48h]
  __int64 v43; // [rsp+50h] [rbp-20h] BYREF
  struct IUnknown *v44; // [rsp+58h] [rbp-18h] BYREF
  struct IUnknown *v45; // [rsp+60h] [rbp-10h] BYREF
  LPVOID v46; // [rsp+68h] [rbp-8h] BYREF

  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  v18 = pperrinfo;
  v43 = 0;
  v19 = Value;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  if ( pperrinfo )
    *pperrinfo = 0;
  v20 = a13;
  if ( a13 )
    a13->lpVtbl = 0;
  *a15 = 0;
  if ( (a6 & 0x80u) == 0 )
  {
    if ( (a6 & 0x100) != 0 )
    {
      v21 = &IID_IStream;
    }
    else
    {
      v21 = &IID_IRow;
      if ( (a6 & 0x200) == 0 )
        v21 = &IID_IUnknown;
    }
  }
  else
  {
    v21 = &GUID_NULL;
  }
  lpVtbl = a2->lpVtbl;
  if ( (a6 & 2) != 0 )
  {
    AddRef = lpVtbl[1].AddRef;
    if ( (a6 & 4) != 0 )
    {
      pperrinfo = 0;
      FxRowset = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct tagDBPARAMS *, struct IUnknown *, struct IUnknown **))AddRef)(
                   a2,
                   0,
                   &IID_IMultipleResults,
                   a7,
                   v20,
                   &v45);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2692105;
          LODWORD(v42) = 2629;
LABEL_17:
          LODWORD(ppv) = FxRowset;
LABEL_18:
          bidTraceW(
            off_18012A1C0[0],
            v27,
            L"<CConnection::Execute|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            BidObjectID,
            ppv,
            v42);
          goto LABEL_104;
        }
        LODWORD(ppv) = 2629;
        v28 = 2692105;
LABEL_102:
        v36 = (unsigned int)FxRowset;
LABEL_103:
        bidTraceW(off_18012A1C0[0], v28, L"<CConnection::Execute|ADO|ERR> 0x%08x{HRESULT} line %d\n", v36, ppv);
        goto LABEL_104;
      }
      if ( !GetErrorInfo(0, (IErrorInfo **)&pperrinfo) )
      {
        SetErrorInfo(0, (IErrorInfo *)pperrinfo);
        ((void (__fastcall *)(struct IMultipleResults **))(*pperrinfo)[2].lpVtbl)(pperrinfo);
        CConnection::OverwriteErrorInfo(v29, FxRowset, (struct IErrorInfo **)v19 + 2, (int *)v19 + 6);
      }
      if ( (a6 & 1) != 0 )
      {
        a13 = 0;
        FxRowset = GetFxRowset(a3, a8, a9, (CConnection *)((char *)this + 304), a12, v45, &IID_IMultipleResults, &a13);
        if ( FxRowset < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_104;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v27 = 2714633;
            LODWORD(v42) = 2651;
            goto LABEL_17;
          }
          LODWORD(ppv) = 2651;
          v28 = 2714633;
          goto LABEL_102;
        }
        a8 = 0;
        a9 = 0;
        ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
        v30 = a13;
        v45 = a13;
      }
      else
      {
        v30 = v45;
      }
      FxRowset = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, GUID *, struct IUnknown *, __int64 *))v30->lpVtbl[1].QueryInterface)(
                   v30,
                   0,
                   0,
                   v21,
                   v20,
                   &v43);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2729993;
          LODWORD(v42) = 2666;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2666;
        v28 = 2729993;
        goto LABEL_102;
      }
    }
    else
    {
      FxRowset = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct tagDBPARAMS *, struct IUnknown *, __int64 *))AddRef)(
                   a2,
                   0,
                   v21,
                   a7,
                   v20,
                   &v43);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2743305;
          LODWORD(v42) = 2679;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2679;
        v28 = 2743305;
        goto LABEL_102;
      }
    }
  }
  else
  {
    QueryInterface = lpVtbl[1].QueryInterface;
    if ( (a6 & 4) != 0 )
    {
      FxRowset = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, GUID *, struct IUnknown *, __int64 *))QueryInterface)(
                   a2,
                   0,
                   0,
                   v21,
                   v20,
                   &v43);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2757641;
          LODWORD(v42) = 2693;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2693;
        v28 = 2757641;
        goto LABEL_102;
      }
    }
    else
    {
      FxRowset = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct tagDBID *, struct tagDBID *, GUID *, unsigned int, struct tagDBPROPSET *, __int64 *))QueryInterface)(
                   a2,
                   0,
                   a4,
                   a5,
                   v21,
                   a10,
                   a11,
                   &v43);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2764809;
          LODWORD(v42) = 2700;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2700;
        v28 = 2764809;
        goto LABEL_102;
      }
    }
  }
  CConnection::OverwriteErrorInfo(v24, FxRowset, (struct IErrorInfo **)v19 + 2, (int *)v19 + 6);
  v32 = v43;
  if ( (a6 & 0x300) != 0 )
  {
    if ( !v43 )
      goto LABEL_120;
    if ( (a6 & 0x100) != 0 )
    {
      v34 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IUnknown **))v43)(v43, &IID_IStream, a15);
      v35 = v34;
      if ( v34 < 0 )
      {
        FxRowset = v34;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          LODWORD(v42) = 2777;
          v27 = 2843657;
          LODWORD(ppv) = FxRowset;
          goto LABEL_18;
        }
        LODWORD(ppv) = 2777;
        v36 = v35;
        v28 = 2843657;
        goto LABEL_103;
      }
    }
    else
    {
      if ( (a6 & 0x200) == 0 )
        goto LABEL_118;
      FxRowset = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IUnknown **))v43)(v43, &IID_IRow, a15);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2848777;
          LODWORD(v42) = 2782;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2782;
        v28 = 2848777;
        goto LABEL_102;
      }
    }
    v32 = v43;
LABEL_118:
    if ( v32 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v43 = 0;
    }
    goto LABEL_120;
  }
  if ( !v43 )
    goto LABEL_120;
  pperrinfo = 0;
  if ( (a6 & 8) != 0 )
  {
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IMultipleResults ***))v43)(
           v43,
           &IID_ICreateRowset,
           &pperrinfo) < 0 )
    {
      FxRowset = CoCreateInstance(&CLSID_CRowsetHelper, 0, 3u, &IID_IRDSService, &v46);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2785289;
          LODWORD(v42) = 2720;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2720;
        v28 = 2785289;
        goto LABEL_102;
      }
      FxRowset = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, struct IUnknown **))(*(_QWORD *)v46 + 32LL))(
                   v46,
                   &IID_IRowset,
                   v43,
                   &v44);
      if ( FxRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v27 = 2791433;
          LODWORD(v42) = 2726;
          goto LABEL_17;
        }
        LODWORD(ppv) = 2726;
        v28 = 2791433;
        goto LABEL_102;
      }
      goto LABEL_73;
    }
    v32 = v43;
  }
  FxRowset = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IUnknown **))v32)(v32, &IID_IRowset, &v44);
  if ( FxRowset < 0 )
  {
    v24 = (CConnection *)pperrinfo;
    if ( pperrinfo )
    {
      ((void (__fastcall *)(struct IMultipleResults **))(*pperrinfo)[2].lpVtbl)(pperrinfo);
      pperrinfo = 0;
    }
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_104:
      if ( FxRowset == -2147467262 )
        FxRowset = -2146825037;
      CConnection::OverwriteErrorInfo(v24, FxRowset, (struct IErrorInfo **)v19 + 2, (int *)v19 + 6);
      if ( v43 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        v43 = 0;
      }
      if ( v46 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
        v46 = 0;
      }
      if ( v45 )
      {
        ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
        v45 = 0;
      }
      if ( v44 )
      {
        ((void (__fastcall *)(struct IUnknown *))v44->lpVtbl->Release)(v44);
        v44 = 0;
      }
      if ( (bidGblFlags & 2) != 0 && off_18012A398[0] )
      {
        v37 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v38 = off_18012A398[0];
        v39 = 2876416;
LABEL_125:
        LODWORD(ppv) = FxRowset;
        bidTraceW(off_18012A1C0[0], v39, v38, v37, ppv);
        return (unsigned int)FxRowset;
      }
      return (unsigned int)FxRowset;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v27 = 2799625;
      LODWORD(v42) = 2734;
      goto LABEL_17;
    }
    LODWORD(ppv) = 2734;
    v28 = 2799625;
    goto LABEL_102;
  }
LABEL_73:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( pperrinfo )
  {
    ((void (__fastcall *)(struct IMultipleResults **))(*pperrinfo)[2].lpVtbl)(pperrinfo);
    pperrinfo = 0;
  }
  if ( (a6 & 1) != 0 )
  {
    v33 = &IID_IDBAsynchStatus;
    a13 = 0;
    if ( (a8 & 0x100000) == 0 )
      v33 = &IID_IRowset;
    FxRowset = GetFxRowset(a3, a8, a9, (CConnection *)((char *)this + 304), a12, v44, v33, &a13);
    if ( FxRowset < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_104;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v27 = 2823177;
        LODWORD(v42) = 2757;
        goto LABEL_17;
      }
      LODWORD(ppv) = 2757;
      v28 = 2823177;
      goto LABEL_102;
    }
    ((void (__fastcall *)(struct IUnknown *))v44->lpVtbl->Release)(v44);
    v44 = a13;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  *a15 = v44;
LABEL_120:
  if ( v18 )
    *v18 = (struct IMultipleResults *)v45;
  if ( (bidGblFlags & 2) != 0 && off_18012A3B8[0] )
  {
    v37 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
    v38 = off_18012A3B8[0];
    v39 = 2860032;
    goto LABEL_125;
  }
  return (unsigned int)FxRowset;
}

```

## disassembly

```asm
0x180068dd0  mov     [rsp-38h+arg_0], rbx
0x180068dd5  mov     [rsp-38h+arg_18], r9
0x180068dda  mov     [rsp-38h+arg_10], r8
0x180068ddf  push    rbp
0x180068de0  push    rsi
0x180068de1  push    rdi
0x180068de2  push    r12
0x180068de4  push    r13
0x180068de6  push    r14
0x180068de8  push    r15
0x180068dea  mov     rbp, rsp
0x180068ded  sub     rsp, 70h
0x180068df1  mov     rdi, rcx
0x180068df4  mov     rbx, rdx
0x180068df7  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180068dfe  mov     ecx, [rcx+14h]; dwTlsIndex
0x180068e01  call    cs:__imp_TlsGetValue
0x180068e08  nop     dword ptr [rax+rax+00h]
0x180068e0d  mov     r12, [rbp+pperrinfo]
0x180068e14  xor     edx, edx
0x180068e16  mov     [rbp+var_20], rdx
0x180068e1a  mov     r13, rax
0x180068e1d  mov     [rbp+var_18], rdx
0x180068e21  mov     [rbp+var_10], rdx
0x180068e25  mov     [rbp+var_8], rdx
0x180068e29  test    r12, r12
0x180068e2c  jz      short loc_180068E32
0x180068e2e  mov     [r12], rdx
0x180068e32  mov     r15, [rbp+arg_60]
0x180068e39  test    r15, r15
0x180068e3c  jz      short loc_180068E41
0x180068e3e  mov     [r15], rdx
0x180068e41  mov     rax, [rbp+arg_70]
0x180068e48  mov     esi, dword ptr [rbp+arg_28]
0x180068e4b  mov     [rax], rdx
0x180068e4e  test    sil, sil
0x180068e51  jns     short loc_180068E5C
0x180068e53  lea     r14, GUID_NULL
0x180068e5a  jmp     short loc_180068E81
0x180068e5c  bt      esi, 8
0x180068e60  jnb     short loc_180068E6B
0x180068e62  lea     r14, IID_IStream
0x180068e69  jmp     short loc_180068E81
0x180068e6b  bt      esi, 9
0x180068e6f  lea     r14, IID_IRow
0x180068e76  lea     rax, IID_IUnknown
0x180068e7d  cmovnb  r14, rax
0x180068e81  mov     rcx, [rbx]
0x180068e84  mov     eax, esi
0x180068e86  and     eax, 4
0x180068e89  test    sil, 2
0x180068e8d  jz      loc_180069151
0x180068e93  mov     r10, [rcx+20h]
0x180068e97  mov     rcx, rbx
0x180068e9a  mov     r9, [rbp+arg_30]
0x180068e9e  test    eax, eax
0x180068ea0  jz      loc_1800690E1
0x180068ea6  lea     rax, [rbp+var_10]
0x180068eaa  mov     [rbp+pperrinfo], rdx
0x180068eb1  mov     [rsp+70h+var_48], rax
0x180068eb6  lea     r8, IID_IMultipleResults
0x180068ebd  mov     rax, r10
0x180068ec0  mov     [rsp+70h+ppv], r15
0x180068ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068eca  mov     ebx, eax
0x180068ecc  test    eax, eax
0x180068ece  jns     short loc_180068F37
0x180068ed0  test    byte ptr cs:_bidGblFlags, 2
0x180068ed7  jz      loc_180069689
0x180068edd  lea     rsi, [rdi+100h]
0x180068ee4  mov     rcx, rsi; this
0x180068ee7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180068eec  cmp     eax, 0FFFFFFFFh
0x180068eef  jz      short loc_180068F25
0x180068ef1  mov     rcx, rsi; this
0x180068ef4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180068ef9  mov     edx, 291409h
0x180068efe  mov     dword ptr [rsp+70h+var_48], 0A45h
0x180068f06  mov     dword ptr [rsp+70h+ppv], ebx
0x180068f0a  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180068f11  lea     r8, aCconnectionExe; "<CConnection::Execute|ADO|ERR> %u#,0x%0"...
0x180068f18  mov     r9d, eax
0x180068f1b  call    _bidTraceW
0x180068f20  jmp     loc_180069689
0x180068f25  mov     dword ptr [rsp+70h+ppv], 0A45h
0x180068f2d  mov     edx, 291409h
0x180068f32  jmp     loc_180069673
0x180068f37  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180068f3e  xor     ecx, ecx; dwReserved
0x180068f40  call    cs:__imp_GetErrorInfo
0x180068f47  nop     dword ptr [rax+rax+00h]
0x180068f4c  test    eax, eax
0x180068f4e  jnz     short loc_180068F87
0x180068f50  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180068f57  xor     ecx, ecx; dwReserved
0x180068f59  call    cs:__imp_SetErrorInfo
0x180068f60  nop     dword ptr [rax+rax+00h]
0x180068f65  mov     rcx, [rbp+pperrinfo]
0x180068f6c  mov     rax, [rcx]
0x180068f6f  mov     rax, [rax+10h]
0x180068f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f78  lea     r9, [r13+18h]; int *
0x180068f7c  mov     edx, ebx; int
0x180068f7e  lea     r8, [r13+10h]; struct IErrorInfo **
0x180068f82  call    ?OverwriteErrorInfo@CConnection@@QEAAXJPEAPEAUIErrorInfo@@PEAJ@Z; CConnection::OverwriteErrorInfo(long,IErrorInfo * *,long *)
0x180068f87  test    sil, 1
0x180068f8b  jz      loc_180069064
0x180068f91  mov     r8d, [rbp+arg_40]; unsigned int
0x180068f98  lea     rax, [rbp+arg_60]
0x180068f9f  mov     edx, [rbp+arg_38]; unsigned int
0x180068fa2  lea     r9, [rdi+130h]; struct CConnectionInfo *
0x180068fa9  mov     rcx, [rbp+arg_10]; struct _ADORecordset *
0x180068fad  mov     [rsp+70h+var_38], rax; struct IUnknown **
0x180068fb2  lea     rax, IID_IMultipleResults
0x180068fb9  mov     [rsp+70h+var_40], rax; struct _GUID *
0x180068fbe  mov     rax, [rbp+var_10]
0x180068fc2  mov     [rsp+70h+var_48], rax; struct IUnknown *
0x180068fc7  mov     rax, [rbp+arg_58]
0x180068fce  mov     [rsp+70h+ppv], rax; struct IRDSServiceProperties *
0x180068fd3  mov     [rbp+arg_60], 0
0x180068fde  call    ?GetFxRowset@@YAJPEAU_ADORecordset@@KKAEAVCConnectionInfo@@PEAUIRDSServiceProperties@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@@Z; GetFxRowset(_ADORecordset *,ulong,ulong,CConnectionInfo &,IRDSServiceProperties *,IUnknown *,_GUID const &,IUnknown * *)
0x180068fe3  mov     ebx, eax
0x180068fe5  test    eax, eax
0x180068fe7  jns     short loc_180069036
0x180068fe9  test    byte ptr cs:_bidGblFlags, 2
0x180068ff0  jz      loc_180069689
0x180068ff6  lea     rsi, [rdi+100h]
0x180068ffd  mov     rcx, rsi; this
0x180069000  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180069005  cmp     eax, 0FFFFFFFFh
0x180069008  jz      short loc_180069024
0x18006900a  mov     rcx, rsi; this
0x18006900d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180069012  mov     edx, 296C09h
0x180069017  mov     dword ptr [rsp+70h+var_48], 0A5Bh
0x18006901f  jmp     loc_180068F06
0x180069024  mov     dword ptr [rsp+70h+ppv], 0A5Bh
0x18006902c  mov     edx, 296C09h
0x180069031  jmp     loc_180069673
0x180069036  mov     rcx, [rbp+var_10]
0x18006903a  mov     [rbp+arg_38], 0
0x180069041  mov     [rbp+arg_40], 0
0x18006904b  mov     rax, [rcx]
0x18006904e  mov     rax, [rax+10h]
0x180069052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069057  mov     rcx, [rbp+arg_60]
0x18006905e  mov     [rbp+var_10], rcx
0x180069062  jmp     short loc_180069068
0x180069064  mov     rcx, [rbp+var_10]
0x180069068  mov     rax, [rcx]
0x18006906b  lea     rdx, [rbp+var_20]
0x18006906f  mov     [rsp+70h+var_48], rdx
0x180069074  mov     r9, r14
0x180069077  xor     r8d, r8d
0x18006907a  mov     [rsp+70h+ppv], r15
0x18006907f  xor     edx, edx
0x180069081  mov     rax, [rax+18h]
0x180069085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006908a  mov     ebx, eax
0x18006908c  test    eax, eax
0x18006908e  jns     loc_180069255
0x180069094  test    byte ptr cs:_bidGblFlags, 2
0x18006909b  jz      loc_180069689
0x1800690a1  lea     rsi, [rdi+100h]
0x1800690a8  mov     rcx, rsi; this
0x1800690ab  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800690b0  cmp     eax, 0FFFFFFFFh
0x1800690b3  jz      short loc_1800690CF
0x1800690b5  mov     rcx, rsi; this
0x1800690b8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800690bd  mov     edx, 29A809h
0x1800690c2  mov     dword ptr [rsp+70h+var_48], 0A6Ah
0x1800690ca  jmp     loc_180068F06
0x1800690cf  mov     dword ptr [rsp+70h+ppv], 0A6Ah
0x1800690d7  mov     edx, 29A809h
0x1800690dc  jmp     loc_180069673
0x1800690e1  lea     rax, [rbp+var_20]
0x1800690e5  mov     r8, r14
0x1800690e8  mov     [rsp+70h+var_48], rax
0x1800690ed  mov     rax, r10
0x1800690f0  mov     [rsp+70h+ppv], r15
0x1800690f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690fa  mov     ebx, eax
0x1800690fc  test    eax, eax
0x1800690fe  jns     loc_180069255
0x180069104  test    byte ptr cs:_bidGblFlags, 2
0x18006910b  jz      loc_180069689
0x180069111  lea     rsi, [rdi+100h]
0x180069118  mov     rcx, rsi; this
0x18006911b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180069120  cmp     eax, 0FFFFFFFFh
0x180069123  jz      short loc_18006913F
0x180069125  mov     rcx, rsi; this
0x180069128  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006912d  mov     edx, 29DC09h
0x180069132  mov     dword ptr [rsp+70h+var_48], 0A77h
0x18006913a  jmp     loc_180068F06
0x18006913f  mov     dword ptr [rsp+70h+ppv], 0A77h
0x180069147  mov     edx, 29DC09h
0x18006914c  jmp     loc_180069673
0x180069151  mov     r10, [rcx+18h]
0x180069155  test    eax, eax
0x180069157  lea     rax, [rbp+var_20]
0x18006915b  jz      short loc_1800691CF
0x18006915d  mov     [rsp+70h+var_48], rax
0x180069162  mov     r9, r14
0x180069165  mov     rax, r10
0x180069168  mov     [rsp+70h+ppv], r15
0x18006916d  xor     r8d, r8d
0x180069170  mov     rcx, rbx
0x180069173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069178  mov     ebx, eax
0x18006917a  test    eax, eax
0x18006917c  jns     loc_180069255
0x180069182  test    byte ptr cs:_bidGblFlags, 2
0x180069189  jz      loc_180069689
0x18006918f  lea     rsi, [rdi+100h]
0x180069196  mov     rcx, rsi; this
0x180069199  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006919e  cmp     eax, 0FFFFFFFFh
0x1800691a1  jz      short loc_1800691BD
0x1800691a3  mov     rcx, rsi; this
0x1800691a6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800691ab  mov     edx, 2A1409h
0x1800691b0  mov     dword ptr [rsp+70h+var_48], 0A85h
0x1800691b8  jmp     loc_180068F06
0x1800691bd  mov     dword ptr [rsp+70h+ppv], 0A85h
0x1800691c5  mov     edx, 2A1409h
0x1800691ca  jmp     loc_180069673
0x1800691cf  mov     rcx, [rbp+arg_50]
0x1800691d6  mov     r9, [rbp+arg_20]
0x1800691da  mov     r8, [rbp+arg_18]
0x1800691de  mov     [rsp+70h+var_38], rax
0x1800691e3  mov     rax, r10
0x1800691e6  mov     [rsp+70h+var_40], rcx
0x1800691eb  mov     ecx, [rbp+arg_48]
0x1800691f1  mov     dword ptr [rsp+70h+var_48], ecx
0x1800691f5  mov     rcx, rbx
0x1800691f8  mov     [rsp+70h+ppv], r14
0x1800691fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069202  mov     ebx, eax
0x180069204  test    eax, eax
0x180069206  jns     short loc_180069255
0x180069208  test    byte ptr cs:_bidGblFlags, 2
0x18006920f  jz      loc_180069689
0x180069215  lea     rsi, [rdi+100h]
0x18006921c  mov     rcx, rsi; this
0x18006921f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180069224  cmp     eax, 0FFFFFFFFh
0x180069227  jz      short loc_180069243
0x180069229  mov     rcx, rsi; this
0x18006922c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180069231  mov     edx, 2A3009h
0x180069236  mov     dword ptr [rsp+70h+var_48], 0A8Ch
0x18006923e  jmp     loc_180068F06
0x180069243  mov     dword ptr [rsp+70h+ppv], 0A8Ch
0x18006924b  mov     edx, 2A3009h
0x180069250  jmp     loc_180069673
0x180069255  lea     r9, [r13+18h]; int *
0x180069259  mov     edx, ebx; int
0x18006925b  lea     r8, [r13+10h]; struct IErrorInfo **
0x18006925f  call    ?OverwriteErrorInfo@CConnection@@QEAAXJPEAPEAUIErrorInfo@@PEAJ@Z; CConnection::OverwriteErrorInfo(long,IErrorInfo * *,long *)
0x180069264  mov     rcx, [rbp+var_20]
0x180069268  test    esi, 300h
0x18006926e  jnz     loc_18006957D
0x180069274  test    rcx, rcx
0x180069277  jz      loc_180069761
0x18006927d  mov     [rbp+pperrinfo], 0
0x180069288  test    sil, 8
0x18006928c  jz      loc_1800693AC
0x180069292  mov     rax, [rcx]
0x180069295  lea     r8, [rbp+pperrinfo]
0x18006929c  lea     rdx, IID_ICreateRowset
0x1800692a3  mov     rax, [rax]
0x1800692a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692ab  test    eax, eax
0x1800692ad  jns     loc_1800693A8
0x1800692b3  xor     edx, edx; pUnkOuter
0x1800692b5  lea     rax, [rbp+var_8]
0x1800692b9  lea     r9, ?IID_IRDSService@@3U_GUID@@B; riid
0x1800692c0  mov     [rsp+70h+ppv], rax; ppv
0x1800692c5  lea     rcx, CLSID_CRowsetHelper; rclsid
0x1800692cc  lea     r8d, [rdx+3]; dwClsContext
0x1800692d0  call    cs:__imp_CoCreateInstance
0x1800692d7  nop     dword ptr [rax+rax+00h]
0x1800692dc  mov     ebx, eax
0x1800692de  test    eax, eax
0x1800692e0  jns     short loc_18006932F
0x1800692e2  test    byte ptr cs:_bidGblFlags, 2
0x1800692e9  jz      loc_180069689
0x1800692ef  lea     rsi, [rdi+100h]
0x1800692f6  mov     rcx, rsi; this
0x1800692f9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800692fe  cmp     eax, 0FFFFFFFFh
0x180069301  jz      short loc_18006931D
0x180069303  mov     rcx, rsi; this
0x180069306  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006930b  mov     edx, 2A8009h
0x180069310  mov     dword ptr [rsp+70h+var_48], 0AA0h
0x180069318  jmp     loc_180068F06
  ... truncated ...
```
