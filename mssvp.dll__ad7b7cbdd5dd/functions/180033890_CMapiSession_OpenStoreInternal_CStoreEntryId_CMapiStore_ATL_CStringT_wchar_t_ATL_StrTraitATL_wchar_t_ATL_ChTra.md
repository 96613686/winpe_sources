# CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)

- ea: `0x180033890`
- end: `0x180033cd4`
- name: `?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z`
- size: `1092`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800330b4`
- `0x180033434`

## callees

- `0x180003fe0`
- `0x180004850`
- `0x1800048c0`
- `0x180005210`
- `0x180007110`
- `0x18000a56c`
- `0x180024504`
- `0x18002a304`
- `0x18002adc4`
- `0x18002b2e0`
- `0x18002ca40`
- `0x18002d33c`
- `0x18002d37c`
- `0x18002ede8`
- `0x18003026c`
- `0x180032b58`
- `0x180033890`
- `0x180033f6c`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033c81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033c81`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180033b45`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180033b45`

## string_xrefs

- `0x180033b33`: `Error string: {%s}, Component: {%s}, Low level error: {0x%X}, Error context: {0x%X}`
- `0x180033c30`: `CMapiSession::OpenStoreInternal: Do not index online classic OST {%s}`
- `0x180033a0a`: `OpenMsgStore()`
- `0x180033ad4`: `CMapiSession::OpenStoreInternal: Failed to open message store {%s}`
- `0x1800339cd`: `failed OpenMsgStore() with UNKNOWN_FLAGS, trying again`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMapiSession::OpenStoreInternal(__int64 a1, unsigned int *a2, _QWORD *a3, __int64 a4, int a5)
{
  unsigned int *v9; // rdi
  __int64 CachedStore; // rax
  void *v12; // rax
  CMapiStore *v13; // rax
  int v14; // ebx
  int v15; // eax
  int v16; // edi
  enum POLICY_RESULT_ID *v17; // r8
  CMapiStore *v18; // rax
  CMapiStore *v19; // rdi
  const WCHAR *v20; // rdi
  const WCHAR *v21; // r9
  void *v22; // rax
  struct IUnknown *v23; // [rsp+20h] [rbp-50h]
  __int64 v24; // [rsp+28h] [rbp-48h]
  struct IMsgStore *v25; // [rsp+50h] [rbp-20h] BYREF
  CMapiStore *v26; // [rsp+58h] [rbp-18h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h] BYREF
  unsigned int *v28; // [rsp+68h] [rbp-8h]
  LPVOID pv; // [rsp+A8h] [rbp+38h] BYREF

  v9 = a2 + 20;
  v28 = a2 + 20;
  CachedStore = CMapiSession::FindCachedStore(a1, a2 + 20);
  if ( CachedStore )
  {
    *a3 = CachedStore;
    return 0;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v27);
  LODWORD(pv) = 0;
  if ( (unsigned int)CMapiSupport::GetTrustLevelPropVal(
                       *a2,
                       *((_QWORD *)a2 + 1),
                       (unsigned int)&v27,
                       (unsigned int)&pv,
                       (__int64)&v25) != 2 )
  {
    v15 = 0;
    if ( a2[4] )
      v15 = (unsigned int)CEntryId::operator==(a2) != 0 ? 16 : 48;
    v16 = v15 | 1;
    if ( *(_DWORD *)(a1 + 160) )
      v16 = v15;
    v25 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, struct IMsgStore **))(**(_QWORD **)(a1 + 24) + 40LL))(
            *(_QWORD *)(a1 + 24),
            0,
            *a2,
            *((_QWORD *)a2 + 1),
            0,
            v16 | 0x2000000u,
            &v25);
    if ( v14 == -2147221242 )
    {
      CLogger::Info(L"failed OpenMsgStore() with UNKNOWN_FLAGS, trying again");
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, struct IMsgStore **))(**(_QWORD **)(a1 + 24) + 40LL))(
              *(_QWORD *)(a1 + 24),
              0,
              *a2,
              *((_QWORD *)a2 + 1),
              0,
              v16,
              &v25);
    }
    CLogger::Info(v14, L"OpenMsgStore()");
    if ( v14 )
    {
      if ( v14 >= 0 )
      {
        v19 = 0;
      }
      else
      {
        if ( CLogger::m_fLoggingEnabled )
        {
          pv = 0;
          v20 = &lParam;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
            &v26,
            &lParam);
          CLogger::Error(v14, L"CMapiSession::OpenStoreInternal: Failed to open message store {%s}", v26);
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *))(**(_QWORD **)(a1 + 24) + 24LL))(
                 *(_QWORD *)(a1 + 24),
                 (unsigned int)v14,
                 0x80000000LL,
                 &pv) >= 0
            && pv )
          {
            v21 = &lParam;
            if ( *((_QWORD *)pv + 2) )
              v21 = (const WCHAR *)*((_QWORD *)pv + 2);
            if ( *((_QWORD *)pv + 1) )
              v20 = (const WCHAR *)*((_QWORD *)pv + 1);
            LODWORD(v24) = *((_DWORD *)pv + 7);
            LODWORD(v23) = *((_DWORD *)pv + 6);
            CLogger::Error(
              v14,
              L"Error string: {%s}, Component: {%s}, Low level error: {0x%X}, Error context: {0x%X}",
              v20,
              v21,
              v23,
              v24);
            MAPIFreeBuffer(pv);
          }
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v26);
        }
        if ( !a5 )
          goto LABEL_48;
        v22 = operator new(0x2A0u, (const struct std::nothrow_t *)std::nothrow);
        pv = v22;
        if ( v22 )
          v19 = CMapiStore::CMapiStore(
                  (CMapiStore *)v22,
                  *(_QWORD *)(a1 + 16),
                  (__int64)a2,
                  (struct _SPropValue *)a1,
                  0,
                  1u,
                  0,
                  a4,
                  1);
        else
          v19 = 0;
        if ( !v19 )
          goto LABEL_21;
        v14 = 0;
      }
    }
    else
    {
      if ( a2[12] )
        CStoreEntryId::ReInitializeEID((CStoreEntryId *)a2, v25);
      v18 = (CMapiStore *)operator new(0x2A0u, (const struct std::nothrow_t *)std::nothrow);
      v26 = v18;
      if ( v18 )
        v19 = CMapiStore::CMapiStore(
                v18,
                *(_QWORD *)(a1 + 16),
                (__int64)a2,
                (struct _SPropValue *)a1,
                (struct IUnknown *)v25,
                0,
                (_DWORD)pv == 0,
                a4,
                0);
      else
        v19 = 0;
      if ( !v19 )
      {
LABEL_21:
        v14 = -2147024882;
LABEL_48:
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&v25);
        v9 = v28;
        goto LABEL_49;
      }
    }
    if ( *((_DWORD *)v19 + 20) && a2[13] && !*((_DWORD *)v19 + 24) )
    {
      LODWORD(pv) = 0;
      v14 = CMapiSupport::CheckPolicyOnStore(v19, (int *)&pv, v17);
      if ( v14 < 0 )
      {
LABEL_46:
        if ( v19 )
          (*(void (__fastcall **)(CMapiStore *, __int64))(*(_QWORD *)v19 + 24LL))(v19, 1);
        goto LABEL_48;
      }
      if ( !(_DWORD)pv )
      {
        v14 = -2147216895;
        if ( CLogger::m_fLoggingEnabled )
        {
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&pv);
          CMapiStore::GetDisplayName(v19, &pv);
          CLogger::Info(-2147216895, L"CMapiSession::OpenStoreInternal: Do not index online classic OST {%s}", pv);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&pv);
        }
        goto LABEL_46;
      }
    }
    *a3 = v19;
    goto LABEL_48;
  }
  v12 = operator new(0x2A0u, (const struct std::nothrow_t *)std::nothrow);
  pv = v12;
  if ( v12 )
    v13 = CMapiStore::CMapiStore((CMapiStore *)v12, *(_QWORD *)(a1 + 16), (__int64)a2, 0, 0, 1u, 0, a4, 0);
  else
    v13 = 0;
  *a3 = v13;
  v14 = v13 == 0 ? 0x8007000E : 0;
LABEL_49:
  if ( v14 >= 0 )
  {
    if ( *a3 )
    {
      pv = (LPVOID)(a1 + 120);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 120));
      ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::SetAt(
        a1 + 48,
        *(_QWORD *)v9,
        a3);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>((struct _RTL_CRITICAL_SECTION **)&pv);
    }
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v27);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180033890  mov     [rsp-28h+arg_0], rbx
0x180033895  mov     [rsp-28h+arg_10], rsi
0x18003389a  push    rbp
0x18003389b  push    rdi
0x18003389c  push    r13
0x18003389e  push    r14
0x1800338a0  push    r15
0x1800338a2  mov     rbp, rsp
0x1800338a5  sub     rsp, 70h
0x1800338a9  mov     r13, r9
0x1800338ac  mov     r15, r8
0x1800338af  mov     rsi, rdx
0x1800338b2  mov     r14, rcx
0x1800338b5  lea     rdi, [rdx+50h]
0x1800338b9  mov     [rbp+var_8], rdi
0x1800338bd  mov     rdx, rdi
0x1800338c0  call    ?FindCachedStore@CMapiSession@@AEAAPEAVCMapiStore@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::FindCachedStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800338c5  xor     ebx, ebx
0x1800338c7  test    rax, rax
0x1800338ca  jz      short loc_1800338D6
0x1800338cc  mov     [r15], rax
0x1800338cf  xor     eax, eax
0x1800338d1  jmp     loc_180033CAD
0x1800338d6  lea     rcx, [rbp+var_10]
0x1800338da  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800338df  nop
0x1800338e0  mov     dword ptr [rbp+pv], ebx
0x1800338e3  lea     rax, [rbp+var_20]
0x1800338e7  mov     [rsp+70h+var_50], rax
0x1800338ec  lea     r9, [rbp+pv]
0x1800338f0  lea     r8, [rbp+var_10]
0x1800338f4  mov     rdx, [rsi+8]
0x1800338f8  mov     ecx, [rsi]
0x1800338fa  call    ?GetTrustLevelPropVal@CMapiSupport@@SAHKPEAEAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAK2@Z; CMapiSupport::GetTrustLevelPropVal(ulong,uchar *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ulong *,ulong *)
0x1800338ff  cmp     eax, 2
0x180033902  jnz     short loc_180033964
0x180033904  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003390b  mov     ecx, 2A0h; unsigned __int64
0x180033910  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033915  mov     [rbp+pv], rax
0x180033919  test    rax, rax
0x18003391c  jz      short loc_18003394C
0x18003391e  mov     [rsp+70h+var_30], ebx; int
0x180033922  mov     [rsp+70h+var_38], r13; __int64
0x180033927  mov     [rsp+70h+var_40], ebx; int
0x18003392b  mov     dword ptr [rsp+70h+var_48], 1; unsigned int
0x180033933  mov     [rsp+70h+var_50], rbx; struct IUnknown *
0x180033938  xor     r9d, r9d
0x18003393b  mov     r8, rsi
0x18003393e  mov     rdx, [r14+10h]
0x180033942  mov     rcx, rax; this
0x180033945  call    ??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x18003394a  jmp     short loc_18003394F
0x18003394c  mov     rax, rbx
0x18003394f  mov     [r15], rax
0x180033952  neg     rax
0x180033955  sbb     ebx, ebx
0x180033957  not     ebx
0x180033959  and     ebx, 8007000Eh
0x18003395f  jmp     loc_180033C6F
0x180033964  mov     eax, ebx
0x180033966  lea     rdx, [rsi+10h]
0x18003396a  cmp     [rdx], ebx
0x18003396c  jbe     short loc_180033980
0x18003396e  mov     rcx, rsi
0x180033971  call    ??8CEntryId@@QEAAHAEBV0@@Z; CEntryId::operator==(CEntryId const &)
0x180033976  neg     eax
0x180033978  sbb     eax, eax
0x18003397a  and     eax, 0FFFFFFE0h
0x18003397d  add     eax, 30h ; '0'
0x180033980  mov     edi, eax
0x180033982  or      edi, 1
0x180033985  cmp     [r14+0A0h], ebx
0x18003398c  cmovnz  edi, eax
0x18003398f  mov     [rbp+var_20], rbx
0x180033993  mov     rcx, [r14+18h]
0x180033997  mov     rax, [rcx]
0x18003399a  mov     edx, edi
0x18003399c  bts     edx, 19h
0x1800339a0  lea     r8, [rbp+var_20]
0x1800339a4  mov     qword ptr [rsp+70h+var_40], r8
0x1800339a9  mov     dword ptr [rsp+70h+var_48], edx
0x1800339ad  mov     [rsp+70h+var_50], rbx
0x1800339b2  mov     r9, [rsi+8]
0x1800339b6  mov     r8d, [rsi]
0x1800339b9  xor     edx, edx
0x1800339bb  mov     rax, [rax+28h]
0x1800339bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339c4  mov     ebx, eax
0x1800339c6  cmp     eax, 80040106h
0x1800339cb  jnz     short loc_180033A0A
0x1800339cd  lea     rcx, aFailedOpenmsgs; "failed OpenMsgStore() with UNKNOWN_FLAG"...
0x1800339d4  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800339d9  mov     rcx, [r14+18h]
0x1800339dd  mov     rax, [rcx]
0x1800339e0  lea     rdx, [rbp+var_20]
0x1800339e4  mov     qword ptr [rsp+70h+var_40], rdx
0x1800339e9  mov     dword ptr [rsp+70h+var_48], edi
0x1800339ed  mov     [rsp+70h+var_50], 0
0x1800339f6  mov     r9, [rsi+8]
0x1800339fa  mov     r8d, [rsi]
0x1800339fd  xor     edx, edx
0x1800339ff  mov     rax, [rax+28h]
0x180033a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a08  mov     ebx, eax
0x180033a0a  lea     rdx, aOpenmsgstore; "OpenMsgStore()"
0x180033a11  mov     ecx, ebx; int
0x180033a13  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180033a18  test    ebx, ebx
0x180033a1a  jnz     loc_180033AA1
0x180033a20  cmp     [rsi+30h], ebx
0x180033a23  jz      short loc_180033A31
0x180033a25  mov     rdx, [rbp+var_20]; struct IMsgStore *
0x180033a29  mov     rcx, rsi; this
0x180033a2c  call    ?ReInitializeEID@CStoreEntryId@@QEAAJPEAUIMsgStore@@@Z; CStoreEntryId::ReInitializeEID(IMsgStore *)
0x180033a31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033a38  mov     ecx, 2A0h; unsigned __int64
0x180033a3d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033a42  mov     [rbp+var_18], rax
0x180033a46  test    rax, rax
0x180033a49  jz      short loc_180033A8C
0x180033a4b  xor     edx, edx
0x180033a4d  cmp     dword ptr [rbp+pv], edx
0x180033a50  setz    dl
0x180033a53  mov     rcx, [rbp+var_20]
0x180033a57  mov     [rsp+70h+var_30], 0; int
0x180033a5f  mov     [rsp+70h+var_38], r13; __int64
0x180033a64  mov     [rsp+70h+var_40], edx; int
0x180033a68  mov     dword ptr [rsp+70h+var_48], 0; unsigned int
0x180033a70  mov     [rsp+70h+var_50], rcx; struct IUnknown *
0x180033a75  mov     r9, r14
0x180033a78  mov     r8, rsi
0x180033a7b  mov     rdx, [r14+10h]
0x180033a7f  mov     rcx, rax; this
0x180033a82  call    ??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180033a87  mov     rdi, rax
0x180033a8a  jmp     short loc_180033A8E
0x180033a8c  xor     edi, edi
0x180033a8e  test    rdi, rdi
0x180033a91  jnz     loc_180033BC7
0x180033a97  mov     ebx, 8007000Eh
0x180033a9c  jmp     loc_180033C62
0x180033aa1  jns     loc_180033BC5
0x180033aa7  cmp     cs:?m_fLoggingEnabled@CLogger@@0HA, 0; int CLogger::m_fLoggingEnabled
0x180033aae  jz      loc_180033B55
0x180033ab4  mov     [rbp+pv], 0
0x180033abc  lea     rdi, lParam
0x180033ac3  mov     rdx, rdi
0x180033ac6  lea     rcx, [rbp+var_18]
0x180033aca  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180033acf  nop
0x180033ad0  mov     r8, [rbp+var_18]
0x180033ad4  lea     rdx, aCmapisessionOp; "CMapiSession::OpenStoreInternal: Failed"...
0x180033adb  mov     ecx, ebx; int
0x180033add  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180033ae2  mov     rcx, [r14+18h]
0x180033ae6  mov     rax, [rcx]
0x180033ae9  lea     r9, [rbp+pv]
0x180033aed  mov     r8d, 80000000h
0x180033af3  mov     edx, ebx
0x180033af5  mov     rax, [rax+18h]
0x180033af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033afe  test    eax, eax
0x180033b00  js      short loc_180033B4C
0x180033b02  mov     rdx, [rbp+pv]
0x180033b06  test    rdx, rdx
0x180033b09  jz      short loc_180033B4C
0x180033b0b  mov     eax, [rdx+1Ch]
0x180033b0e  mov     ecx, [rdx+18h]
0x180033b11  mov     r9, rdi
0x180033b14  cmp     qword ptr [rdx+10h], 0
0x180033b19  cmovnz  r9, [rdx+10h]
0x180033b1e  cmp     qword ptr [rdx+8], 0
0x180033b23  cmovnz  rdi, [rdx+8]
0x180033b28  mov     dword ptr [rsp+70h+var_48], eax
0x180033b2c  mov     dword ptr [rsp+70h+var_50], ecx
0x180033b30  mov     r8, rdi
0x180033b33  lea     rdx, aErrorStringSCo; "Error string: {%s}, Component: {%s}, Lo"...
0x180033b3a  mov     ecx, ebx; int
0x180033b3c  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180033b41  mov     rcx, [rbp+pv]; pv
0x180033b45  call    cs:__imp_MAPIFreeBuffer
0x180033b4b  nop
0x180033b4c  lea     rcx, [rbp+var_18]
0x180033b50  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033b55  cmp     [rbp+arg_20], 0
0x180033b59  jz      loc_180033C62
0x180033b5f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033b66  mov     ecx, 2A0h; unsigned __int64
0x180033b6b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033b70  mov     [rbp+pv], rax
0x180033b74  test    rax, rax
0x180033b77  jz      short loc_180033BB6
0x180033b79  mov     [rsp+70h+var_30], 1; int
0x180033b81  mov     [rsp+70h+var_38], r13; __int64
0x180033b86  mov     [rsp+70h+var_40], 0; int
0x180033b8e  mov     dword ptr [rsp+70h+var_48], 1; unsigned int
0x180033b96  mov     [rsp+70h+var_50], 0; struct IUnknown *
0x180033b9f  mov     r9, r14
0x180033ba2  mov     r8, rsi
0x180033ba5  mov     rdx, [r14+10h]
0x180033ba9  mov     rcx, rax; this
0x180033bac  call    ??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180033bb1  mov     rdi, rax
0x180033bb4  jmp     short loc_180033BB8
0x180033bb6  xor     edi, edi
0x180033bb8  test    rdi, rdi
0x180033bbb  jz      loc_180033A97
0x180033bc1  xor     ebx, ebx
0x180033bc3  jmp     short loc_180033BC7
0x180033bc5  xor     edi, edi
0x180033bc7  cmp     dword ptr [rdi+50h], 0
0x180033bcb  jz      loc_180033CC6
0x180033bd1  cmp     dword ptr [rsi+34h], 0
0x180033bd5  jz      loc_180033CC6
0x180033bdb  cmp     dword ptr [rdi+60h], 0
0x180033bdf  jnz     loc_180033CC6
0x180033be5  mov     dword ptr [rbp+pv], 0
0x180033bec  lea     rdx, [rbp+pv]; int *
0x180033bf0  mov     rcx, rdi; struct CMapiStore *
0x180033bf3  call    ?CheckPolicyOnStore@CMapiSupport@@SAJPEAVCMapiStore@@PEAHPEAW4POLICY_RESULT_ID@@@Z; CMapiSupport::CheckPolicyOnStore(CMapiStore *,int *,POLICY_RESULT_ID *)
0x180033bf8  mov     ebx, eax
0x180033bfa  test    eax, eax
0x180033bfc  js      short loc_180033C48
0x180033bfe  cmp     dword ptr [rbp+pv], 0
0x180033c02  jnz     loc_180033CCE
0x180033c08  mov     ebx, 80041201h
0x180033c0d  cmp     cs:?m_fLoggingEnabled@CLogger@@0HA, 0; int CLogger::m_fLoggingEnabled
0x180033c14  jz      short loc_180033C48
0x180033c16  lea     rcx, [rbp+pv]
0x180033c1a  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180033c1f  nop
0x180033c20  lea     rdx, [rbp+pv]
0x180033c24  mov     rcx, rdi
0x180033c27  call    ?GetDisplayName@CMapiStore@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiStore::GetDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180033c2c  mov     r8, [rbp+pv]
0x180033c30  lea     rdx, aCmapisessionOp_3; "CMapiSession::OpenStoreInternal: Do not"...
0x180033c37  mov     ecx, ebx; int
0x180033c39  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180033c3e  nop
0x180033c3f  lea     rcx, [rbp+pv]
0x180033c43  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033c48  test    rdi, rdi
0x180033c4b  jz      short loc_180033C62
0x180033c4d  mov     rax, [rdi]
0x180033c50  mov     edx, 1
0x180033c55  mov     rcx, rdi
0x180033c58  mov     rax, [rax+18h]
0x180033c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c61  nop
0x180033c62  lea     rcx, [rbp+var_20]
0x180033c66  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180033c6b  mov     rdi, [rbp+var_8]
0x180033c6f  test    ebx, ebx
0x180033c71  js      short loc_180033CA2
0x180033c73  cmp     qword ptr [r15], 0
0x180033c77  jz      short loc_180033CA2
0x180033c79  lea     rcx, [r14+78h]; lpCriticalSection
0x180033c7d  mov     [rbp+pv], rcx
0x180033c81  call    cs:__imp_EnterCriticalSection
0x180033c87  nop
0x180033c88  lea     rcx, [r14+30h]
0x180033c8c  mov     r8, r15
0x180033c8f  mov     rdx, [rdi]
0x180033c92  call    ?SetAt@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiStore@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiStore@@@2@@ATL@@QEAAPEAU__POSITION@@PEB_WAEBQEAVCMapiStore@@@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::SetAt(wchar_t const *,CMapiStore * const &)
0x180033c97  nop
0x180033c98  lea     rcx, [rbp+pv]
0x180033c9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180033ca1  nop
0x180033ca2  lea     rcx, [rbp+var_10]
0x180033ca6  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180033cab  mov     eax, ebx
0x180033cad  lea     r11, [rsp+70h+var_s0]
0x180033cb2  mov     rbx, [r11+30h]
0x180033cb6  mov     rsi, [r11+40h]
0x180033cba  mov     rsp, r11
0x180033cbd  pop     r15
0x180033cbf  pop     r14
0x180033cc1  pop     r13
0x180033cc3  pop     rdi
0x180033cc4  pop     rbp
0x180033cc5  retn
0x180033cc6  test    ebx, ebx
0x180033cc8  js      loc_180033C48
0x180033cce  mov     [r15], rdi
0x180033cd1  jmp     short loc_180033C62
```
