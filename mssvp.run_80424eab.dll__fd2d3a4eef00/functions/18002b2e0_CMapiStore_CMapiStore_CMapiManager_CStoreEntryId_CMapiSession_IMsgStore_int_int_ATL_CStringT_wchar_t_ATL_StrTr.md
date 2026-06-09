# CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)

- ea: `0x18002b2e0`
- end: `0x18002bd5c`
- name: `??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z`
- size: `2684`
- prototype: `__int64 __usercall@<rax>(CMapiStore *this@<rcx>, struct IUnknown *, unsigned int, int, __int64, int)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180033890`

## callees

- `0x1800031c0`
- `0x1800038f0`
- `0x180003fe0`
- `0x1800045e4`
- `0x180004850`
- `0x1800048c0`
- `0x180004d40`
- `0x180005210`
- `0x180007110`
- `0x18000be2c`
- `0x18000c344`
- `0x18000c3f0`
- `0x1800115c4`
- `0x180019084`
- `0x180024504`
- `0x18002922c`
- `0x18002a11c`
- `0x18002b060`
- `0x18002b1e8`
- `0x18002b230`
- `0x18002b2e0`
- `0x18002c4d0`
- `0x18002c9ac`
- `0x18002ca40`
- `0x18002ce70`
- `0x18002cfe0`
- `0x18002d154`
- `0x18002d37c`
- `0x18002d4a8`
- `0x18002d514`
- `0x18002d59c`
- `0x18002d62c`
- `0x18002dd8c`
- `0x18002e3a8`
- `0x18002e454`
- `0x18002eea8`
- `0x18002f7f8`
- `0x180030a04`
- `0x1800314c0`
- `0x180031c64`
- `0x180032c68`
- `0x18003d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002bab4`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002bab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002bada`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002bada`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b6ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002bb73`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b6ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002bb73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002bae6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002bae6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002bc6e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002bc6e`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x18002bc52`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x18002bc52`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x18002bbf4`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x18002bbf4`

## string_xrefs

- `0x18002b96c`: `IsCached`
- `0x18002bd06`: `CMapiStore::CMapiStore(%s) Created`
- `0x18002bb9e`: `Unable to create CPusherAdvise()`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
CMapiStore *CMapiStore::CMapiStore(
        CMapiStore *this,
        __int64 a2,
        __int64 a3,
        struct _SPropValue *a4,
        struct IUnknown *a5,
        unsigned int a6,
        int a7,
        ...)
{
  _QWORD *v10; // r15
  struct IUnknown **v11; // r14
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // xmm5_4
  int v19; // r11d
  int v20; // r10d
  int v21; // r9d
  __int64 v22; // r8
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  int *v25; // r12
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // r12d
  struct IUnknown *v31; // rbx
  BOOL v32; // eax
  wchar_t *v33; // r9
  int v34; // eax
  LPMAPIPROP *v35; // rsi
  int MapiManager; // eax
  struct CMapiManager *v37; // rcx
  LPSPropValue v38; // r14
  char *v39; // rbx
  _QWORD *v40; // r15
  unsigned int v41; // ebx
  LPSPropValue v42; // rcx
  __int64 ul; // rdx
  LPSPropValue v44; // r8
  LPMAPIPROP v45; // rcx
  unsigned int v47; // [rsp+20h] [rbp-48h]
  unsigned int v48; // [rsp+28h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES *v49; // [rsp+30h] [rbp-38h]
  unsigned int *v50; // [rsp+38h] [rbp-30h]
  __int64 v51; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v52[4]; // [rsp+48h] [rbp-20h] BYREF
  LPCWSTR lpSubKey; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v54; // [rsp+C0h] [rbp+58h] BYREF
  LPSPropValue pProp; // [rsp+C8h] [rbp+60h] BYREF
  __int64 v56; // [rsp+E8h] [rbp+80h] BYREF
  va_list va; // [rsp+E8h] [rbp+80h]
  __int64 v58; // [rsp+F0h] [rbp+88h]
  va_list va1; // [rsp+F8h] [rbp+90h] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v56 = va_arg(va1, _QWORD);
  v58 = va_arg(va1, _QWORD);
  pProp = a4;
  *(_QWORD *)this = &CMapiStore::`vftable';
  CEntryId::CEntryId((CMapiStore *)((char *)this + 16), (struct CEntryId *)a3, (int *)a3);
  *((_QWORD *)this + 4) = 0;
  v10 = (_QWORD *)((char *)this + 40);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 40);
  v11 = (struct IUnknown **)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 64);
  *((_DWORD *)this + 18) = 1;
  *((_DWORD *)this + 19) = 1;
  *((_QWORD *)this + 13) = 0;
  *(_QWORD *)((char *)this + 132) = 500;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 144);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 248,
    v12,
    v13,
    v14,
    LODWORD(FLOAT_2_25));
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 320,
    v15,
    v16,
    v17,
    v18);
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_DWORD *)this + 102) = 17;
  *((_QWORD *)this + 53) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 110) = 0;
  *((_DWORD *)this + 111) = 10;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 103) = 1061158912;
  *((_DWORD *)this + 104) = 1048576000;
  *((_DWORD *)this + 105) = 1074790400;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds((char *)this + 392);
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_DWORD *)this + 120) = 17;
  *((_QWORD *)this + 62) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 63) = 0;
  *((_DWORD *)this + 128) = 0;
  *((_DWORD *)this + 129) = 10;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_DWORD *)this + 121) = v19;
  *((_DWORD *)this + 122) = v20;
  *((_DWORD *)this + 123) = v21;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds((char *)this + 464);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 536);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 544);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 552);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 560);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 568);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 576);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 584);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 592);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 600);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 608);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 616);
  *((_QWORD *)this + 79) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((char *)this + 664);
  *((_QWORD *)this + 78) = a2;
  *((_DWORD *)this + 30) = a6;
  v23 = *(_QWORD *)(a3 + 80);
  v24 = (_QWORD *)(v23 - 24);
  v25 = (int *)(*((_QWORD *)this + 5) - 24LL);
  if ( (int *)(v23 - 24) != v25 )
  {
    if ( v25[4] >= 0 && *v24 == *(_QWORD *)v25 )
    {
      v26 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v24);
      ATL::CStringData::Release((ATL::CStringData *)v25);
      *v10 = v26 + 24;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 40, v23, *(unsigned int *)(v23 - 16));
    }
  }
  LOBYTE(v22) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 248,
    257,
    v22);
  LOBYTE(v27) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 320,
    257,
    v27);
  LOBYTE(v28) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 392,
    257,
    v28);
  LOBYTE(v29) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 464,
    257,
    v29);
  if ( v56 )
    CMapiStore::GenerateDisplayName((char *)this + 40, v56, (char *)this + 64);
  else
    ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 64, &lParam, 0);
  *((_DWORD *)this + 2) = 1;
  v30 = 0;
  v31 = a5;
  if ( !a5 )
    goto LABEL_17;
  v56 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a5->lpVtbl->QueryInterface)(
         a5,
         &IID_IProxyStoreObject,
         (__int64 *)va) >= 0 )
  {
    a5 = 0;
    if ( (*(int (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v56 + 32LL))(v56, &a5) < 0 )
    {
      CLogger::Error(-2147467259, L"Unable to unwrap PRXPST store");
    }
    else
    {
      if ( *v11 != a5 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 6, a5);
      v30 = 1;
    }
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)va);
  if ( !v30 )
  {
LABEL_17:
    if ( *v11 != v31 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 6, v31);
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 4);
  *((_DWORD *)this + 20) = *(_DWORD *)(a3 + 32);
  *((_DWORD *)this + 21) = *(_DWORD *)(a3 + 36);
  *((_DWORD *)this + 24) = *(_DWORD *)(a3 + 40);
  v32 = v30 || *(_DWORD *)(a3 + 44);
  *((_DWORD *)this + 23) = v32;
  *((_DWORD *)this + 22) = *(_DWORD *)(a3 + 48);
  *((_DWORD *)this + 31) = a7;
  *((_DWORD *)this + 25) = 0;
  *((_DWORD *)this + 28) = *(_DWORD *)(a3 + 52);
  *((_DWORD *)this + 29) = 0;
  *((_DWORD *)this + 32) = v58;
  if ( pProp )
  {
    if ( !*v11 )
      goto LABEL_44;
    CMapiSession::GetProfileNameDisplayName(pProp, (char *)this + 664);
  }
  if ( *v11 )
  {
    *((_DWORD *)this + 25) = CMapiStore::IsStorePusherEnabled(this);
    pProp = 0;
    if ( (int)CMapiStore::GetRootFolderorIPMSubTree(this, (struct IMAPIFolder **)&pProp, 1) < 0 )
    {
      CLogger::Error(L"CMapiStore::CMapiStore: Failed to fetch IPMSubtree");
    }
    else
    {
      *((_DWORD *)this + 27) = CMapiStore::IsDeepHierarchyNotificationSupported(this, (struct IMAPIFolder *)pProp);
      if ( !*((_DWORD *)this + 24)
        && (unsigned int)CMapiStore::IsICSSupported(this, (struct IMAPIFolder *)pProp)
        && *((_DWORD *)this + 27) )
      {
        *((_DWORD *)this + 26) = 1;
        if ( (*(int (__fastcall **)(LPSPropValue, __int64, char *))(*(_QWORD *)&pProp->ulPropTag + 120LL))(
               pProp,
               2147483649LL,
               (char *)this + 56) < 0 )
          CLogger::Error(L"CMapiStore::CMapiStore: Failed to get hierarchy table");
      }
      else
      {
        *((_DWORD *)this + 26) = 0;
      }
    }
    a6 = -1;
    if ( (int)CMapiSupport::CheckPolicy_DWORD(L"EnableThrottlingOnlineMailboxes", 0, &a6, 1, 1) >= 0 && a6 != -1 )
    {
      if ( a6 )
      {
        a6 = 0;
        if ( (int)CMapiSupport::CheckPolicy_DWORD(L"EnableThrottlingOnlineMailboxesValue", 0, &a6, 1, 1) >= 0 && a6 )
          *((_DWORD *)this + 33) = 0xEA60 / a6;
        else
          CLogger::Error(L"CMapistore::CMapiStore Failed to get Group Policy EnableThrottlingOnlineMailboxesValue");
      }
      else
      {
        *((_DWORD *)this + 33) = 0;
      }
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&pProp);
  }
LABEL_44:
  if ( *((_DWORD *)this + 20) )
  {
    if ( *((_DWORD *)this + 28) )
    {
      a6 = 0;
      if ( (int)CMapiStore::GetOnlineStatus(this, (int *)&a6) >= 0 )
      {
        if ( a6 )
        {
          if ( *((_DWORD *)this + 24) )
          {
            *((_DWORD *)this + 29) = 1;
            if ( CLogger::m_fLoggingEnabled )
            {
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&pProp);
              CMapiStore::GetDisplayName(this, &pProp);
              CLogger::Info(L"CMapiStore::CMapiStore: Do not index offline classic OST {%s} when online", pProp);
LABEL_54:
              ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&pProp);
            }
          }
        }
        else if ( !*((_DWORD *)this + 24) )
        {
          *((_DWORD *)this + 29) = 1;
          if ( CLogger::m_fLoggingEnabled )
          {
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&pProp);
            CMapiStore::GetDisplayName(this, &pProp);
            CLogger::Info(L"CMapiStore::CMapiStore: Do not index online classic OST {%s} when offline", pProp);
            goto LABEL_54;
          }
        }
      }
    }
  }
  *((_DWORD *)this + 35) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v51);
  CEntryId::ToByte((unsigned int *)a3, &v51);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v54);
  CEntryId::ToByte((unsigned int *)(a3 + 16), &v54);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&lpSubKey);
  CMapiStore::GetHashTableRegistryLocation(&lpSubKey);
  memset(v52, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Create((ATL::CRegKey *)v52, HKEY_CURRENT_USER, lpSubKey, v33, v47, v48, v49, v50) )
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &pProp,
      &lParam);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsCached");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v52, (const wchar_t *)pProp, *((_DWORD *)this + 24));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsPublic");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v52, (const wchar_t *)pProp, *((_DWORD *)this + 21));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsExchange");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v52, (const wchar_t *)pProp, *((_DWORD *)this + 20));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(&pProp, L"%s.%s", *v10, L"IsPST");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v52, (const wchar_t *)pProp, *((_DWORD *)this + 23));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsDelegate");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v52, (const wchar_t *)pProp, *((_DWORD *)this + 22));
    ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&pProp);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v52);
  CMapiStore::RecordHash((char *)this + 40, &v51, &v54);
  if ( *((_DWORD *)this + 25) )
  {
    ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 64, &lParam, 0);
    CMapiStore::IsProviderExcluded(this);
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&a5);
  CMapiStore::GetDisplayName(this, &a5);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64 *)va);
  if ( (int)CMapiSupport::GetInstalledOutlookVersion((__int64 *)va) < 0 )
    v34 = 0;
  else
    v34 = _o__wtol(v56);
  *((_DWORD *)this + 39) = v34;
  *((_DWORD *)this + 160) = 0;
  *(_QWORD *)((char *)this + 644) = 0;
  *((_DWORD *)this + 163) = GetCurrentProcessId();
  *((_DWORD *)this + 164) = GetTickCount();
  v35 = (LPMAPIPROP *)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
  {
    pProp = 0;
    MapiManager = CMapiManager::GetMapiManager((struct CMapiManager **)&pProp, 0);
    v38 = pProp;
    if ( MapiManager < 0 || !pProp[6].Value.cur.Hi || !*((_DWORD *)&pProp[6].Value.at + 2) )
    {
LABEL_92:
      if ( v38 )
        CMapiManager::ReleaseMapiManager(v37);
      goto LABEL_94;
    }
    if ( *((_DWORD *)this + 25) )
    {
      v39 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
      pProp = (LPSPropValue)v39;
      if ( v39 )
      {
        *(_QWORD *)v39 = &CMapiStore::CPusherAdvise::`vftable';
        *((_DWORD *)v39 + 2) = 1;
        *((_QWORD *)v39 + 7) = this;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v39 + 16));
      }
      else
      {
        v39 = 0;
      }
      v40 = (_QWORD *)((char *)this + 632);
      if ( *((char **)this + 79) != v39 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 79, (struct IUnknown *)v39);
      v41 = 0;
      if ( *v40 )
      {
        if ( ((int (__fastcall *)(LPMAPIPROP, _QWORD, _QWORD, __int64, _QWORD, char *))(*v35)->lpVtbl[1].QueryInterface)(
               *v35,
               0,
               0,
               0x10000,
               *v40,
               (char *)this + 640) >= 0 )
        {
          pProp = 0;
          if ( HrGetOneProp(*v35, 0x34190003u, &pProp) )
          {
            if ( *((_DWORD *)this + 161) )
            {
LABEL_86:
              CLogger::Info(L"Store watcher added successfully to %s", *((_QWORD *)this + 8));
              goto LABEL_92;
            }
            do
            {
              if ( v41 >= 5 )
                break;
              ++v41;
              Sleep(0xC8u);
            }
            while ( !*((_DWORD *)this + 161) );
          }
          else
          {
            v42 = pProp;
            if ( pProp->ulPropTag == 874053635 )
            {
              ul = pProp->Value.ul;
              if ( (_DWORD)ul )
              {
                if ( (unsigned int)CMapiManager::AddStoreWatcher(*((_QWORD *)this + 78), ul, (char *)this + 40) )
                {
                  *((_DWORD *)this + 161) = 1;
                  v44 = pProp;
                  *((_DWORD *)this + 162) = pProp->Value.l;
                  CLogger::Info(
                    L"Store %s is waiting on process (%u) - via GetProps()",
                    *((_QWORD *)this + 8),
                    v44->Value.ul);
                }
                v42 = pProp;
              }
            }
            MAPIFreeBuffer(v42);
          }
        }
      }
      else
      {
        CLogger::Error(-2147024882, L"Unable to create CPusherAdvise()");
      }
    }
    else if ( (unsigned int)CMapiManager::AddStoreWatcher(pProp, 0, (char *)this + 40) )
    {
      *((_DWORD *)this + 161) = 1;
    }
    if ( !*((_DWORD *)this + 161) )
    {
      CMapiStore::RemoveAllSinks(this);
      CMapiStore::RemoveMapiManager(this);
      v45 = *v35;
      *v35 = 0;
      ((void (__fastcall *)(LPMAPIPROP))v45->lpVtbl->Release)(v45);
      if ( *v35 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 6, 0);
      CLogger::Warning(L"Store watcher add failed for %s", *((_QWORD *)this + 8));
      goto LABEL_92;
    }
    goto LABEL_86;
  }
LABEL_94:
  CLogger::Info(L"CMapiStore::CMapiStore(%s) Created", a5);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>((__int64 *)va);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&a5);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&lpSubKey);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v54);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v51);
  return this;
}

```

## disassembly

```asm
0x18002b2e0  mov     [rsp-40h+pProp], r9
0x18002b2e5  mov     [rsp-40h+arg_0], rcx
0x18002b2ea  push    rbp
0x18002b2eb  push    rbx
0x18002b2ec  push    rsi
0x18002b2ed  push    rdi
0x18002b2ee  push    r12
0x18002b2f0  push    r13
0x18002b2f2  push    r14
0x18002b2f4  push    r15
0x18002b2f6  mov     rbp, rsp
0x18002b2f9  sub     rsp, 68h
0x18002b2fd  mov     rsi, r8
0x18002b300  mov     rbx, rdx
0x18002b303  mov     rdi, rcx
0x18002b306  lea     rax, ??_7CMapiStore@@6B@; const CMapiStore::`vftable'
0x18002b30d  mov     [rcx], rax
0x18002b310  add     rcx, 10h; this
0x18002b314  mov     rdx, r8; struct CEntryId *
0x18002b317  call    ??0CEntryId@@QEAA@AEAV0@PEAJ@Z; CEntryId::CEntryId(CEntryId &,long *)
0x18002b31c  nop
0x18002b31d  xor     r12d, r12d
0x18002b320  mov     [rdi+20h], r12
0x18002b324  lea     r15, [rdi+28h]
0x18002b328  mov     rcx, r15
0x18002b32b  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b330  nop
0x18002b331  lea     r14, [rdi+30h]
0x18002b335  mov     [r14], r12
0x18002b338  mov     [rdi+38h], r12
0x18002b33c  lea     rcx, [rdi+40h]
0x18002b340  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b345  nop
0x18002b346  lea     eax, [r12+1]
0x18002b34b  mov     [rdi+48h], eax
0x18002b34e  mov     [rdi+4Ch], eax
0x18002b351  mov     [rdi+68h], r12
0x18002b355  mov     qword ptr [rdi+84h], 1F4h
0x18002b360  lea     rcx, [rdi+90h]
0x18002b367  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b36c  nop
0x18002b36d  mov     [rdi+0C8h], r12
0x18002b374  mov     [rdi+0D0h], r12
0x18002b37b  mov     [rdi+0D8h], r12
0x18002b382  mov     [rdi+0E0h], r12
0x18002b389  mov     [rdi+0E8h], r12
0x18002b390  mov     [rdi+0F0h], r12
0x18002b397  lea     rcx, [rdi+0F8h]
0x18002b39e  movss   xmm5, cs:__real@40100000
0x18002b3a6  movss   [rsp+68h+var_48], xmm5
0x18002b3ac  movss   xmm3, cs:__real@3e800000
0x18002b3b4  movss   xmm4, cs:__real@3f400000
0x18002b3bc  movaps  xmm2, xmm4
0x18002b3bf  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x18002b3c4  nop
0x18002b3c5  lea     rcx, [rdi+140h]
0x18002b3cc  movss   [rsp+68h+var_48], xmm5
0x18002b3d2  movaps  xmm2, xmm4
0x18002b3d5  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x18002b3da  nop
0x18002b3db  lea     r13, [rdi+188h]
0x18002b3e2  mov     [r13+0], r12
0x18002b3e6  mov     [r13+8], r12
0x18002b3ea  mov     dword ptr [r13+10h], 11h
0x18002b3f2  mov     eax, 0FFFFFFFFh
0x18002b3f7  mov     [r13+20h], rax
0x18002b3fb  mov     [r13+28h], r12
0x18002b3ff  mov     [r13+30h], r12d
0x18002b403  mov     r12d, 0Ah
0x18002b409  mov     [r13+34h], r12d
0x18002b40d  mov     qword ptr [r13+38h], 0
0x18002b415  mov     qword ptr [r13+40h], 0
0x18002b41d  mov     r11d, 3F400000h
0x18002b423  mov     [r13+14h], r11d
0x18002b427  mov     r10d, 3E800000h
0x18002b42d  mov     [r13+18h], r10d
0x18002b431  mov     r9d, 40100000h
0x18002b437  mov     [r13+1Ch], r9d
0x18002b43b  mov     rcx, r13
0x18002b43e  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds(void)
0x18002b443  nop
0x18002b444  lea     rax, [rdi+1D0h]
0x18002b44b  xor     ecx, ecx
0x18002b44d  mov     [rax], rcx
0x18002b450  mov     [rax+8], rcx
0x18002b454  mov     dword ptr [rax+10h], 11h
0x18002b45b  mov     edx, 0FFFFFFFFh
0x18002b460  mov     [rax+20h], rdx
0x18002b464  mov     [rax+28h], rcx
0x18002b468  mov     [rax+30h], ecx
0x18002b46b  mov     [rax+34h], r12d
0x18002b46f  mov     [rax+38h], rcx
0x18002b473  mov     [rax+40h], rcx
0x18002b477  mov     [rax+14h], r11d
0x18002b47b  mov     [rax+18h], r10d
0x18002b47f  mov     [rax+1Ch], r9d
0x18002b483  mov     rcx, rax
0x18002b486  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds(void)
0x18002b48b  nop
0x18002b48c  lea     rcx, [rdi+218h]
0x18002b493  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b498  nop
0x18002b499  lea     rcx, [rdi+220h]
0x18002b4a0  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4a5  nop
0x18002b4a6  lea     rcx, [rdi+228h]
0x18002b4ad  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4b2  nop
0x18002b4b3  lea     rcx, [rdi+230h]
0x18002b4ba  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4bf  nop
0x18002b4c0  lea     rcx, [rdi+238h]
0x18002b4c7  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4cc  nop
0x18002b4cd  lea     rcx, [rdi+240h]
0x18002b4d4  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4d9  nop
0x18002b4da  lea     rcx, [rdi+248h]
0x18002b4e1  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4e6  nop
0x18002b4e7  lea     rcx, [rdi+250h]
0x18002b4ee  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b4f3  nop
0x18002b4f4  lea     rcx, [rdi+258h]
0x18002b4fb  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b500  nop
0x18002b501  lea     rcx, [rdi+260h]
0x18002b508  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b50d  nop
0x18002b50e  lea     rcx, [rdi+268h]
0x18002b515  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b51a  nop
0x18002b51b  mov     qword ptr [rdi+278h], 0
0x18002b526  lea     rcx, [rdi+298h]
0x18002b52d  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002b532  nop
0x18002b533  mov     [rdi+270h], rbx
0x18002b53a  mov     eax, [rbp+arg_28]
0x18002b53d  mov     [rdi+78h], eax
0x18002b540  mov     rdx, [rsi+50h]
0x18002b544  lea     rcx, [rdx-18h]
0x18002b548  mov     r12, [r15]
0x18002b54b  add     r12, 0FFFFFFFFFFFFFFE8h
0x18002b54f  cmp     rcx, r12
0x18002b552  jz      short loc_18002B58A
0x18002b554  cmp     dword ptr [r12+10h], 0
0x18002b55a  jl      short loc_18002B57E
0x18002b55c  mov     rax, [r12]
0x18002b560  cmp     [rcx], rax
0x18002b563  jnz     short loc_18002B57E
0x18002b565  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18002b56a  mov     rbx, rax
0x18002b56d  mov     rcx, r12; this
0x18002b570  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b575  lea     rax, [rbx+18h]
0x18002b579  mov     [r15], rax
0x18002b57c  jmp     short loc_18002B58A
0x18002b57e  mov     r8d, [rdx-10h]
0x18002b582  mov     rcx, r15
0x18002b585  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002b58a  mov     r8b, 1
0x18002b58d  mov     ebx, 101h
0x18002b592  mov     edx, ebx
0x18002b594  lea     rcx, [rdi+0F8h]
0x18002b59b  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18002b5a0  mov     r8b, 1
0x18002b5a3  mov     edx, ebx
0x18002b5a5  lea     rcx, [rdi+140h]
0x18002b5ac  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18002b5b1  mov     r8b, 1
0x18002b5b4  mov     edx, ebx
0x18002b5b6  mov     rcx, r13
0x18002b5b9  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18002b5be  mov     r8b, 1
0x18002b5c1  mov     edx, ebx
0x18002b5c3  lea     rcx, [rdi+1D0h]
0x18002b5ca  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18002b5cf  mov     rdx, [rbp+arg_38]
0x18002b5d6  lea     r13, [rdi+40h]
0x18002b5da  test    rdx, rdx
0x18002b5dd  jz      short loc_18002B5EC
0x18002b5df  mov     r8, r13
0x18002b5e2  mov     rcx, r15
0x18002b5e5  call    ?GenerateDisplayName@CMapiStore@@SAXAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@00@Z; CMapiStore::GenerateDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002b5ea  jmp     short loc_18002B5FE
0x18002b5ec  xor     r8d, r8d
0x18002b5ef  lea     rdx, lParam
0x18002b5f6  mov     rcx, r13
0x18002b5f9  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002b5fe  mov     dword ptr [rdi+8], 1
0x18002b605  xor     r12d, r12d
0x18002b608  mov     rbx, [rbp+arg_20]
0x18002b60c  test    rbx, rbx
0x18002b60f  jz      loc_18002B697
0x18002b615  mov     [rbp+arg_38], r12
0x18002b61c  mov     rax, [rbx]
0x18002b61f  lea     r8, [rbp+arg_38]
0x18002b626  lea     rdx, IID_IProxyStoreObject
0x18002b62d  mov     rcx, rbx
0x18002b630  mov     rax, [rax]
0x18002b633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b638  test    eax, eax
0x18002b63a  js      short loc_18002B686
0x18002b63c  mov     [rbp+arg_20], r12
0x18002b640  mov     rcx, [rbp+arg_38]
0x18002b647  mov     rax, [rcx]
0x18002b64a  lea     rdx, [rbp+arg_20]
0x18002b64e  mov     rax, [rax+20h]
0x18002b652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b657  test    eax, eax
0x18002b659  js      short loc_18002B674
0x18002b65b  mov     rdx, [rbp+arg_20]; struct IUnknown *
0x18002b65f  cmp     [r14], rdx
0x18002b662  jz      short loc_18002B66C
0x18002b664  mov     rcx, r14; struct IUnknown **
0x18002b667  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002b66c  mov     r12d, 1
0x18002b672  jmp     short loc_18002B686
0x18002b674  lea     rdx, aUnableToUnwrap; "Unable to unwrap PRXPST store"
0x18002b67b  mov     ecx, 80004005h; int
0x18002b680  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002b685  nop
0x18002b686  lea     rcx, [rbp+arg_38]
0x18002b68d  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002b692  test    r12d, r12d
0x18002b695  jnz     short loc_18002B6A7
0x18002b697  cmp     [r14], rbx
0x18002b69a  jz      short loc_18002B6A7
0x18002b69c  mov     rdx, rbx; struct IUnknown *
0x18002b69f  mov     rcx, r14; struct IUnknown **
0x18002b6a2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002b6a7  lea     rcx, [rdi+0A0h]; lpCriticalSection
0x18002b6ae  call    cs:__imp_InitializeCriticalSection
0x18002b6b4  mov     eax, [rsi+20h]
0x18002b6b7  mov     [rdi+50h], eax
0x18002b6ba  mov     eax, [rsi+24h]
0x18002b6bd  mov     [rdi+54h], eax
0x18002b6c0  mov     eax, [rsi+28h]
0x18002b6c3  mov     [rdi+60h], eax
0x18002b6c6  xor     ebx, ebx
0x18002b6c8  test    r12d, r12d
0x18002b6cb  jnz     short loc_18002B6DA
0x18002b6cd  cmp     [rsi+2Ch], ebx
0x18002b6d0  jnz     short loc_18002B6DA
0x18002b6d2  mov     eax, ebx
0x18002b6d4  lea     r12d, [rbx+1]
0x18002b6d8  jmp     short loc_18002B6E3
0x18002b6da  mov     r12d, 1
0x18002b6e0  mov     eax, r12d
0x18002b6e3  mov     [rdi+5Ch], eax
0x18002b6e6  mov     eax, [rsi+30h]
0x18002b6e9  mov     [rdi+58h], eax
0x18002b6ec  mov     eax, [rbp+arg_30]
0x18002b6ef  mov     [rdi+7Ch], eax
0x18002b6f2  mov     [rdi+64h], ebx
0x18002b6f5  mov     eax, [rsi+34h]
0x18002b6f8  mov     [rdi+70h], eax
0x18002b6fb  mov     [rdi+74h], ebx
0x18002b6fe  mov     eax, dword ptr [rbp+arg_40]
0x18002b704  mov     [rdi+80h], eax
0x18002b70a  mov     rax, [rbp+pProp]
0x18002b70e  test    rax, rax
0x18002b711  jz      short loc_18002B72B
0x18002b713  cmp     [r14], rbx
0x18002b716  jz      loc_18002B844
0x18002b71c  lea     rdx, [rdi+298h]
0x18002b723  mov     rcx, rax
0x18002b726  call    ?GetProfileNameDisplayName@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::GetProfileNameDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002b72b  cmp     [r14], rbx
0x18002b72e  jz      loc_18002B844
0x18002b734  mov     rcx, rdi; this
0x18002b737  call    ?IsStorePusherEnabled@CMapiStore@@AEAAHXZ; CMapiStore::IsStorePusherEnabled(void)
0x18002b73c  mov     [rdi+64h], eax
0x18002b73f  mov     [rbp+pProp], rbx
0x18002b743  mov     r8d, r12d; int
0x18002b746  lea     rdx, [rbp+pProp]; struct IMAPIFolder **
0x18002b74a  mov     rcx, rdi; this
0x18002b74d  call    ?GetRootFolderorIPMSubTree@CMapiStore@@QEAAJPEAPEAUIMAPIFolder@@H@Z; CMapiStore::GetRootFolderorIPMSubTree(IMAPIFolder * *,int)
0x18002b752  test    eax, eax
0x18002b754  js      short loc_18002B7AE
0x18002b756  mov     rdx, [rbp+pProp]; struct IMAPIFolder *
0x18002b75a  mov     rcx, rdi; this
0x18002b75d  call    ?IsDeepHierarchyNotificationSupported@CMapiStore@@AEAAHPEAUIMAPIFolder@@@Z; CMapiStore::IsDeepHierarchyNotificationSupported(IMAPIFolder *)
0x18002b762  mov     [rdi+6Ch], eax
0x18002b765  cmp     [rdi+60h], ebx
0x18002b768  jnz     short loc_18002B7A9
0x18002b76a  mov     rdx, [rbp+pProp]; struct IMAPIFolder *
0x18002b76e  mov     rcx, rdi; this
0x18002b771  call    ?IsICSSupported@CMapiStore@@AEAAHPEAUIMAPIFolder@@@Z; CMapiStore::IsICSSupported(IMAPIFolder *)
0x18002b776  test    eax, eax
0x18002b778  jz      short loc_18002B7A9
0x18002b77a  cmp     [rdi+6Ch], ebx
0x18002b77d  jz      short loc_18002B7A9
0x18002b77f  mov     [rdi+68h], r12d
0x18002b783  mov     rcx, [rbp+pProp]
0x18002b787  mov     rax, [rcx]
0x18002b78a  lea     r8, [rdi+38h]
0x18002b78e  mov     edx, 80000001h
0x18002b793  mov     rax, [rax+78h]
0x18002b797  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
