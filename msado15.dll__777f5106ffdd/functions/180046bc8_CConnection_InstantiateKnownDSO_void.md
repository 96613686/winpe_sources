# CConnection::InstantiateKnownDSO(void)

- ea: `0x180046bc8`
- end: `0x1800474a3`
- name: `?InstantiateKnownDSO@CConnection@@QEAAJXZ`
- size: `2267`
- prototype: `__int64 __fastcall(CConnection *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800465dc`

## callees

- `0x180046bc8`
- `0x1800474ac`
- `0x180047520`
- `0x18004f110`
- `0x18004f330`
- `0x18005137c`
- `0x180054c0c`
- `0x180056144`
- `0x18005b950`
- `0x180066680`
- `0x180066bb4`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800ca408`
- `0x1800ca894`
- `0x1800caa28`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180047458`
- `KERNEL32!CompareStringW` at `0x180047458`
- `ole32!CoCreateInstance` at `0x180046eba`
- `ole32!CoCreateInstance` at `0x180046eba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnection::InstantiateKnownDSO(CConnection *this)
{
  char *v2; // r15
  unsigned __int16 **v3; // rdi
  unsigned __int16 *v4; // rdx
  const unsigned __int16 *v5; // rcx
  int Instance; // edi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  struct IUnknown *v12; // r8
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // r9
  unsigned int BidObjectID; // eax
  CMPString *v17; // r13
  CBidGenericBase *v18; // r14
  int v19; // eax
  __int64 v20; // r9
  unsigned int v21; // r12d
  const unsigned __int16 *v22; // rdx
  unsigned __int8 v23; // r9
  unsigned __int8 v24; // r15
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  unsigned __int16 *v28; // rdi
  unsigned __int64 v29; // r11
  const unsigned __int16 *v30; // r8
  unsigned __int16 *v31; // rcx
  __int64 *v32; // r8
  __int64 v33; // rdx
  unsigned int v34; // eax
  unsigned int i; // esi
  LPVOID *ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  LPVOID *ppvb; // [rsp+20h] [rbp-40h]
  int cchCount2[2]; // [rsp+28h] [rbp-38h]
  int cchCount2a; // [rsp+28h] [rbp-38h]
  int cchCount2b[2]; // [rsp+28h] [rbp-38h]
  struct _GUID v43; // [rsp+50h] [rbp-10h] BYREF
  struct IBindResource *v44; // [rsp+A0h] [rbp+40h] BYREF
  struct IUnknown *v45; // [rsp+A8h] [rbp+48h] BYREF

  v45 = 0;
  *((_DWORD *)this + 99) = 3;
  v2 = (char *)this + 304;
  if ( *((_DWORD *)this + 96) != 1 )
  {
    if ( *((_DWORD *)this + 96) == 2 )
    {
      v44 = 0;
      Instance = CoCreateInstance(&CLSID_CRootBinder, 0, 0x17u, &IID_IBindResource, (LPVOID *)&v44);
      if ( Instance >= 0 )
      {
        if ( (*((_BYTE *)this + 344) & 4) != 0 )
          v13 = (unsigned __int16 *)*((_QWORD *)this + 42);
        else
          v13 = 0;
        if ( (*((_BYTE *)this + 328) & 4) != 0 )
          v14 = (unsigned __int16 *)*((_QWORD *)this + 40);
        else
          v14 = 0;
        if ( (*((_BYTE *)this + 360) & 4) != 0 )
          v15 = (unsigned __int16 *)*((_QWORD *)this + 44);
        else
          v15 = 0;
        v43 = DBGUID_DSO;
        Instance = CConnection::BindURL(
                     this,
                     v44,
                     v12,
                     v15,
                     0x1000001u,
                     &v43,
                     &IID_IDBInitialize,
                     v14,
                     v13,
                     (struct IUnknown **)this + 121);
        if ( Instance < 0 && (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
          {
            LODWORD(ppv) = 5638;
            bidTraceW(
              off_18012A1C0[0],
              5773321,
              L"<CConnection::InstantiateKnownDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              (unsigned int)Instance,
              ppv);
          }
          else
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            cchCount2[0] = 5638;
            LODWORD(ppv) = Instance;
            bidTraceW(
              off_18012A1C0[0],
              5773321,
              L"<CConnection::InstantiateKnownDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              BidObjectID,
              ppv,
              *(_QWORD *)cchCount2);
          }
        }
        ((void (__fastcall *)(struct IBindResource *))v44->lpVtbl->Release)(v44);
        if ( Instance >= 0 || (bidGblFlags & 2) == 0 )
          goto LABEL_118;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          cchCount2[0] = 5640;
          v8 = 5775369;
          goto LABEL_14;
        }
        LODWORD(ppv) = 5640;
        v9 = 5775369;
      }
      else
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_118;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          cchCount2[0] = 5629;
          v8 = 5764105;
          goto LABEL_14;
        }
        LODWORD(ppv) = 5629;
        v9 = 5764105;
      }
LABEL_16:
      bidTraceW(
        off_18012A1C0[0],
        v9,
        L"<CConnection::InstantiateKnownDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)Instance,
        ppv);
      goto LABEL_118;
    }
    v17 = (CConnection *)((char *)this + 352);
    if ( (*((_BYTE *)this + 360) & 4) == 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(
          off_18012A1C0[0],
          5781513,
          L"<CConnection::InstantiateKnownDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          2147942414LL,
          5646);
      Instance = -2147024882;
      goto LABEL_118;
    }
    Instance = CConnection::GetDataInit(this);
    if ( Instance < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_118;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        cchCount2[0] = 5651;
        v8 = 5786633;
        goto LABEL_14;
      }
      LODWORD(ppv) = 5651;
      v9 = 5786633;
      goto LABEL_16;
    }
    v18 = (CConnection *)((char *)this + 256);
    if ( !(unsigned int)CMPString::IsEmpty((CMPString *)(v2 + 64)) )
    {
      v19 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      if ( CConnectionInfo::IsProviderSpecified((CConnectionInfo *)v2, v19) )
      {
        if ( (*((_BYTE *)this + 376) & 4) != 0 )
          v20 = *((_QWORD *)this + 46);
        else
          v20 = 0;
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, GUID *, char *))(**((_QWORD **)this + 124)
                                                                                               + 24LL))(
                     *((_QWORD *)this + 124),
                     0,
                     23,
                     v20,
                     &IID_IDBInitialize,
                     (char *)this + 968);
        if ( Instance < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_118;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            cchCount2[0] = 5660;
            v8 = 5795849;
            goto LABEL_14;
          }
          LODWORD(ppv) = 5660;
          v9 = 5795849;
          goto LABEL_16;
        }
LABEL_113:
        for ( i = 0; i < 3; ++i )
        {
          if ( CompareStringW(0x400u, 0x30001u, *(PCNZWCH *)v17, -1, (PCNZWCH)*(&g_rgProviderProps + 2 * i), -1) == 2 )
          {
            *((_DWORD *)this + 99) = i;
            goto LABEL_118;
          }
        }
        goto LABEL_118;
      }
    }
    v21 = CMPString::GetLength(v17) + 11;
    CMPString::CMPString((CMPString *)&v43, v22, v21, v23);
    v24 = v43.Data4[0];
    if ( (v43.Data4[0] & 4) != 0 )
    {
      v28 = *(unsigned __int16 **)&v43.Data1;
      v44 = (struct IBindResource *)v21;
      StringCchCopyW(*(unsigned __int16 **)&v43.Data1, v21, L"Provider=");
      if ( (*((_BYTE *)v17 + 8) & 4) != 0 )
        v30 = *(const unsigned __int16 **)v17;
      else
        v30 = 0;
      if ( (v24 & 4) != 0 )
        v31 = v28;
      else
        v31 = 0;
      StringCchCatW(v31, v29, v30);
      StringCchCatW(
        (unsigned __int16 *)((unsigned __int64)v28 & -(__int64)((v24 & 4) != 0)),
        (unsigned __int64)v44,
        L";");
      if ( !(unsigned int)CMPString::IsEmpty((CConnection *)((char *)this + 368)) )
      {
        if ( (v32[1] & 4) != 0 )
          v33 = *v32;
        else
          v33 = 0;
        CMPString::operator+=(&v43, v33);
        v24 = v43.Data4[0];
        v28 = *(unsigned __int16 **)&v43.Data1;
      }
      if ( (v24 & 4) != 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, GUID *, char *))(**((_QWORD **)this + 124) + 24LL))(
                     *((_QWORD *)this + 124),
                     0,
                     23,
                     v28,
                     &IID_IDBInitialize,
                     (char *)this + 968);
        if ( Instance < 0 && (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
          {
            LODWORD(ppvb) = 5693;
            bidTraceW(
              off_18012A1C0[0],
              5829641,
              L"<CConnection::InstantiateKnownDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              (unsigned int)Instance,
              ppvb);
          }
          else
          {
            v34 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            cchCount2b[0] = 5693;
            LODWORD(ppvb) = Instance;
            bidTraceW(
              off_18012A1C0[0],
              5829641,
              L"<CConnection::InstantiateKnownDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v34,
              ppvb,
              *(_QWORD *)cchCount2b);
          }
        }
        CMPString::~CMPString((CMPString *)&v43);
        if ( Instance < 0 )
          goto LABEL_118;
        goto LABEL_113;
      }
      Instance = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(v18) != -1 )
        {
          v25 = CBidGenericBase::GetBidObjectID(v18);
          cchCount2a = 5689;
          v26 = 5825545;
          goto LABEL_87;
        }
        ppva = 5689;
        v27 = 5825545;
LABEL_89:
        bidTraceW(
          off_18012A1C0[0],
          v27,
          L"<CConnection::InstantiateKnownDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          2147942414LL,
          ppva);
      }
    }
    else
    {
      Instance = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(v18) != -1 )
        {
          v25 = CBidGenericBase::GetBidObjectID(v18);
          cchCount2a = 5669;
          v26 = 5805065;
LABEL_87:
          bidTraceW(
            off_18012A1C0[0],
            v26,
            L"<CConnection::InstantiateKnownDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v25,
            -2147024882,
            cchCount2a);
          goto LABEL_90;
        }
        ppva = 5669;
        v27 = 5805065;
        goto LABEL_89;
      }
    }
LABEL_90:
    CMPString::~CMPString((CMPString *)&v43);
    goto LABEL_118;
  }
  (*(void (__fastcall **)(char *, GUID *, struct IUnknown **))(*((_QWORD *)this + 26) + 32LL))(
    (char *)this + 208,
    &IID_IUnknown,
    &v45);
  v3 = (unsigned __int16 **)((char *)this + 232);
  if ( (*((_BYTE *)this + 240) & 3) != 0 )
  {
    if ( !*v3 )
    {
LABEL_11:
      Instance = -2146824572;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_118;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        cchCount2[0] = 5604;
        v8 = 5738505;
LABEL_14:
        LODWORD(ppv) = Instance;
        bidTraceW(
          off_18012A1C0[0],
          v8,
          L"<CConnection::InstantiateKnownDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v7,
          ppv,
          *(_QWORD *)cchCount2);
        goto LABEL_118;
      }
      LODWORD(ppv) = 5604;
      v9 = 5738505;
      goto LABEL_16;
    }
    v4 = *v3;
  }
  else
  {
    v4 = *v3;
    if ( !*v3 )
      goto LABEL_17;
  }
  if ( (*((_BYTE *)this + 360) & 4) != 0 )
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 44);
  else
    v5 = 0;
  if ( (int)SecurityCheck(v5, v4) < 0 && (unsigned int)SecurityDialog(v45, *v3, 1) )
    goto LABEL_11;
LABEL_17:
  if ( (*((_BYTE *)this + 360) & 4) != 0 )
    v10 = (unsigned __int16 *)*((_QWORD *)this + 44);
  else
    v10 = 0;
  Instance = CConnection::BindToDSO(this, v10, 0);
  if ( Instance >= 0 )
  {
    Instance = CConnection::GetDataInit(this);
    if ( Instance >= 0 )
    {
      if ( (unsigned int)CMPString::IsEmpty((CMPString *)(v2 + 64)) )
        goto LABEL_118;
      v11 = (*((_BYTE *)this + 376) & 4) != 0 ? *((_QWORD *)this + 46) : 0LL;
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, GUID *, char *))(**((_QWORD **)this + 124)
                                                                                             + 24LL))(
                   *((_QWORD *)this + 124),
                   0,
                   23,
                   v11,
                   &IID_IDBInitialize,
                   (char *)this + 968);
      if ( Instance >= 0 || (bidGblFlags & 2) == 0 )
        goto LABEL_118;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        cchCount2[0] = 5615;
        v8 = 5749769;
        goto LABEL_14;
      }
      LODWORD(ppv) = 5615;
      v9 = 5749769;
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_118;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        cchCount2[0] = 5612;
        v8 = 5746697;
        goto LABEL_14;
      }
      LODWORD(ppv) = 5612;
      v9 = 5746697;
    }
    goto LABEL_16;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v7 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      cchCount2[0] = 5610;
      v8 = 5744649;
      goto LABEL_14;
    }
    LODWORD(ppv) = 5610;
    v9 = 5744649;
    goto LABEL_16;
  }
LABEL_118:
  if ( v45 )
    ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180046bc8  mov     [rsp-38h+arg_10], rbx
0x180046bcd  push    rbp
0x180046bce  push    rsi
0x180046bcf  push    rdi
0x180046bd0  push    r12
0x180046bd2  push    r13
0x180046bd4  push    r14
0x180046bd6  push    r15
0x180046bd8  mov     rbp, rsp
0x180046bdb  sub     rsp, 60h
0x180046bdf  mov     rbx, rcx
0x180046be2  mov     [rbp+arg_8], 0
0x180046bea  mov     dword ptr [rcx+18Ch], 3
0x180046bf4  lea     r15, [rcx+130h]
0x180046bfb  cmp     dword ptr [r15+50h], 1
0x180046c00  jnz     loc_180046E8A
0x180046c06  add     rcx, 0D0h
0x180046c0d  mov     rax, [rcx]
0x180046c10  lea     r8, [rbp+arg_8]
0x180046c14  lea     rdx, IID_IUnknown
0x180046c1b  mov     rax, [rax+20h]
0x180046c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c24  lea     rdi, [rbx+0E8h]
0x180046c2b  mov     sil, 4
0x180046c2e  test    byte ptr [rbx+0F0h], 3
0x180046c35  jz      short loc_180046C42
0x180046c37  cmp     qword ptr [rdi], 0
0x180046c3b  jz      short loc_180046C89
0x180046c3d  mov     rdx, [rdi]
0x180046c40  jmp     short loc_180046C4E
0x180046c42  mov     rdx, [rdi]; unsigned __int16 *
0x180046c45  test    rdx, rdx
0x180046c48  jz      loc_180046D0C
0x180046c4e  test    [rbx+168h], sil
0x180046c55  jz      short loc_180046C60
0x180046c57  mov     rcx, [rbx+160h]
0x180046c5e  jmp     short loc_180046C62
0x180046c60  xor     ecx, ecx; unsigned __int16 *
0x180046c62  call    ?SecurityCheck@@YAJPEBGPEAG@Z; SecurityCheck(ushort const *,ushort *)
0x180046c67  test    eax, eax
0x180046c69  jns     loc_180046D0C
0x180046c6f  mov     r8d, 1; int
0x180046c75  mov     rdx, [rdi]; unsigned __int16 *
0x180046c78  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180046c7c  call    ?SecurityDialog@@YAJPEAUIUnknown@@PEAGH@Z; SecurityDialog(IUnknown *,ushort *,int)
0x180046c81  test    eax, eax
0x180046c83  jz      loc_180046D0C
0x180046c89  mov     edi, 800A0E84h
0x180046c8e  test    byte ptr cs:_bidGblFlags, 2
0x180046c95  jz      loc_180047473
0x180046c9b  lea     rcx, [rbx+100h]; this
0x180046ca2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046ca7  cmp     eax, 0FFFFFFFFh
0x180046caa  jz      short loc_180046CE4
0x180046cac  lea     rcx, [rbx+100h]; this
0x180046cb3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046cb8  mov     [rsp+60h+cchCount2], 15E4h
0x180046cc0  mov     edx, 579009h
0x180046cc5  lea     r8, aCconnectionIns_0; "<CConnection::InstantiateKnownDSO|ADO|E"...
0x180046ccc  mov     r9d, eax
0x180046ccf  mov     dword ptr [rsp+60h+ppv], edi
0x180046cd3  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180046cda  call    _bidTraceW
0x180046cdf  jmp     loc_180047473
0x180046ce4  mov     dword ptr [rsp+60h+ppv], 15E4h
0x180046cec  mov     edx, 579009h
0x180046cf1  lea     r8, aCconnectionIns_2; "<CConnection::InstantiateKnownDSO|ADO|E"...
0x180046cf8  mov     r9d, edi
0x180046cfb  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180046d02  call    _bidTraceW
0x180046d07  jmp     loc_180047473
0x180046d0c  test    [rbx+168h], sil
0x180046d13  jz      short loc_180046D1E
0x180046d15  mov     rdx, [rbx+160h]
0x180046d1c  jmp     short loc_180046D20
0x180046d1e  xor     edx, edx; unsigned __int16 *
0x180046d20  xor     r8d, r8d; struct ISourcesRowset *
0x180046d23  mov     rcx, rbx; this
0x180046d26  call    ?BindToDSO@CConnection@@QEAAJPEAGPEAUISourcesRowset@@@Z; CConnection::BindToDSO(ushort *,ISourcesRowset *)
0x180046d2b  mov     edi, eax
0x180046d2d  test    eax, eax
0x180046d2f  jns     short loc_180046D7F
0x180046d31  test    byte ptr cs:_bidGblFlags, 2
0x180046d38  jz      loc_180047473
0x180046d3e  lea     rcx, [rbx+100h]; this
0x180046d45  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046d4a  cmp     eax, 0FFFFFFFFh
0x180046d4d  jz      short loc_180046D6D
0x180046d4f  lea     rcx, [rbx+100h]; this
0x180046d56  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046d5b  mov     [rsp+60h+cchCount2], 15EAh
0x180046d63  mov     edx, 57A809h
0x180046d68  jmp     loc_180046CC5
0x180046d6d  mov     dword ptr [rsp+60h+ppv], 15EAh
0x180046d75  mov     edx, 57A809h
0x180046d7a  jmp     loc_180046CF1
0x180046d7f  mov     rcx, rbx; this
0x180046d82  call    ?GetDataInit@CConnection@@QEAAJXZ; CConnection::GetDataInit(void)
0x180046d87  mov     edi, eax
0x180046d89  test    eax, eax
0x180046d8b  jns     short loc_180046DDB
0x180046d8d  test    byte ptr cs:_bidGblFlags, 2
0x180046d94  jz      loc_180047473
0x180046d9a  lea     rcx, [rbx+100h]; this
0x180046da1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046da6  cmp     eax, 0FFFFFFFFh
0x180046da9  jz      short loc_180046DC9
0x180046dab  lea     rcx, [rbx+100h]; this
0x180046db2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046db7  mov     [rsp+60h+cchCount2], 15ECh
0x180046dbf  mov     edx, 57B009h
0x180046dc4  jmp     loc_180046CC5
0x180046dc9  mov     dword ptr [rsp+60h+ppv], 15ECh
0x180046dd1  mov     edx, 57B009h
0x180046dd6  jmp     loc_180046CF1
0x180046ddb  lea     rcx, [r15+40h]; this
0x180046ddf  call    ?IsEmpty@CMPString@@QEBAHXZ; CMPString::IsEmpty(void)
0x180046de4  test    eax, eax
0x180046de6  jnz     loc_180047473
0x180046dec  mov     rcx, [rbx+3E0h]
0x180046df3  mov     rax, [rcx]
0x180046df6  test    [rbx+178h], sil
0x180046dfd  jz      short loc_180046E08
0x180046dff  mov     r9, [rbx+170h]
0x180046e06  jmp     short loc_180046E0B
0x180046e08  xor     r9d, r9d
0x180046e0b  lea     rdx, [rbx+3C8h]
0x180046e12  mov     qword ptr [rsp+60h+cchCount2], rdx
0x180046e17  lea     rdx, IID_IDBInitialize
0x180046e1e  mov     [rsp+60h+ppv], rdx
0x180046e23  xor     edx, edx
0x180046e25  lea     r8d, [rdx+17h]
0x180046e29  mov     rax, [rax+18h]
0x180046e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e32  mov     edi, eax
0x180046e34  test    eax, eax
0x180046e36  jns     loc_180047473
0x180046e3c  test    byte ptr cs:_bidGblFlags, 2
0x180046e43  jz      loc_180047473
0x180046e49  lea     rcx, [rbx+100h]; this
0x180046e50  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046e55  cmp     eax, 0FFFFFFFFh
0x180046e58  jz      short loc_180046E78
0x180046e5a  lea     rcx, [rbx+100h]; this
0x180046e61  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046e66  mov     [rsp+60h+cchCount2], 15EFh
0x180046e6e  mov     edx, 57BC09h
0x180046e73  jmp     loc_180046CC5
0x180046e78  mov     dword ptr [rsp+60h+ppv], 15EFh
0x180046e80  mov     edx, 57BC09h
0x180046e85  jmp     loc_180046CF1
0x180046e8a  cmp     dword ptr [r15+50h], 2
0x180046e8f  jnz     loc_180047082
0x180046e95  mov     [rbp+arg_0], 0
0x180046e9d  lea     rax, [rbp+arg_0]
0x180046ea1  mov     [rsp+60h+ppv], rax; ppv
0x180046ea6  lea     r9, IID_IBindResource; riid
0x180046ead  xor     edx, edx; pUnkOuter
0x180046eaf  lea     r8d, [rdx+17h]; dwClsContext
0x180046eb3  lea     rcx, ?CLSID_CRootBinder@@3U_GUID@@B; rclsid
0x180046eba  call    cs:__imp_CoCreateInstance
0x180046ec1  nop     dword ptr [rax+rax+00h]
0x180046ec6  mov     edi, eax
0x180046ec8  test    eax, eax
0x180046eca  jns     short loc_180046F1A
0x180046ecc  test    byte ptr cs:_bidGblFlags, 2
0x180046ed3  jz      loc_180047473
0x180046ed9  lea     rcx, [rbx+100h]; this
0x180046ee0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046ee5  cmp     eax, 0FFFFFFFFh
0x180046ee8  jz      short loc_180046F08
0x180046eea  lea     rcx, [rbx+100h]; this
0x180046ef1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046ef6  mov     [rsp+60h+cchCount2], 15FDh
0x180046efe  mov     edx, 57F409h
0x180046f03  jmp     loc_180046CC5
0x180046f08  mov     dword ptr [rsp+60h+ppv], 15FDh
0x180046f10  mov     edx, 57F409h
0x180046f15  jmp     loc_180046CF1
0x180046f1a  mov     sil, 4
0x180046f1d  test    [rbx+158h], sil
0x180046f24  jz      short loc_180046F2F
0x180046f26  mov     rdx, [rbx+150h]
0x180046f2d  jmp     short loc_180046F31
0x180046f2f  xor     edx, edx
0x180046f31  test    [rbx+148h], sil
0x180046f38  jz      short loc_180046F43
0x180046f3a  mov     rcx, [rbx+140h]
0x180046f41  jmp     short loc_180046F45
0x180046f43  xor     ecx, ecx
0x180046f45  movups  xmm0, xmmword ptr cs:DBGUID_DSO.Data1
0x180046f4c  test    [rbx+168h], sil
0x180046f53  jz      short loc_180046F5E
0x180046f55  mov     r9, [rbx+160h]
0x180046f5c  jmp     short loc_180046F61
0x180046f5e  xor     r9d, r9d; unsigned __int16 *
0x180046f61  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180046f66  lea     rax, [rbx+3C8h]
0x180046f6d  mov     [rsp+60h+var_18], rax; struct IUnknown **
0x180046f72  mov     [rsp+60h+var_20], rdx; unsigned __int16 *
0x180046f77  mov     [rsp+60h+var_28], rcx; unsigned __int16 *
0x180046f7c  lea     rdx, IID_IDBInitialize
0x180046f83  mov     [rsp+60h+var_30], rdx; struct _GUID *
0x180046f88  lea     rax, [rbp+var_10]
0x180046f8c  mov     qword ptr [rsp+60h+cchCount2], rax; struct _GUID *
0x180046f91  mov     dword ptr [rsp+60h+ppv], 1000001h; unsigned int
0x180046f99  mov     rdx, [rbp+arg_0]; struct IBindResource *
0x180046f9d  mov     rcx, rbx; this
0x180046fa0  call    ?BindURL@CConnection@@AEAAJPEAUIBindResource@@PEAUIUnknown@@PEAGKU_GUID@@AEBU4@22PEAPEAU3@@Z; CConnection::BindURL(IBindResource *,IUnknown *,ushort *,ulong,_GUID,_GUID const &,ushort *,ushort *,IUnknown * *)
0x180046fa5  mov     edi, eax
0x180046fa7  test    eax, eax
0x180046fa9  jns     short loc_18004701C
0x180046fab  test    byte ptr cs:_bidGblFlags, 2
0x180046fb2  jz      short loc_18004701C
0x180046fb4  lea     rsi, [rbx+100h]
0x180046fbb  mov     rcx, rsi; this
0x180046fbe  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046fc3  cmp     eax, 0FFFFFFFFh
0x180046fc6  jz      short loc_180046FF9
0x180046fc8  mov     rcx, rsi; this
0x180046fcb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180046fd0  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180046fd7  mov     [rsp+60h+cchCount2], 1606h
0x180046fdf  mov     dword ptr [rsp+60h+ppv], edi
0x180046fe3  mov     r9d, eax
0x180046fe6  lea     r8, aCconnectionIns_0; "<CConnection::InstantiateKnownDSO|ADO|E"...
0x180046fed  mov     edx, 581809h
0x180046ff2  call    _bidTraceW
0x180046ff7  jmp     short loc_18004701C
0x180046ff9  mov     dword ptr [rsp+60h+ppv], 1606h
0x180047001  mov     r9d, edi
0x180047004  lea     r8, aCconnectionIns_2; "<CConnection::InstantiateKnownDSO|ADO|E"...
0x18004700b  mov     edx, 581809h
0x180047010  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180047017  call    _bidTraceW
0x18004701c  mov     rcx, [rbp+arg_0]
0x180047020  mov     rax, [rcx]
0x180047023  mov     rax, [rax+10h]
0x180047027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004702c  test    edi, edi
0x18004702e  jns     loc_180047473
0x180047034  test    byte ptr cs:_bidGblFlags, 2
0x18004703b  jz      loc_180047473
0x180047041  lea     rcx, [rbx+100h]; this
0x180047048  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004704d  cmp     eax, 0FFFFFFFFh
0x180047050  jz      short loc_180047070
0x180047052  lea     rcx, [rbx+100h]; this
0x180047059  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004705e  mov     [rsp+60h+cchCount2], 1608h
0x180047066  mov     edx, 582009h
0x18004706b  jmp     loc_180046CC5
0x180047070  mov     dword ptr [rsp+60h+ppv], 1608h
0x180047078  mov     edx, 582009h
0x18004707d  jmp     loc_180046CF1
0x180047082  lea     r13, [rcx+160h]
0x180047089  mov     sil, 4
0x18004708c  test    [r13+8], sil
0x180047090  jnz     short loc_1800470CA
0x180047092  mov     ebx, 8007000Eh
0x180047097  test    byte ptr cs:_bidGblFlags, 2
0x18004709e  jz      short loc_1800470C3
0x1800470a0  mov     dword ptr [rsp+60h+ppv], 160Eh
0x1800470a8  mov     r9d, ebx
0x1800470ab  lea     r8, aCconnectionIns_2; "<CConnection::InstantiateKnownDSO|ADO|E"...
0x1800470b2  mov     edx, 583809h
0x1800470b7  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800470be  call    _bidTraceW
0x1800470c3  mov     edi, ebx
0x1800470c5  jmp     loc_180047473
0x1800470ca  call    ?GetDataInit@CConnection@@QEAAJXZ; CConnection::GetDataInit(void)
0x1800470cf  mov     edi, eax
0x1800470d1  test    eax, eax
0x1800470d3  jns     short loc_180047123
0x1800470d5  test    byte ptr cs:_bidGblFlags, 2
0x1800470dc  jz      loc_180047473
0x1800470e2  lea     rcx, [rbx+100h]; this
0x1800470e9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800470ee  cmp     eax, 0FFFFFFFFh
0x1800470f1  jz      short loc_180047111
0x1800470f3  lea     rcx, [rbx+100h]; this
0x1800470fa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800470ff  mov     [rsp+60h+cchCount2], 1613h
0x180047107  mov     edx, 584C09h
0x18004710c  jmp     loc_180046CC5
0x180047111  mov     dword ptr [rsp+60h+ppv], 1613h
0x180047119  mov     edx, 584C09h
0x18004711e  jmp     loc_180046CF1
0x180047123  lea     r14, [rbx+100h]
0x18004712a  lea     rcx, [r15+40h]; this
0x18004712e  call    ?IsEmpty@CMPString@@QEBAHXZ; CMPString::IsEmpty(void)
0x180047133  test    eax, eax
0x180047135  jnz     loc_1800471EB
0x18004713b  mov     rcx, r14; this
0x18004713e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180047143  mov     edx, eax; int
0x180047145  mov     rcx, r15; this
0x180047148  call    ?IsProviderSpecified@CConnectionInfo@@QEAA_NH@Z; CConnectionInfo::IsProviderSpecified(int)
0x18004714d  test    al, al
0x18004714f  jz      loc_1800471EB
  ... truncated ...
```
