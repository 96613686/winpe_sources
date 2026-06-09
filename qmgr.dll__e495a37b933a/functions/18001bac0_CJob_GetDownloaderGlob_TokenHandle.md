# CJob::GetDownloaderGlob(TokenHandle)

- ea: `0x18001bac0`
- end: `0x18001c674`
- name: `?GetDownloaderGlob@CJob@@MEAAPEAUTRANSFER_GLOB@1@VTokenHandle@@@Z`
- size: `2996`
- prototype: `_QWORD *__fastcall(__int64 *, TokenHandle *)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800065ac`
- `0x180006640`
- `0x180014310`
- `0x18001bac0`
- `0x18001c67c`
- `0x18001c8fc`
- `0x18001c9c4`
- `0x18001dac0`
- `0x18001dad4`
- `0x18001df10`
- `0x1800213d8`
- `0x18002c990`
- `0x180035c04`
- `0x180066a40`
- `0x1800720e0`
- `0x180076d90`
- `0x18007ffe4`
- `0x18008823c`
- `0x18008d4a0`
- `0x18008df60`
- `0x18008e2ec`
- `0x18008ea2c`
- `0x1800961b8`
- `0x180099740`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800b8a5c`
- `0x1800c735c`
- `0x1800c9be0`
- `0x1800cc400`
- `0x1800f4f2c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bb17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bb17`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c0f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c1ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c506`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c0f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c1ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c506`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c2e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c2e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c62b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c62b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001c446`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001c446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall CJob::GetDownloaderGlob(__int64 *a1, TokenHandle *a2)
{
  CJob::TRANSFER_GLOB *v4; // rax
  CJobManager *v5; // rcx
  __int64 v6; // r13
  int v7; // edx
  _BYTE *v8; // rbx
  int v9; // r8d
  __int64 v10; // rax
  LPOLESTR v11; // rcx
  int v13; // edx
  int v14; // r8d
  LPOLESTR v15; // r10
  EVENT_LOG *v16; // rcx
  CJobManager *v17; // rcx
  LPOLESTR v18; // rcx
  LPOLESTR v19; // rdx
  char v20; // r14
  char v21; // r15
  int v22; // ebx
  int v23; // edi
  int v24; // esi
  int v25; // r11d
  void **v26; // rsi
  const IID *v27; // r13
  LPVOID v28; // r15
  __int64 v29; // rbx
  LPOLESTR v30; // rdi
  _QWORD *v31; // r14
  struct _GUID *v32; // rcx
  __int64 v33; // rcx
  const unsigned __int16 *FriendlyBITSJobName; // rax
  __int64 v35; // r8
  char *v36; // r15
  const unsigned __int16 *v37; // r12
  struct _GUID *v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r8
  bool v41; // dl
  int v42; // eax
  __int64 v43; // rdx
  __int128 v44; // xmm0
  __int128 *v45; // rcx
  __int128 *v46; // rcx
  const unsigned __int16 *v47; // rax
  __int64 v48; // r8
  HRESULT v49; // eax
  __int64 v50; // r8
  __int128 *v51; // rax
  __int128 *v52; // rax
  __int64 *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rdx
  char *v56; // rcx
  __int64 v57; // [rsp+38h] [rbp-128h]
  int v58; // [rsp+50h] [rbp-110h]
  char v59; // [rsp+B8h] [rbp-A8h]
  char v60; // [rsp+E0h] [rbp-80h]
  bool v61; // [rsp+E1h] [rbp-7Fh]
  char v62; // [rsp+E2h] [rbp-7Eh]
  LPOLESTR lpsz; // [rsp+E8h] [rbp-78h] BYREF
  LPVOID Context; // [rsp+F0h] [rbp-70h] BYREF
  IID *rclsid; // [rsp+F8h] [rbp-68h] BYREF
  _QWORD *PdcClientRegistrationHandle; // [rsp+100h] [rbp-60h] BYREF
  __int64 v67; // [rsp+108h] [rbp-58h] BYREF
  __int128 *v68; // [rsp+110h] [rbp-50h] BYREF
  int v69; // [rsp+118h] [rbp-48h]
  __int64 v70; // [rsp+120h] [rbp-40h] BYREF
  LPVOID v71; // [rsp+128h] [rbp-38h] BYREF
  void **pExceptionObject; // [rsp+130h] [rbp-30h] BYREF
  __int128 v73; // [rsp+138h] [rbp-28h]
  int v74; // [rsp+148h] [rbp-18h]
  int v75; // [rsp+14Ch] [rbp-14h]
  int v76; // [rsp+150h] [rbp-10h]
  __int64 v77; // [rsp+190h] [rbp+30h] BYREF
  __int64 v78; // [rsp+198h] [rbp+38h] BYREF
  _QWORD v79[3]; // [rsp+1A0h] [rbp+40h] BYREF
  LPOLESTR v80; // [rsp+1B8h] [rbp+58h]
  void **v81; // [rsp+1C0h] [rbp+60h]
  TokenHandle *v82; // [rsp+1C8h] [rbp+68h]
  struct _GUID v83; // [rsp+1D0h] [rbp+70h] BYREF
  __int64 v84; // [rsp+1E0h] [rbp+80h]
  unsigned __int64 v85; // [rsp+1E8h] [rbp+88h]
  __int128 v86; // [rsp+1F0h] [rbp+90h] BYREF
  __int64 v87; // [rsp+200h] [rbp+A0h]
  unsigned __int64 v88; // [rsp+208h] [rbp+A8h]
  __int128 v89; // [rsp+210h] [rbp+B0h] BYREF
  __int64 v90; // [rsp+220h] [rbp+C0h]
  unsigned __int64 v91; // [rsp+228h] [rbp+C8h]

  v81 = (void **)a2;
  lpsz = (LPOLESTR)a1;
  v82 = a2;
  v4 = (CJob::TRANSFER_GLOB *)HeapAlloc(hBitsHeap, 8u, 0x58u);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 88);
    v73 = 0;
    pExceptionObject = &ComError::`vftable';
    v74 = -2147024882;
    v75 = 0;
    v76 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v6 = CJob::TRANSFER_GLOB::TRANSFER_GLOB(v4);
  PdcClientRegistrationHandle = (_QWORD *)v6;
  v70 = v6;
  if ( *((_DWORD *)a1 + 165) != 2 )
  {
    CJob::SetState((CJob *)a1, BG_JOB_STATE_CONNECTING);
    CJob::ScheduleModificationCallback((CJob *)a1);
  }
  v83 = (struct _GUID)*((_OWORD *)a1 + 83);
  CJobManager::SignalBackgroundTransferSebEventBestEffort(v5, &v83, (const struct CustomUserContext *)(a1 + 163));
  v8 = (_BYTE *)(*(__int64 (__fastcall **)(__int64 *))(*a1 + 424))(a1);
  v71 = v8;
  if ( !v8 )
  {
    v83.Data1 = 4;
    v84 = 0;
    *(_DWORD *)&v83.Data4[4] = 2;
    *(_DWORD *)v83.Data4 = 2;
    *(_DWORD *)&v83.Data2 = 1359;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_llDDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v9, 4, 2, 79, 2, (__int64)&qword_18011AC70);
    v10 = *a1;
    v11 = (LPOLESTR)a1;
LABEL_13:
    (*(void (__fastcall **)(LPOLESTR, struct _GUID *, __int64))(v10 + 456))(v11, &v83, -1);
    std::unique_ptr<CJob::TRANSFER_GLOB>::~unique_ptr<CJob::TRANSFER_GLOB>(&v70);
    TokenHandle::Decrement(a2);
    return 0;
  }
  v79[0] = 2;
  v79[1] = 0;
  v79[2] = 0;
  v67 = *(_QWORD *)a2;
  _InterlockedIncrement((volatile signed __int32 *)(v67 + 8));
  if ( !(unsigned __int8)CFile::ValidateDriveInfo(v8, &v67, v79) )
  {
    if ( LODWORD(v79[0]) == 4 )
      (*(void (__fastcall **)(__int64 *, _QWORD *, __int64))(*a1 + 456))(a1, v79, -1);
    else
      CJob::SetTransientError((CJob *)a1, (struct QMErrInfo *)v79, *((_DWORD *)a1 + 210), 1, 1);
    std::unique_ptr<CJob::TRANSFER_GLOB>::~unique_ptr<CJob::TRANSFER_GLOB>(&v70);
    TokenHandle::Decrement(a2);
    return 0;
  }
  v15 = lpsz;
  if ( *((_DWORD *)lpsz + 308) && !**((_QWORD **)lpsz + 155) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
      v16 = WPP_GLOBAL_Control;
      v15 = lpsz;
    }
    v83.Data1 = 4;
    v84 = 0;
    *(_DWORD *)&v83.Data4[4] = 2;
    *(_DWORD *)v83.Data4 = 1;
    *(_DWORD *)&v83.Data2 = -2145386410;
    if ( v16 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
    {
      WPP_SF_llDDS(*((_QWORD *)v16 + 2), v13, v14, 4, 1, 86, 2, (__int64)&qword_18011AC70);
      v15 = lpsz;
    }
    v10 = *(_QWORD *)v15;
    v11 = v15;
    goto LABEL_13;
  }
  if ( v8[259] )
  {
    v60 = 0;
    CFile::RangeHeadersNotSupported((CFile *)v8);
    CFile::FileChanged((CFile *)v8);
    v15 = lpsz;
  }
  else
  {
    v60 = 1;
  }
  if ( *((_BYTE *)v15 + 673) || *((_BYTE *)v15 + 1296) )
    goto LABEL_36;
  if ( !(*(unsigned __int8 (__fastcall **)(LPOLESTR, _BYTE *))(*(_QWORD *)v15 + 488LL))(v15, v8) )
  {
    v15 = lpsz;
LABEL_36:
    v61 = 0;
    goto LABEL_37;
  }
  v61 = CJobManager::ActivateVortex(v17);
  v15 = lpsz;
LABEL_37:
  v68 = *(__int128 **)(*(_QWORD *)v8 + 8LL);
  v18 = v15;
  if ( !*((_BYTE *)v15 + 1504) )
    v18 = 0;
  v19 = v18 + 308;
  if ( !v18 )
    v19 = 0;
  v80 = v19;
  v20 = *((_BYTE *)v15 + 1296);
  v21 = *((_BYTE *)v15 + 744);
  v62 = *((_BYTE *)v15 + 1270);
  v69 = *((_DWORD *)v15 + 302);
  LODWORD(v67) = *((_DWORD *)v15 + 264);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v15 + 161) + 8LL));
  v77 = *((_QWORD *)v15 + 161);
  v22 = *((_DWORD *)v15 + 319);
  v23 = *((_DWORD *)v15 + 164);
  v24 = *((_DWORD *)v15 + 308);
  v83 = *(struct _GUID *)(v15 + 356);
  _InterlockedIncrement(*(volatile signed __int32 **)v83.Data4);
  v25 = *((_DWORD *)v15 + 166);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v15 + 91) + 8LL));
  v78 = *((_QWORD *)v15 + 91);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v15 + 87) + 8LL));
  Context = (LPVOID)*((_QWORD *)v15 + 87);
  rclsid = (IID *)(v15 + 338);
  v59 = v21;
  v58 = v24;
  v26 = v81;
  v57 = v6 + 56;
  v27 = (const IID *)(v15 + 338);
  v28 = v71;
  v29 = ((__int64 (__fastcall *)(LPVOID, LPOLESTR, LPVOID *, __int64 *, int, struct _GUID *, char *, __int64, void **, LPOLESTR, int, int, int, __int64 *, LPOLESTR, LPOLESTR, _DWORD, LPOLESTR, LPOLESTR, int, bool, char, char, char, char, LPOLESTR))v68)(
          v71,
          v15 + 338,
          &Context,
          &v78,
          v25,
          &v83,
          (char *)v15 + 913,
          v57,
          v81,
          v15 + 620,
          v58,
          v23,
          v22,
          &v77,
          v15 + 504,
          v15 + 516,
          v67,
          v15 + 536,
          v15 + 532,
          v69,
          v61,
          v62,
          v60,
          v59,
          v20,
          v80);
  v30 = lpsz;
  (*(void (__fastcall **)(__int64, void (__fastcall *)(void *), LPOLESTR))(*(_QWORD *)v29 + 72LL))(
    v29,
    CJob::StaticProgressCallback,
    lpsz);
  v31 = PdcClientRegistrationHandle;
  *PdcClientRegistrationHandle = lpsz;
  v31[1] = v28;
  v31[2] =  CJob::`vcall'{320,{flat}};
  *((_DWORD *)v31 + 6) = 0;
  *((_DWORD *)v31 + 7) = *(_DWORD *)&v83.Data4[4];
  v31[4] = v29;
  if ( (*((_DWORD *)v30 + 318) & 1) != 0 || !*((_BYTE *)g_GlobalInfo + 249) )
  {
    Context = 0;
    if ( !InitOnceExecuteOnce(&g_pdcManager, LazyGlobal<PdcManager>::LazyGlobalInitializer, 0, &Context) )
    {
      v73 = 0;
      pExceptionObject = &ComError::`vftable';
      v74 = -2147024882;
      v75 = 51;
      v76 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( PdcManager::IsPdcFeatureAvailable((PdcManager *)Context) )
    {
      v83 = 0;
      v85 = 0;
      std::wstring::_Construct_empty(&v83);
      v84 = 0;
      v32 = &v83;
      if ( v85 > 7 )
        v32 = *(struct _GUID **)&v83.Data1;
      LOWORD(v32->Data1) = 0;
      v33 = *((_QWORD *)v30 + 92);
      if ( v33 )
      {
        AppPackageInfo::GetAppUserModelId(v33, &v83);
      }
      else
      {
        FriendlyBITSJobName = CTelemetry::GetFriendlyBITSJobName((LPCWCH)(*((_QWORD *)v30 + 87) + 12LL));
        v35 = -1;
        do
          ++v35;
        while ( FriendlyBITSJobName[v35] );
        std::wstring::_Assign<unsigned short>(&v83, FriendlyBITSJobName);
      }
      v36 = (char *)operator new(0xA0u);
      v68 = (__int128 *)v36;
      if ( v36 )
      {
        Context = 0;
        if ( !InitOnceExecuteOnce(&g_pdcManager, LazyGlobal<PdcManager>::LazyGlobalInitializer, 0, &Context) )
        {
          v73 = 0;
          pExceptionObject = &ComError::`vftable';
          v74 = -2147024882;
          v75 = 51;
          v76 = 1;
          throw (ComError *)&pExceptionObject;
        }
        PdcClientRegistrationHandle = PdcManager::GetPdcClientRegistrationHandle((PdcManager *)Context);
        v37 = CTelemetry::JobTypeAsString((enum BG_JOB_TYPE)*((_DWORD *)v30 + 166));
        v38 = &v83;
        if ( v85 > 7 )
          v38 = *(struct _GUID **)&v83.Data1;
        *(_OWORD *)v36 = *(_OWORD *)(v30 + 338);
        *((_OWORD *)v36 + 1) = 0;
        *((_QWORD *)v36 + 4) = 0;
        *((_QWORD *)v36 + 5) = 0;
        v39 = -1;
        do
          ++v39;
        while ( *((_WORD *)&v38->Data1 + v39) );
        std::wstring::_Construct<1,unsigned short const *>(v36 + 16, v38);
        *((_OWORD *)v36 + 3) = 0;
        *((_QWORD *)v36 + 8) = 0;
        *((_QWORD *)v36 + 9) = 0;
        v40 = -1;
        do
          ++v40;
        while ( v37[v40] );
        std::wstring::_Construct<1,unsigned short const *>(v36 + 48, v37);
        *((_QWORD *)v36 + 10) = PdcClientRegistrationHandle;
        CCritSec2::CCritSec2((CCritSec2 *)(v36 + 88), v41);
        *((_QWORD *)v36 + 17) = 0;
        *((_DWORD *)v36 + 36) = 0;
        *((_QWORD *)v36 + 19) = GetTickCount64();
        v42 = ScopedPdcActivationHolder::PdcActivateNetwork((ScopedPdcActivationHolder *)v36);
        if ( v42 < 0 )
        {
          v73 = 0;
          pExceptionObject = &ComError::`vftable';
          v74 = v42;
          v75 = 218;
          v76 = 1;
          throw (ComError *)&pExceptionObject;
        }
      }
      else
      {
        v36 = 0;
      }
      v43 = v31[9];
      v31[9] = v36;
      if ( v43 )
        std::default_delete<ScopedPdcActivationHolder>::operator()();
      if ( v85 > 7 )
        std::_Deallocate<16>(*(_QWORD *)&v83.Data1, 2 * v85 + 2);
    }
  }
  else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
  }
  v44 = 0;
  v86 = 0;
  v88 = 0;
  *(double *)&v44 = std::wstring::_Construct_empty(&v86);
  v89 = v44;
  v91 = 0;
  std::wstring::_Construct_empty(&v89);
  v87 = 0;
  v45 = &v86;
  if ( v88 > 7 )
    v45 = (__int128 *)v86;
  *(_WORD *)v45 = 0;
  v90 = 0;
  v46 = &v89;
  if ( v91 > 7 )
    v46 = (__int128 *)v89;
  *(_WORD *)v46 = 0;
  if ( CJob::IsOwnedByAppPackage((CJob *)v30) )
  {
    AppPackageInfo::GetAppUserModelId(*((_QWORD *)v30 + 92), &v86);
  }
  else
  {
    v47 = CTelemetry::GetFriendlyBITSJobName((LPCWCH)(*((_QWORD *)v30 + 87) + 12LL));
    v48 = -1;
    do
      ++v48;
    while ( v47[v48] );
    std::wstring::_Assign<unsigned short>(&v86, v47);
  }
  lpsz = 0;
  v49 = StringFromCLSID(v27, &lpsz);
  if ( v49 < 0 )
  {
    v73 = 0;
    pExceptionObject = &ComError::`vftable';
    v74 = v49;
    v75 = 807;
    v76 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v50 = -1;
  do
    ++v50;
  while ( lpsz[v50] );
  std::wstring::_Assign<unsigned short>(&v89, lpsz);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  v51 = &v89;
  if ( v91 > 7 )
    v51 = (__int128 *)v89;
  PdcClientRegistrationHandle = v51;
  v52 = &v86;
  if ( v88 > 7 )
    v52 = (__int128 *)v86;
  v68 = v52;
  Context = 0;
  if ( !InitOnceExecuteOnce(&g_SmePolicyTracker, LazyGlobal<SmePolicyTracker>::LazyGlobalInitializer, 0, &Context) )
  {
    v73 = 0;
    pExceptionObject = &ComError::`vftable';
    v74 = -2147024882;
    v75 = 51;
    v76 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v71 = Context;
  v53 = (__int64 *)std::make_unique<ScopedSmeTaskHolder,SmePolicyTracker *,SmePolicyID &,unsigned short const *,unsigned short const *,0>(
                     (unsigned int)&rclsid,
                     (unsigned int)&v71,
                     (int)v30 + 1472,
                     (unsigned int)&v68,
                     (__int64)&PdcClientRegistrationHandle);
  v54 = *v53;
  *v53 = 0;
  v55 = v31[10];
  v31[10] = v54;
  if ( v55 )
    std::default_delete<ScopedSmeTaskHolder>::operator()();
  if ( rclsid )
    std::default_delete<ScopedSmeTaskHolder>::operator()();
  if ( v91 > 7 )
    std::_Deallocate<16>(v89, 2 * v91 + 2);
  v90 = 0;
  v91 = 7;
  LOWORD(v89) = 0;
  if ( v88 > 7 )
    std::_Deallocate<16>(v86, 2 * v88 + 2);
  v87 = 0;
  v88 = 7;
  LOWORD(v86) = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v26 + 2, 0xFFFFFFFF) == 1 )
  {
    v56 = *(char **)*v26;
    if ( (unsigned __int64)(v56 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v56);
      *(_QWORD *)*v26 = 0;
    }
    operator delete(*v26, 0x10u);
    *v26 = 0;
  }
  return v31;
}

```

## disassembly

```asm
0x18001bac0  mov     [rsp-8+arg_10], rbx
0x18001bac5  push    rbp
0x18001bac6  push    rsi
0x18001bac7  push    rdi
0x18001bac8  push    r12
0x18001baca  push    r13
0x18001bacc  push    r14
0x18001bace  push    r15
0x18001bad0  lea     rbp, [rsp-0E0h]
0x18001bad8  sub     rsp, 240h
0x18001badf  mov     rax, cs:__security_cookie
0x18001bae6  xor     rax, rsp
0x18001bae9  mov     [rbp+110h+var_40], rax
0x18001baf0  mov     rsi, rdx
0x18001baf3  mov     [rbp+110h+var_B0], rdx
0x18001baf7  mov     rdi, rcx
0x18001bafa  mov     [rbp+110h+lpsz], rcx
0x18001bafe  mov     [rbp+110h+var_A8], rdx
0x18001bb02  xor     r14d, r14d
0x18001bb05  mov     edx, 8; dwFlags
0x18001bb0a  mov     r8d, 58h ; 'X'; dwBytes
0x18001bb10  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18001bb17  call    cs:__imp_HeapAlloc
0x18001bb1d  test    rax, rax
0x18001bb20  jnz     short loc_18001BB8B
0x18001bb22  lea     r15, WPP_GLOBAL_Control
0x18001bb29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb30  cmp     rcx, r15
0x18001bb33  jz      short loc_18001BB56
0x18001bb35  test    byte ptr [rcx+1Ch], 4
0x18001bb39  jz      short loc_18001BB56
0x18001bb3b  mov     edx, 0Ah
0x18001bb40  mov     r9d, 58h ; 'X'
0x18001bb46  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18001bb4d  mov     rcx, [rcx+10h]
0x18001bb51  call    WPP_SF_d
0x18001bb56  xorps   xmm0, xmm0
0x18001bb59  movups  [rbp+110h+var_138], xmm0
0x18001bb5d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001bb64  mov     [rbp+110h+pExceptionObject], rcx
0x18001bb68  mov     [rbp+110h+var_128], 8007000Eh
0x18001bb6f  mov     [rbp+110h+var_124], r14d
0x18001bb73  mov     [rbp+110h+var_120], 1
0x18001bb7a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001bb81  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x18001bb85  call    _CxxThrowException_0
0x18001bb8b  mov     [rbp+110h+var_170], rax
0x18001bb8f  mov     rcx, rax; this
0x18001bb92  call    ??0TRANSFER_GLOB@CJob@@QEAA@XZ; CJob::TRANSFER_GLOB::TRANSFER_GLOB(void)
0x18001bb97  mov     r13, rax
0x18001bb9a  mov     [rbp+110h+var_170], rax
0x18001bb9e  mov     [rbp+110h+var_150], rax
0x18001bba2  cmp     dword ptr [rdi+294h], 2
0x18001bba9  jz      short loc_18001BBC0
0x18001bbab  mov     edx, 1; enum BG_JOB_STATE
0x18001bbb0  mov     rcx, rdi; this
0x18001bbb3  call    ?SetState@CJob@@IEAAXW4BG_JOB_STATE@@@Z; CJob::SetState(BG_JOB_STATE)
0x18001bbb8  mov     rcx, rdi; this
0x18001bbbb  call    ?ScheduleModificationCallback@CJob@@IEAAXXZ; CJob::ScheduleModificationCallback(void)
0x18001bbc0  movups  xmm0, xmmword ptr [rdi+530h]
0x18001bbc7  movaps  xmmword ptr [rbp+110h+var_A0.Data1], xmm0
0x18001bbcb  lea     r8, [rdi+518h]; struct CustomUserContext *
0x18001bbd2  lea     rdx, [rbp+110h+var_A0]; struct _GUID
0x18001bbd6  call    ?SignalBackgroundTransferSebEventBestEffort@CJobManager@@QEAAXU_GUID@@AEBVCustomUserContext@@@Z; CJobManager::SignalBackgroundTransferSebEventBestEffort(_GUID,CustomUserContext const &)
0x18001bbdb  mov     rax, [rdi]
0x18001bbde  mov     rcx, rdi
0x18001bbe1  mov     rax, [rax+1A8h]
0x18001bbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbed  mov     rbx, rax
0x18001bbf0  mov     [rbp+110h+var_148], rax
0x18001bbf4  test    rax, rax
0x18001bbf7  jnz     loc_18001BCA3
0x18001bbfd  mov     [rbp+110h+var_A0.Data1], 4
0x18001bc04  mov     [rbp+110h+var_90], r14
0x18001bc0b  mov     dword ptr [rbp+110h+var_A0.Data4+4], 2
0x18001bc12  mov     dword ptr [rbp+110h+var_A0.Data4], 2
0x18001bc19  mov     dword ptr [rbp+110h+var_A0.Data2], 54Fh
0x18001bc20  lea     r15, WPP_GLOBAL_Control
0x18001bc27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc2e  cmp     rcx, r15
0x18001bc31  jz      short loc_18001BC6C
0x18001bc33  test    byte ptr [rcx+1Ch], 1
0x18001bc37  jz      short loc_18001BC6C
0x18001bc39  lea     rax, qword_18011AC70
0x18001bc40  mov     [rsp+270h+var_238], rax
0x18001bc45  mov     dword ptr [rsp+270h+var_240], 2
0x18001bc4d  mov     dword ptr [rsp+270h+var_248], 54Fh
0x18001bc55  mov     dword ptr [rsp+270h+var_250], 2
0x18001bc5d  mov     r9d, 4
0x18001bc63  mov     rcx, [rcx+10h]
0x18001bc67  call    WPP_SF_llDDS
0x18001bc6c  mov     rax, [rdi]
0x18001bc6f  mov     rcx, rdi
0x18001bc72  lea     rdx, [rbp+110h+var_A0]
0x18001bc76  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001bc7d  mov     rax, [rax+1C8h]
0x18001bc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc89  nop
0x18001bc8a  lea     rcx, [rbp+110h+var_150]
0x18001bc8e  call    ??1?$unique_ptr@UTRANSFER_GLOB@CJob@@U?$default_delete@UTRANSFER_GLOB@CJob@@@std@@@std@@QEAA@XZ; std::unique_ptr<CJob::TRANSFER_GLOB>::~unique_ptr<CJob::TRANSFER_GLOB>(void)
0x18001bc93  nop
0x18001bc94  mov     rcx, rsi; this
0x18001bc97  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001bc9c  xor     eax, eax
0x18001bc9e  jmp     loc_18001C64A
0x18001bca3  mov     [rbp+110h+var_D0], 2
0x18001bcab  mov     [rbp+110h+var_C8], r14
0x18001bcaf  mov     [rbp+110h+var_C0], r14
0x18001bcb3  mov     rax, [rsi]
0x18001bcb6  mov     [rbp+110h+var_168], rax
0x18001bcba  lock inc dword ptr [rax+8]
0x18001bcbe  lea     r8, [rbp+110h+var_D0]
0x18001bcc2  lea     rdx, [rbp+110h+var_168]
0x18001bcc6  mov     rcx, rbx
0x18001bcc9  call    ?ValidateDriveInfo@CFile@@QEAA_NVTokenHandle@@AEAUQMErrInfo@@@Z; CFile::ValidateDriveInfo(TokenHandle,QMErrInfo &)
0x18001bcce  test    al, al
0x18001bcd0  jnz     short loc_18001BD25
0x18001bcd2  lea     rdx, [rbp+110h+var_D0]; struct QMErrInfo *
0x18001bcd6  mov     rcx, rdi; this
0x18001bcd9  cmp     dword ptr [rbp+110h+var_D0], 4
0x18001bcdd  jnz     short loc_18001BCF7
0x18001bcdf  mov     rax, [rdi]
0x18001bce2  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001bce9  mov     rax, [rax+1C8h]
0x18001bcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcf5  jmp     short loc_18001BD0C
0x18001bcf7  mov     [rsp+270h+var_250], 1; bool
0x18001bcfc  mov     r9b, 1; bool
0x18001bcff  mov     r8d, [rdi+348h]; int
0x18001bd06  call    ?SetTransientError@CJob@@IEAAXAEAUQMErrInfo@@J_N1@Z; CJob::SetTransientError(QMErrInfo &,long,bool,bool)
0x18001bd0b  nop
0x18001bd0c  lea     rcx, [rbp+110h+var_150]
0x18001bd10  call    ??1?$unique_ptr@UTRANSFER_GLOB@CJob@@U?$default_delete@UTRANSFER_GLOB@CJob@@@std@@@std@@QEAA@XZ; std::unique_ptr<CJob::TRANSFER_GLOB>::~unique_ptr<CJob::TRANSFER_GLOB>(void)
0x18001bd15  nop
0x18001bd16  mov     rcx, rsi; this
0x18001bd19  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001bd1e  xor     eax, eax
0x18001bd20  jmp     loc_18001C64A
0x18001bd25  mov     r10, [rbp+110h+lpsz]
0x18001bd29  cmp     dword ptr [r10+4D0h], 0
0x18001bd31  jz      loc_18001BDF1
0x18001bd37  mov     rax, [r10+4D8h]
0x18001bd3e  cmp     qword ptr [rax], 0
0x18001bd42  jnz     loc_18001BDF1
0x18001bd48  lea     r15, WPP_GLOBAL_Control
0x18001bd4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd56  cmp     rcx, r15
0x18001bd59  jz      short loc_18001BD81
0x18001bd5b  test    byte ptr [rcx+1Ch], 2
0x18001bd5f  jz      short loc_18001BD81
0x18001bd61  mov     edx, 79h ; 'y'
0x18001bd66  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001bd6d  mov     rcx, [rcx+10h]
0x18001bd71  call    WPP_SF_
0x18001bd76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd7d  mov     r10, [rbp+110h+lpsz]
0x18001bd81  mov     [rbp+110h+var_A0.Data1], 4
0x18001bd88  mov     [rbp+110h+var_90], r14
0x18001bd8f  mov     dword ptr [rbp+110h+var_A0.Data4+4], 2
0x18001bd96  mov     dword ptr [rbp+110h+var_A0.Data4], 1
0x18001bd9d  mov     dword ptr [rbp+110h+var_A0.Data2], 80200056h
0x18001bda4  cmp     rcx, r15
0x18001bda7  jz      short loc_18001BDE6
0x18001bda9  test    byte ptr [rcx+1Ch], 1
0x18001bdad  jz      short loc_18001BDE6
0x18001bdaf  lea     rax, qword_18011AC70
0x18001bdb6  mov     [rsp+270h+var_238], rax
0x18001bdbb  mov     dword ptr [rsp+270h+var_240], 2
0x18001bdc3  mov     dword ptr [rsp+270h+var_248], 80200056h
0x18001bdcb  mov     dword ptr [rsp+270h+var_250], 1
0x18001bdd3  mov     r9d, 4
0x18001bdd9  mov     rcx, [rcx+10h]
0x18001bddd  call    WPP_SF_llDDS
0x18001bde2  mov     r10, [rbp+110h+lpsz]
0x18001bde6  mov     rax, [r10]
0x18001bde9  mov     rcx, r10
0x18001bdec  jmp     loc_18001BC72
0x18001bdf1  cmp     byte ptr [rbx+103h], 0
0x18001bdf8  jnz     short loc_18001BE00
0x18001bdfa  mov     [rbp+110h+var_190], 1
0x18001bdfe  jmp     short loc_18001BE18
0x18001be00  mov     [rbp+110h+var_190], 0
0x18001be04  mov     rcx, rbx; this
0x18001be07  call    ?RangeHeadersNotSupported@CFile@@QEAAXXZ; CFile::RangeHeadersNotSupported(void)
0x18001be0c  mov     rcx, rbx; this
0x18001be0f  call    ?FileChanged@CFile@@QEAAXXZ; CFile::FileChanged(void)
0x18001be14  mov     r10, [rbp+110h+lpsz]
0x18001be18  cmp     byte ptr [r10+2A1h], 0
0x18001be20  jnz     short loc_18001BE57
0x18001be22  cmp     byte ptr [r10+510h], 0
0x18001be2a  jnz     short loc_18001BE57
0x18001be2c  mov     rax, [r10]
0x18001be2f  mov     rdx, rbx
0x18001be32  mov     rcx, r10
0x18001be35  mov     rax, [rax+1E8h]
0x18001be3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be41  test    al, al
0x18001be43  jz      short loc_18001BE53
0x18001be45  call    ?ActivateVortex@CJobManager@@QEAA_NXZ; CJobManager::ActivateVortex(void)
0x18001be4a  mov     [rbp+110h+var_18F], al
0x18001be4d  mov     r10, [rbp+110h+lpsz]
0x18001be51  jmp     short loc_18001BE5B
0x18001be53  mov     r10, [rbp+110h+lpsz]
0x18001be57  mov     [rbp+110h+var_18F], 0
0x18001be5b  mov     rax, [rbx]
0x18001be5e  mov     rax, [rax+8]
0x18001be62  mov     [rbp+110h+var_160], rax
0x18001be66  mov     rcx, r10
0x18001be69  cmp     byte ptr [r10+5E0h], 0
0x18001be71  cmovz   rcx, r14
0x18001be75  lea     rdx, [rcx+268h]
0x18001be7c  test    rcx, rcx
0x18001be7f  cmovz   rdx, r14
0x18001be83  mov     [rbp+110h+var_B8], rdx
0x18001be87  movzx   r14d, byte ptr [r10+510h]
0x18001be8f  movzx   r15d, byte ptr [r10+2E8h]
0x18001be97  movzx   r12d, byte ptr [r10+4F6h]
0x18001be9f  mov     [rbp+110h+var_18E], r12b
0x18001bea3  mov     eax, [r10+4B8h]
0x18001beaa  mov     [rbp+110h+var_158], eax
0x18001bead  mov     eax, [r10+420h]
0x18001beb4  mov     dword ptr [rbp+110h+var_168], eax
0x18001beb7  mov     rax, [r10+508h]
0x18001bebe  lock inc dword ptr [rax+8]
0x18001bec2  mov     rax, [r10+508h]
0x18001bec9  mov     [rbp+110h+var_E0], rax
0x18001becd  mov     ebx, [r10+4FCh]
0x18001bed4  mov     edi, [r10+290h]
0x18001bedb  mov     esi, [r10+4D0h]
0x18001bee2  add     r13, 38h ; '8'
0x18001bee6  mov     rax, [r10+2C8h]
0x18001beed  mov     qword ptr [rbp+110h+var_A0.Data1], rax
0x18001bef1  mov     rax, [r10+2D0h]
0x18001bef8  mov     qword ptr [rbp+110h+var_A0.Data4], rax
0x18001befc  lock inc dword ptr [rax]
0x18001beff  mov     r11d, [r10+298h]
0x18001bf06  mov     rax, [r10+2D8h]
0x18001bf0d  lock inc dword ptr [rax+8]
0x18001bf11  mov     rax, [r10+2D8h]
0x18001bf18  mov     [rbp+110h+var_D8], rax
0x18001bf1c  mov     rax, [r10+2B8h]
0x18001bf23  lock inc dword ptr [rax+8]
0x18001bf27  mov     rax, [r10+2B8h]
0x18001bf2e  mov     [rbp+110h+Context], rax
0x18001bf32  lea     rax, [r10+2A4h]
0x18001bf39  mov     [rbp+110h+rclsid], rax
0x18001bf3d  lea     rax, [r10+428h]
0x18001bf44  lea     rcx, [r10+430h]
0x18001bf4b  lea     rdx, [r10+408h]
0x18001bf52  lea     r8, [r10+3F0h]
0x18001bf59  lea     r9, [r10+4D8h]
0x18001bf60  add     r10, 391h
0x18001bf67  mov     r12, [rbp+110h+var_B8]
0x18001bf6b  mov     [rsp+270h+var_1A8], r12
0x18001bf73  mov     [rsp+270h+var_1B0], r14b
0x18001bf7b  mov     [rsp+270h+var_1B8], r15b
0x18001bf83  movzx   r14d, [rbp+110h+var_190]
0x18001bf88  mov     [rsp+270h+var_1C0], r14b
0x18001bf90  movzx   r12d, [rbp+110h+var_18E]
0x18001bf95  mov     [rsp+270h+var_1C8], r12b
0x18001bf9d  movzx   r14d, [rbp+110h+var_18F]
0x18001bfa2  mov     [rsp+270h+var_1D0], r14b
0x18001bfaa  mov     r14d, [rbp+110h+var_158]
0x18001bfae  mov     [rsp+270h+var_1D8], r14d
0x18001bfb6  mov     [rsp+270h+var_1E0], rax
0x18001bfbe  mov     [rsp+270h+var_1E8], rcx
0x18001bfc6  mov     eax, dword ptr [rbp+110h+var_168]
0x18001bfc9  mov     [rsp+270h+var_1F0], eax
0x18001bfd0  mov     [rsp+270h+var_1F8], rdx
0x18001bfd5  mov     [rsp+270h+var_200], r8
0x18001bfda  lea     rax, [rbp+110h+var_E0]
0x18001bfde  mov     [rsp+270h+var_208], rax
0x18001bfe3  mov     [rsp+270h+var_210], ebx
0x18001bfe7  mov     [rsp+270h+var_218], edi
0x18001bfeb  mov     [rsp+270h+var_220], esi
0x18001bfef  mov     [rsp+270h+var_228], r9
0x18001bff4  mov     rsi, [rbp+110h+var_B0]
0x18001bff8  mov     [rsp+270h+var_230], rsi
0x18001bffd  mov     [rsp+270h+var_238], r13
0x18001c002  mov     [rsp+270h+var_240], r10
0x18001c007  lea     rax, [rbp+110h+var_A0]
0x18001c00b  mov     [rsp+270h+var_248], rax
0x18001c010  mov     dword ptr [rsp+270h+var_250], r11d
0x18001c015  lea     r9, [rbp+110h+var_D8]
0x18001c019  lea     r8, [rbp+110h+Context]
0x18001c01d  mov     r13, [rbp+110h+rclsid]
0x18001c021  mov     rdx, r13
0x18001c024  mov     r15, [rbp+110h+var_148]
0x18001c028  mov     rcx, r15
0x18001c02b  mov     rax, [rbp+110h+var_160]
0x18001c02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c034  mov     rbx, rax
0x18001c037  mov     rcx, [rax]
0x18001c03a  mov     rax, [rcx+48h]
0x18001c03e  mov     rdi, [rbp+110h+lpsz]
0x18001c042  mov     r8, rdi
0x18001c045  lea     rdx, ?StaticProgressCallback@CJob@@SAXPEAX@Z; CJob::StaticProgressCallback(void *)
0x18001c04c  mov     rcx, rbx
0x18001c04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c054  mov     r14, [rbp+110h+var_170]
  ... truncated ...
```
