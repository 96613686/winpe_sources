# Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById(HSTRING__ *,IInspectable * *)

- ea: `0x1800bbc00`
- end: `0x1800bc60e`
- name: `?CreateClassById@EMEStoreObjectDllManager@Protection@Media@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `2574`
- prototype: `__int64 __fastcall(Windows::Media::Protection::EMEStoreObjectDllManager *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801544b0`

## callees

- `0x180004870`
- `0x180009af0`
- `0x180014488`
- `0x1800144ac`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003e9d0`
- `0x1800ac65c`
- `0x1800bbc00`
- `0x1800bc614`
- `0x180117aa0`
- `0x18011fff0`
- `0x1801200d0`
- `0x180122d9c`
- `0x18012a700`
- `0x180153c88`
- `0x180153cd8`
- `0x180153e8c`
- `0x180154ae0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bbc71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bbc71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc4a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc4a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbc3e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc410`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbc3e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc410`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbd14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbd22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbe21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbe30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbd14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbd22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbe21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbe30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbeed`
- `ext-ms-win-media-codecpack-mounting-l1-1-0!MountInProcMediaCodecDll` at `0x1800bbe3c`
- `ext-ms-win-media-codecpack-mounting-l1-1-0!MountInProcMediaCodecDll` at `0x1800bbe3c`

## string_xrefs

- `0x1800bbc81`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bbdc4`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bbeaf`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bbf6f`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc056`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc130`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc1d6`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc2a1`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc395`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc53c`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`
- `0x1800bc5e2`: `Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById`

## pseudocode

```c
__int64 __fastcall Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById(
        Windows::Media::Protection::EMEStoreObjectDllManager *this,
        HSTRING a2,
        struct IInspectable **a3)
{
  LONGLONG v4; // r13
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v9; // ebx
  _GUID *v10; // rax
  _GUID v11; // xmm0
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v13; // rax
  int v14; // edi
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  PCWSTR v17; // rbx
  PCWSTR v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CMFInprocDllManager *v21; // rbx
  const unsigned __int16 *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  struct IInspectable *v25; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CMFContentDecryptionModuleFactoryStoreWrapper *v36; // rax
  CMFContentDecryptionModuleFactoryStoreWrapper *v37; // rax
  CMFContentDecryptionModuleFactoryStoreWrapper *v38; // rbx
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  LONGLONG v41; // rbx
  unsigned __int64 v42; // rdx
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-50h] BYREF
  CallStackScopeTrace v49; // [rsp+38h] [rbp-48h] BYREF
  void *v50; // [rsp+40h] [rbp-40h] BYREF
  struct IInspectable *v51; // [rsp+48h] [rbp-38h] BYREF
  __int64 v52; // [rsp+50h] [rbp-30h] BYREF
  __int64 v53; // [rsp+58h] [rbp-28h] BYREF
  __int64 v54; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v55[2]; // [rsp+68h] [rbp-18h] BYREF

  PerformanceCount.QuadPart = 0;
  v4 = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
    v4 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v54 = 0;
  v51 = 0;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    &v49,
    "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
    157);
  v7 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 10) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 296LL))(*((_QWORD *)this + 10));
    v10 = (_GUID *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 10) + 280LL))(
                     *((_QWORD *)this + 10),
                     v55);
    v7 = CallStackTracing::s_wpInstance;
    v11 = *v10;
    ThreadRelativeContext->m_instanceId = v9;
    ThreadRelativeContext->m_sessionId = v11;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
    v13 = WindowsGetStringRawBuffer(a2, 0);
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)v13, (__int64)StringRawBuffer);
    v7 = CallStackTracing::s_wpInstance;
  }
  if ( !*((_QWORD *)this + 9) )
  {
    v14 = -1072875850;
    if ( !v7 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v15->m_result != -1072875850 )
        CallStackContext::TraceFailure(
          v15,
          "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
          159,
          -1072875850);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v16 = 28;
LABEL_18:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids, this, v14);
      goto LABEL_100;
    }
    goto LABEL_100;
  }
  if ( !(unsigned __int8)IsMountMediaCodecAppServicePackagePresent()
    || (v17 = WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0),
        v18 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0),
        v14 = MountInProcMediaCodecDll(v18, v17),
        v14 >= 0) )
  {
    v21 = (CMFInprocDllManager *)*((_QWORD *)this + 9);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v22 = WindowsGetStringRawBuffer(a2, 0);
    v14 = CMFInprocDllManager::LoadDllInternal(v21, v22, &v51);
    if ( v14 < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v23 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v23->m_fEnabled )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(v23);
        if ( v24->m_result != v14 )
          CallStackContext::TraceFailure(
            v24,
            "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
            167,
            v14);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v16 = 30;
        goto LABEL_18;
      }
      goto LABEL_100;
    }
    v25 = v51;
    QueryInterface = v51->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    if ( QueryInterface(v25, &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, (void **)&v52) < 0 )
    {
      if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<IMFContentDecryptionModuleFactory>(&v51, &v53) < 0 )
      {
        v14 = Microsoft::WRL::ComPtr<IInspectable>::As<IInspectable>(&v51, &v50);
        if ( v14 < 0 )
        {
          v46 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v46 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v46 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v46->m_fEnabled )
          {
            v47 = CallStackTracing::GetThreadRelativeContext(v46);
            if ( v47->m_result != v14 )
              CallStackContext::TraceFailure(
                v47,
                "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
                200,
                v14);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v16 = 37;
            goto LABEL_18;
          }
          goto LABEL_100;
        }
LABEL_99:
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v50);
        v14 = 0;
        *a3 = (struct IInspectable *)v50;
        goto LABEL_100;
      }
      v55[0] = *((_QWORD *)this + 9);
      PerformanceCount.QuadPart = 0;
      v14 = Microsoft::WRL::Details::MakeAndInitialize<CMFInprocLifetimeAssociation,CMFInprocLifetimeAssociation,CMFInprocDllManager *>(
              &PerformanceCount,
              v55);
      if ( v14 < 0 )
      {
        v34 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v34 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v34->m_fEnabled )
        {
          v35 = CallStackTracing::GetThreadRelativeContext(v34);
          if ( v35->m_result != v14 )
            CallStackContext::TraceFailure(
              v35,
              "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
              187,
              v14);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_52;
        v29 = 34;
        goto LABEL_51;
      }
      v36 = (CMFContentDecryptionModuleFactoryStoreWrapper *)operator new(0x40u);
      if ( !v36
        || (v37 = CMFContentDecryptionModuleFactoryStoreWrapper::CMFContentDecryptionModuleFactoryStoreWrapper(
                    v36,
                    v25,
                    (struct CMFInprocLifetimeAssociation *)PerformanceCount.QuadPart,
                    *((struct IMFTelemetrySession **)this + 10),
                    *((HSTRING *)this + 12)),
            (v38 = v37) == 0) )
      {
        v44 = CallStackTracing::s_wpInstance;
        v14 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v44 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v44->m_fEnabled )
        {
          v45 = CallStackTracing::GetThreadRelativeContext(v44);
          if ( v45->m_result != -2147024882 )
            CallStackContext::TraceFailure(
              v45,
              "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
              194,
              -2147024882);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_52;
        v29 = 35;
        goto LABEL_51;
      }
      _InterlockedIncrement((volatile signed __int32 *)v37 + 14);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      v14 = CMFContentDecryptionModuleFactoryStoreWrapper::QueryInterface(
              v38,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              &v50);
      if ( v14 < 0 )
      {
        v39 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v39 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v39->m_fEnabled )
        {
          v40 = CallStackTracing::GetThreadRelativeContext(v39);
          if ( v40->m_result != v14 )
            CallStackContext::TraceFailure(
              v40,
              "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
              196,
              v14);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids, this, v14);
        CMFContentDecryptionModuleFactoryStoreWrapper::Release(v38);
        goto LABEL_52;
      }
      CMFContentDecryptionModuleFactoryStoreWrapper::Release(v38);
    }
    else
    {
      v55[0] = *((_QWORD *)this + 9);
      PerformanceCount.QuadPart = 0;
      v14 = Microsoft::WRL::Details::MakeAndInitialize<CMFInprocLifetimeAssociation,CMFInprocLifetimeAssociation,CMFInprocDllManager *>(
              &PerformanceCount,
              v55);
      if ( v14 < 0 )
      {
        v27 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v27 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v27->m_fEnabled )
        {
          v28 = CallStackTracing::GetThreadRelativeContext(v27);
          if ( v28->m_result != v14 )
            CallStackContext::TraceFailure(
              v28,
              "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
              175,
              v14);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_52;
        v29 = 31;
LABEL_51:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids, this, v14);
LABEL_52:
        Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&PerformanceCount);
        goto LABEL_100;
      }
      v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, LARGE_INTEGER))(*(_QWORD *)v52 + 216LL))(
              v52,
              MF_INPROCDLL_LIFETIME_MANAGER,
              PerformanceCount);
      if ( v14 < 0 )
      {
        v30 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v30 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v30->m_fEnabled )
        {
          v31 = CallStackTracing::GetThreadRelativeContext(v30);
          if ( v31->m_result != v14 )
            CallStackContext::TraceFailure(
              v31,
              "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
              176,
              v14);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_52;
        v29 = 32;
        goto LABEL_51;
      }
      v14 = Microsoft::WRL::ComPtr<IInspectable>::As<IInspectable>(&v51, &v50);
      if ( v14 < 0 )
      {
        v32 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v32 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v32->m_fEnabled )
        {
          v33 = CallStackTracing::GetThreadRelativeContext(v32);
          if ( v33->m_result != v14 )
            CallStackContext::TraceFailure(
              v33,
              "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
              178,
              v14);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_52;
        v29 = 33;
        goto LABEL_51;
      }
    }
    Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&PerformanceCount);
    goto LABEL_99;
  }
  v19 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v19 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v19 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v19->m_fEnabled )
  {
    v20 = CallStackTracing::GetThreadRelativeContext(v19);
    if ( v20->m_result != v14 )
      CallStackContext::TraceFailure(
        v20,
        "Windows::Media::Protection::EMEStoreObjectDllManager::CreateClassById",
        164,
        v14);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v16 = 29;
    goto LABEL_18;
  }
LABEL_100:
  v41 = 0;
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
    v41 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
  v42 = (__int64)((unsigned __int128)((v41 - v4) * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
  Windows::Media::Protection::EMEStoreObjectDllManager::LogEMEObjectActivateTelemetry(this, v14, a2, v42 + (v42 >> 63));
  CallStackScopeTrace::~CallStackScopeTrace(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  if ( this != (Windows::Media::Protection::EMEStoreObjectDllManager *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800bbc00  mov     [rsp-38h+arg_18], rbx
0x1800bbc05  push    rbp
0x1800bbc06  push    rsi
0x1800bbc07  push    rdi
0x1800bbc08  push    r12
0x1800bbc0a  push    r13
0x1800bbc0c  push    r14
0x1800bbc0e  push    r15
0x1800bbc10  mov     rbp, rsp
0x1800bbc13  sub     rsp, 80h
0x1800bbc1a  mov     rax, cs:__security_cookie
0x1800bbc21  xor     rax, rsp
0x1800bbc24  mov     [rbp+var_8], rax
0x1800bbc28  mov     rsi, rcx
0x1800bbc2b  xor     ebx, ebx
0x1800bbc2d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800bbc31  mov     qword ptr [rbp+PerformanceCount], rbx
0x1800bbc35  mov     r13d, ebx
0x1800bbc38  mov     r14, r8
0x1800bbc3b  mov     r12, rdx
0x1800bbc3e  call    cs:__imp_QueryPerformanceCounter
0x1800bbc44  test    eax, eax
0x1800bbc46  jz      short loc_1800BBC6A
0x1800bbc48  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1800bbc4c  xor     r9d, r9d; d
0x1800bbc4f  sub     rcx, cs:qword_1801FCD08; a
0x1800bbc56  mov     edx, 989680h; b
0x1800bbc5b  mov     r8, cs:c; c
0x1800bbc62  call    MFllMulDiv
0x1800bbc67  mov     r13, rax
0x1800bbc6a  lea     r15, [rsi+20h]
0x1800bbc6e  mov     rcx, r15; lpCriticalSection
0x1800bbc71  call    cs:__imp_EnterCriticalSection
0x1800bbc77  mov     r8d, 9Dh; int
0x1800bbc7d  mov     [rbp+var_20], rbx
0x1800bbc81  lea     rdx, aWindowsMediaPr_1; "Windows::Media::Protection::EMEStoreObj"...
0x1800bbc88  mov     [rbp+var_38], rbx
0x1800bbc8c  lea     rcx, [rbp+var_48]; this
0x1800bbc90  mov     [rbp+var_40], rbx
0x1800bbc94  mov     [rbp+var_30], rbx
0x1800bbc98  mov     [rbp+var_28], rbx
0x1800bbc9c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bbca1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bbca8  cmp     [rcx+8], bl
0x1800bbcab  jz      short loc_1800BBD05
0x1800bbcad  cmp     [rsi+50h], rbx
0x1800bbcb1  jz      short loc_1800BBD05
0x1800bbcb3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbcb8  mov     rdx, [rsi+50h]
0x1800bbcbc  mov     rdi, rax
0x1800bbcbf  mov     rcx, [rdx]
0x1800bbcc2  mov     rax, [rcx+128h]
0x1800bbcc9  mov     rcx, rdx
0x1800bbccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbcd1  mov     r8, [rsi+50h]
0x1800bbcd5  lea     rdx, [rbp+var_18]
0x1800bbcd9  mov     ebx, eax
0x1800bbcdb  mov     rcx, [r8]
0x1800bbcde  mov     rax, [rcx+118h]
0x1800bbce5  mov     rcx, r8
0x1800bbce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbced  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbcf4  movups  xmm0, xmmword ptr [rax]
0x1800bbcf7  mov     [rdi+7E0h], ebx
0x1800bbcfd  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800bbd05  cmp     cs:byte_1801FD289, 10h
0x1800bbd0c  jb      short loc_1800BBD58
0x1800bbd0e  mov     rcx, [rsi+60h]; string
0x1800bbd12  xor     edx, edx; length
0x1800bbd14  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bbd1a  xor     edx, edx; length
0x1800bbd1c  mov     rcx, r12; string
0x1800bbd1f  mov     rbx, rax
0x1800bbd22  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bbd28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbd2f  lea     r8, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids
0x1800bbd36  mov     edx, 1Bh
0x1800bbd3b  mov     [rsp+80h+var_58], rbx; __int64
0x1800bbd40  mov     r9, rsi
0x1800bbd43  mov     [rsp+80h+var_60], rax; __int64
0x1800bbd48  mov     rcx, [rcx+38h]; LoggerHandle
0x1800bbd4c  call    WPP_SF_qSS
0x1800bbd51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbd58  cmp     qword ptr [rsi+48h], 0
0x1800bbd5d  jnz     loc_1800BBE0E
0x1800bbd63  mov     edi, 0C00D36B6h
0x1800bbd68  test    rcx, rcx
0x1800bbd6b  jnz     short loc_1800BBDAE
0x1800bbd6d  mov     rax, cs:stru_1801FC290.__vftable
0x1800bbd74  lea     r8, stru_1801FC290
0x1800bbd7b  mov     edx, 7F0h
0x1800bbd80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbd87  mov     rcx, r8
0x1800bbd8a  mov     rax, [rax+8]
0x1800bbd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd93  test    eax, eax
0x1800bbd95  jnz     short loc_1800BBDA7
0x1800bbd97  lea     rcx, stru_1801F8A30
0x1800bbd9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbda5  jmp     short loc_1800BBDAE
0x1800bbda7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bbdae  cmp     byte ptr [rcx+8], 0
0x1800bbdb2  jz      short loc_1800BBDD9
0x1800bbdb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbdb9  cmp     [rax+7CCh], edi
0x1800bbdbf  jz      short loc_1800BBDD9
0x1800bbdc1  mov     r9d, edi; int
0x1800bbdc4  lea     rdx, aWindowsMediaPr_1; "Windows::Media::Protection::EMEStoreObj"...
0x1800bbdcb  mov     r8d, 9Fh; int
0x1800bbdd1  mov     rcx, rax; this
0x1800bbdd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bbdd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bbde0  jb      loc_1800BC406
0x1800bbde6  mov     edx, 1Ch
0x1800bbdeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbdf2  lea     r8, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids
0x1800bbdf9  mov     r9, rsi
0x1800bbdfc  mov     dword ptr [rsp+80h+var_60], edi
0x1800bbe00  mov     rcx, [rcx+10h]
0x1800bbe04  call    WPP_SF_qD
0x1800bbe09  jmp     loc_1800BC406
0x1800bbe0e  call    IsMountMediaCodecAppServicePackagePresent
0x1800bbe13  test    al, al
0x1800bbe15  jz      loc_1800BBEDB
0x1800bbe1b  mov     rcx, [rsi+58h]; string
0x1800bbe1f  xor     edx, edx; length
0x1800bbe21  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bbe27  mov     rcx, [rsi+60h]; string
0x1800bbe2b  xor     edx, edx; length
0x1800bbe2d  mov     rbx, rax
0x1800bbe30  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bbe36  mov     rcx, rax
0x1800bbe39  mov     rdx, rbx
0x1800bbe3c  call    cs:__imp_MountInProcMediaCodecDll
0x1800bbe42  mov     edi, eax
0x1800bbe44  test    eax, eax
0x1800bbe46  jns     loc_1800BBEDB
0x1800bbe4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbe53  test    rcx, rcx
0x1800bbe56  jnz     short loc_1800BBE99
0x1800bbe58  mov     rcx, cs:stru_1801FC290.__vftable
0x1800bbe5f  lea     r8, stru_1801FC290
0x1800bbe66  mov     edx, 7F0h
0x1800bbe6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbe72  mov     rax, [rcx+8]
0x1800bbe76  mov     rcx, r8
0x1800bbe79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe7e  test    eax, eax
0x1800bbe80  jnz     short loc_1800BBE92
0x1800bbe82  lea     rcx, stru_1801F8A30
0x1800bbe89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbe90  jmp     short loc_1800BBE99
0x1800bbe92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bbe99  cmp     byte ptr [rcx+8], 0
0x1800bbe9d  jz      short loc_1800BBEC4
0x1800bbe9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbea4  cmp     [rax+7CCh], edi
0x1800bbeaa  jz      short loc_1800BBEC4
0x1800bbeac  mov     r9d, edi; int
0x1800bbeaf  lea     rdx, aWindowsMediaPr_1; "Windows::Media::Protection::EMEStoreObj"...
0x1800bbeb6  mov     r8d, 0A4h; int
0x1800bbebc  mov     rcx, rax; this
0x1800bbebf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bbec4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bbecb  jb      loc_1800BC406
0x1800bbed1  mov     edx, 1Dh
0x1800bbed6  jmp     loc_1800BBDEB
0x1800bbedb  mov     rbx, [rsi+48h]
0x1800bbedf  lea     rcx, [rbp+var_38]
0x1800bbee3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bbee8  xor     edx, edx; length
0x1800bbeea  mov     rcx, r12; string
0x1800bbeed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bbef3  lea     r8, [rbp+var_38]; struct IInspectable **
0x1800bbef7  mov     rcx, rbx; this
0x1800bbefa  mov     rdx, rax; unsigned __int16 *
0x1800bbefd  call    ?LoadDllInternal@CMFInprocDllManager@@QEAAJPEBGPEAPEAUIInspectable@@@Z; CMFInprocDllManager::LoadDllInternal(ushort const *,IInspectable * *)
0x1800bbf02  mov     edi, eax
0x1800bbf04  test    eax, eax
0x1800bbf06  jns     loc_1800BBF9B
0x1800bbf0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbf13  test    rcx, rcx
0x1800bbf16  jnz     short loc_1800BBF59
0x1800bbf18  mov     rax, cs:stru_1801FC290.__vftable
0x1800bbf1f  lea     r8, stru_1801FC290
0x1800bbf26  mov     edx, 7F0h
0x1800bbf2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbf32  mov     rcx, r8
0x1800bbf35  mov     rax, [rax+8]
0x1800bbf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf3e  test    eax, eax
0x1800bbf40  jnz     short loc_1800BBF52
0x1800bbf42  lea     rcx, stru_1801F8A30
0x1800bbf49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbf50  jmp     short loc_1800BBF59
0x1800bbf52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bbf59  cmp     byte ptr [rcx+8], 0
0x1800bbf5d  jz      short loc_1800BBF84
0x1800bbf5f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbf64  cmp     [rax+7CCh], edi
0x1800bbf6a  jz      short loc_1800BBF84
0x1800bbf6c  mov     r9d, edi; int
0x1800bbf6f  lea     rdx, aWindowsMediaPr_1; "Windows::Media::Protection::EMEStoreObj"...
0x1800bbf76  mov     r8d, 0A7h; int
0x1800bbf7c  mov     rcx, rax; this
0x1800bbf7f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bbf84  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bbf8b  jb      loc_1800BC406
0x1800bbf91  mov     edx, 1Eh
0x1800bbf96  jmp     loc_1800BBDEB
0x1800bbf9b  mov     rbx, [rbp+var_38]
0x1800bbf9f  lea     rcx, [rbp+var_30]
0x1800bbfa3  mov     rax, [rbx]
0x1800bbfa6  mov     rdi, [rax]
0x1800bbfa9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bbfae  lea     r8, [rbp+var_30]
0x1800bbfb2  mov     rcx, rbx
0x1800bbfb5  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800bbfbc  mov     rax, rdi
0x1800bbfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfc4  test    eax, eax
0x1800bbfc6  js      loc_1800BC202
0x1800bbfcc  mov     rax, [rsi+48h]
0x1800bbfd0  lea     rdx, [rbp+var_18]
0x1800bbfd4  lea     rcx, [rbp+PerformanceCount]
0x1800bbfd8  mov     [rbp+var_18], rax
0x1800bbfdc  mov     qword ptr [rbp+PerformanceCount], 0
0x1800bbfe4  call    ??$MakeAndInitialize@VCMFInprocLifetimeAssociation@@V1@PEAVCMFInprocDllManager@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@@012@$$QEAPEAVCMFInprocDllManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMFInprocLifetimeAssociation,CMFInprocLifetimeAssociation,CMFInprocDllManager *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>>,CMFInprocDllManager * &&)
0x1800bbfe9  mov     edi, eax
0x1800bbfeb  test    eax, eax
0x1800bbfed  jns     loc_1800BC0A5
0x1800bbff3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbffa  test    rcx, rcx
0x1800bbffd  jnz     short loc_1800BC040
0x1800bbfff  mov     rax, cs:stru_1801FC290.__vftable
0x1800bc006  lea     r8, stru_1801FC290
0x1800bc00d  mov     edx, 7F0h
0x1800bc012  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc019  mov     rcx, r8
0x1800bc01c  mov     rax, [rax+8]
0x1800bc020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc025  test    eax, eax
0x1800bc027  jnz     short loc_1800BC039
0x1800bc029  lea     rcx, stru_1801F8A30
0x1800bc030  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc037  jmp     short loc_1800BC040
0x1800bc039  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bc040  cmp     byte ptr [rcx+8], 0
0x1800bc044  jz      short loc_1800BC06B
0x1800bc046  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc04b  cmp     [rax+7CCh], edi
0x1800bc051  jz      short loc_1800BC06B
0x1800bc053  mov     r9d, edi; int
0x1800bc056  lea     rdx, aWindowsMediaPr_1; "Windows::Media::Protection::EMEStoreObj"...
0x1800bc05d  mov     r8d, 0AFh; int
0x1800bc063  mov     rcx, rax; this
0x1800bc066  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc06b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bc072  jb      short loc_1800BC097
0x1800bc074  mov     edx, 1Fh
0x1800bc079  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc080  lea     r8, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids
0x1800bc087  mov     r9, rsi
0x1800bc08a  mov     dword ptr [rsp+80h+var_60], edi
0x1800bc08e  mov     rcx, [rcx+10h]
0x1800bc092  call    WPP_SF_qD
0x1800bc097  lea     rcx, [rbp+PerformanceCount]
0x1800bc09b  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x1800bc0a0  jmp     loc_1800BC406
0x1800bc0a5  mov     rcx, [rbp+var_30]
0x1800bc0a9  lea     rdx, MF_INPROCDLL_LIFETIME_MANAGER
0x1800bc0b0  mov     r8, qword ptr [rbp+PerformanceCount]
0x1800bc0b4  mov     rax, [rcx]
0x1800bc0b7  mov     rax, [rax+0D8h]
0x1800bc0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc0c3  mov     edi, eax
0x1800bc0c5  test    eax, eax
0x1800bc0c7  jns     loc_1800BC15C
0x1800bc0cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc0d4  test    rcx, rcx
0x1800bc0d7  jnz     short loc_1800BC11A
0x1800bc0d9  mov     rax, cs:stru_1801FC290.__vftable
0x1800bc0e0  lea     r8, stru_1801FC290
0x1800bc0e7  mov     edx, 7F0h
0x1800bc0ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc0f3  mov     rcx, r8
0x1800bc0f6  mov     rax, [rax+8]
0x1800bc0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc0ff  test    eax, eax
0x1800bc101  jnz     short loc_1800BC113
0x1800bc103  lea     rcx, stru_1801F8A30
0x1800bc10a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc111  jmp     short loc_1800BC11A
0x1800bc113  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bc11a  cmp     byte ptr [rcx+8], 0
0x1800bc11e  jz      short loc_1800BC145
0x1800bc120  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc125  cmp     [rax+7CCh], edi
0x1800bc12b  jz      short loc_1800BC145
0x1800bc12d  mov     r9d, edi; int
  ... truncated ...
```
