# CMFWinrtInprocActivate::ActivateObject(_GUID const &,void * *)

- ea: `0x18003d890`
- end: `0x18003e33c`
- name: `?ActivateObject@CMFWinrtInprocActivate@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `2732`
- prototype: `__int64 __fastcall(struct IMFAttributes *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004870`
- `0x180009af0`
- `0x180012500`
- `0x1800144ac`
- `0x1800153c4`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003d890`
- `0x18003e350`
- `0x18003e538`
- `0x18003f178`
- `0x18003f43c`
- `0x1800a2df4`
- `0x180122d9c`
- `0x1801250c8`
- `0x180152644`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d8f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d8f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e323`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e323`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d8bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003e2b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d8bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003e2b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003deba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e08b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003deba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e08b`
- `ext-ms-win-media-codecpack-mounting-l1-1-0!MountInProcMediaCodecDll` at `0x18003ddfe`
- `ext-ms-win-media-codecpack-mounting-l1-1-0!MountInProcMediaCodecDll` at `0x18003ddfe`

## pseudocode

```c
__int64 __fastcall CMFWinrtInprocActivate::ActivateObject(
        struct IMFAttributes *this,
        const struct _GUID *a2,
        void **a3)
{
  struct IMFAttributes *v4; // r14
  int AllocatedString; // esi
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  void *v16; // rcx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  char v19; // al
  unsigned __int16 *v20; // rdi
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  void *QuadPart; // rcx
  void *v24; // rbx
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  CGlobalInprocDllManager *v27; // rcx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  unsigned __int16 *v30; // rbx
  CMFInprocDllManager *v31; // r12
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  LONGLONG v41; // rbx
  unsigned __int64 v42; // rdx
  unsigned __int16 *v44; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  LONGLONG v46; // [rsp+40h] [rbp-18h]
  LARGE_INTEGER PerformanceCount; // [rsp+A0h] [rbp+48h] BYREF
  const struct _GUID *v48; // [rsp+A8h] [rbp+50h]
  void **v49; // [rsp+B0h] [rbp+58h]
  CMFInprocDllManager *v50; // [rsp+B8h] [rbp+60h] BYREF

  v49 = a3;
  v48 = a2;
  v46 = 0;
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
    v46 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)&this[11]);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&PerformanceCount,
    "CMFWinrtInprocActivate::ActivateObject",
    73);
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids, this);
  v4 = this + 17;
  if ( this[16].__vftable )
    goto LABEL_113;
  if ( !LODWORD(v4->__vftable) )
  {
    v44 = 0;
    pv = 0;
    v50 = 0;
    AllocatedString = DeployPackageIfNeeded(this);
    if ( AllocatedString < 0 )
    {
      v6 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v6 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v6->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
        if ( ThreadRelativeContext->m_result != AllocatedString )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFWinrtInprocActivate::ActivateObject",
            83,
            AllocatedString);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_18;
      v8 = 14;
LABEL_17:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
        this,
        AllocatedString);
LABEL_18:
      Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&v50);
      CoTaskMemFree(0);
      v9 = 0;
LABEL_19:
      CoTaskMemFree(v9);
      goto LABEL_144;
    }
    LOBYTE(PerformanceCount.LowPart) = 0;
    AllocatedString = ValidateCodecPackage(this, (unsigned __int8 *)&PerformanceCount);
    if ( AllocatedString < 0 )
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v10->m_fEnabled )
      {
        v11 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( v11->m_result != AllocatedString )
          CallStackContext::TraceFailure(v11, "CMFWinrtInprocActivate::ActivateObject", 86, AllocatedString);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_18;
      v8 = 15;
      goto LABEL_17;
    }
    if ( !LOBYTE(PerformanceCount.LowPart) )
    {
      v12 = CallStackTracing::s_wpInstance;
      AllocatedString = -1072843853;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v12->m_fEnabled )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( v13->m_result != -1072843853 )
          CallStackContext::TraceFailure(v13, "CMFWinrtInprocActivate::ActivateObject", 89, -1072843853);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_18;
      v8 = 16;
      goto LABEL_17;
    }
    AllocatedString = CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(
                        this,
                        &MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID,
                        &v44,
                        0);
    if ( AllocatedString < 0 )
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v14 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v14->m_fEnabled )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v14);
        if ( v15->m_result != AllocatedString )
          CallStackContext::TraceFailure(v15, "CMFWinrtInprocActivate::ActivateObject", 92, AllocatedString);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
          this,
          AllocatedString);
      Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&v50);
      v16 = 0;
      goto LABEL_51;
    }
    AllocatedString = CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(
                        this,
                        &MF_MEDIA_EXTENSION_ABSOLUTE_DLLPATH,
                        &pv,
                        0);
    if ( AllocatedString < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v17->m_fEnabled )
      {
        v18 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( v18->m_result != AllocatedString )
          CallStackContext::TraceFailure(v18, "CMFWinrtInprocActivate::ActivateObject", 93, AllocatedString);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
          this,
          AllocatedString);
      Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&v50);
      v16 = pv;
      goto LABEL_51;
    }
    v19 = IsMountMediaCodecAppServicePackagePresent();
    v20 = (unsigned __int16 *)pv;
    if ( v19 )
    {
      PerformanceCount.QuadPart = 0;
      AllocatedString = CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(
                          this,
                          &MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME,
                          &PerformanceCount,
                          0);
      if ( AllocatedString < 0 )
      {
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v21->m_fEnabled )
        {
          v22 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( v22->m_result != AllocatedString )
            CallStackContext::TraceFailure(v22, "CMFWinrtInprocActivate::ActivateObject", 98, AllocatedString);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
            this,
            AllocatedString);
        QuadPart = (void *)PerformanceCount.QuadPart;
LABEL_75:
        CoTaskMemFree(QuadPart);
LABEL_76:
        Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&v50);
        v16 = v20;
LABEL_51:
        CoTaskMemFree(v16);
        v9 = v44;
        goto LABEL_19;
      }
      v24 = (void *)PerformanceCount.QuadPart;
      AllocatedString = ((__int64 (__fastcall *)(_QWORD, _QWORD))MountInProcMediaCodecDll)(
                          (LARGE_INTEGER)PerformanceCount.QuadPart,
                          v20);
      if ( AllocatedString < 0 )
      {
        v25 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v25 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v25->m_fEnabled )
        {
          v26 = CallStackTracing::GetThreadRelativeContext(v25);
          if ( v26->m_result != AllocatedString )
            CallStackContext::TraceFailure(v26, "CMFWinrtInprocActivate::ActivateObject", 101, AllocatedString);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
            this,
            AllocatedString);
        QuadPart = v24;
        goto LABEL_75;
      }
      CoTaskMemFree(v24);
    }
    Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&v50);
    AllocatedString = CGlobalInprocDllManager::GetDllManager(v27, v20, &v50);
    if ( AllocatedString < 0 )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v28 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v28->m_fEnabled )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(v28);
        if ( v29->m_result != AllocatedString )
          CallStackContext::TraceFailure(v29, "CMFWinrtInprocActivate::ActivateObject", 104, AllocatedString);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
          this,
          AllocatedString);
      goto LABEL_76;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[16]);
    v30 = v44;
    v31 = v50;
    AllocatedString = CMFInprocDllManager::LoadDll(v50, v44, (struct IInspectable **)&this[16]);
    if ( AllocatedString < 0 )
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
        if ( v33->m_result != AllocatedString )
          CallStackContext::TraceFailure(v33, "CMFWinrtInprocActivate::ActivateObject", 105, AllocatedString);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
          this,
          AllocatedString);
      Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&v50);
      CoTaskMemFree(v20);
      v9 = v30;
      goto LABEL_19;
    }
    if ( v31 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v31);
    CoTaskMemFree(v20);
    CoTaskMemFree(v30);
LABEL_113:
    AllocatedString = (*(__int64 (__fastcall **)(IMFAttributes_vtbl *, const struct _GUID *, void **))this[16].QueryInterface)(
                        this[16].__vftable,
                        v48,
                        v49);
    if ( AllocatedString < 0 )
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
        v38 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( v38->m_result != AllocatedString )
          CallStackContext::TraceFailure(v38, "CMFWinrtInprocActivate::ActivateObject", 117, AllocatedString);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v37 = 25;
        goto LABEL_143;
      }
    }
    goto LABEL_144;
  }
  if ( LODWORD(v4->__vftable) != 1 )
  {
    v39 = CallStackTracing::s_wpInstance;
    AllocatedString = -2147418113;
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
      if ( v40->m_result != -2147418113 )
        CallStackContext::TraceFailure(v40, "CMFWinrtInprocActivate::ActivateObject", 113, -2147418113);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v37 = 24;
      goto LABEL_143;
    }
    goto LABEL_144;
  }
  PerformanceCount.QuadPart = (__int64)this;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[16]);
  AllocatedString = Microsoft::WRL::Details::MakeAndInitialize<CMFWinrtInprocByteStreamHandler,IInspectable,CMFWinrtInprocActivate *>(
                      &this[16],
                      &PerformanceCount);
  if ( AllocatedString >= 0 )
    goto LABEL_113;
  v35 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v35 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v35 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v35->m_fEnabled )
  {
    v36 = CallStackTracing::GetThreadRelativeContext(v35);
    if ( v36->m_result != AllocatedString )
      CallStackContext::TraceFailure(v36, "CMFWinrtInprocActivate::ActivateObject", 109, AllocatedString);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v37 = 23;
LABEL_143:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v37,
      &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
      this,
      AllocatedString);
  }
LABEL_144:
  PerformanceCount.QuadPart = 0;
  v41 = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
    v41 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
  if ( !LODWORD(v4->__vftable) )
  {
    v42 = (__int64)((unsigned __int128)((v41 - v46) * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
    CMFWinrtInprocActivate::LogInProcTransformTelemetry(
      (CMFWinrtInprocActivate *)this,
      AllocatedString,
      v42 + (v42 >> 63));
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&PerformanceCount);
  if ( this != (struct IMFAttributes *)-88LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)&this[11]);
  return (unsigned int)AllocatedString;
}

```

## disassembly

```asm
0x18003d890  mov     [rsp-40h+arg_10], r8
0x18003d895  mov     [rsp-40h+arg_8], rdx
0x18003d89a  push    rbp
0x18003d89b  push    rbx
0x18003d89c  push    rsi
0x18003d89d  push    rdi
0x18003d89e  push    r12
0x18003d8a0  push    r13
0x18003d8a2  push    r14
0x18003d8a4  push    r15
0x18003d8a6  mov     rbp, rsp
0x18003d8a9  sub     rsp, 58h
0x18003d8ad  mov     r15, rcx
0x18003d8b0  xor     r12d, r12d
0x18003d8b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003d8b7  mov     [rbp+var_18], r12
0x18003d8bb  mov     qword ptr [rbp+PerformanceCount], r12
0x18003d8bf  call    cs:__imp_QueryPerformanceCounter
0x18003d8c5  test    eax, eax
0x18003d8c7  jz      short loc_18003D8EC
0x18003d8c9  mov     rcx, qword ptr [rbp+PerformanceCount]
0x18003d8cd  xor     r9d, r9d; d
0x18003d8d0  sub     rcx, cs:qword_1801FCD08; a
0x18003d8d7  mov     edx, 989680h; b
0x18003d8dc  mov     r8, cs:c; c
0x18003d8e3  call    MFllMulDiv
0x18003d8e8  mov     [rbp+var_18], rax
0x18003d8ec  lea     rcx, [r15+58h]; lpCriticalSection
0x18003d8f0  call    cs:__imp_EnterCriticalSection
0x18003d8f6  lea     rbx, aCmfwinrtinproc_3; "CMFWinrtInprocActivate::ActivateObject"
0x18003d8fd  mov     r8d, 49h ; 'I'; int
0x18003d903  mov     rdx, rbx; char *
0x18003d906  lea     rcx, [rbp+PerformanceCount]; this
0x18003d90a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d90f  cmp     cs:byte_1801FD289, 10h
0x18003d916  lea     rdi, WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids
0x18003d91d  jb      short loc_18003D93A
0x18003d91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d926  mov     edx, 0Dh
0x18003d92b  mov     r9, r15
0x18003d92e  mov     r8, rdi
0x18003d931  mov     rcx, [rcx+38h]
0x18003d935  call    WPP_SF_q
0x18003d93a  lea     r13, [r15+80h]
0x18003d941  lea     r14, [r15+88h]
0x18003d948  cmp     [r13+0], r12
0x18003d94c  jnz     loc_18003E0A2
0x18003d952  cmp     [r14], r12d
0x18003d955  jnz     loc_18003E111
0x18003d95b  mov     rcx, r15; struct IMFAttributes *
0x18003d95e  mov     [rbp+var_28], r12
0x18003d962  mov     [rbp+pv], r12
0x18003d966  mov     [rbp+arg_18], r12
0x18003d96a  call    ?DeployPackageIfNeeded@@YAJPEAUIMFAttributes@@@Z; DeployPackageIfNeeded(IMFAttributes *)
0x18003d96f  mov     esi, eax
0x18003d971  test    eax, eax
0x18003d973  jns     loc_18003DA30
0x18003d979  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d980  test    rcx, rcx
0x18003d983  jnz     short loc_18003D9C3
0x18003d985  mov     rdx, cs:stru_1801FC290.__vftable
0x18003d98c  lea     rcx, stru_1801FC290
0x18003d993  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d99a  mov     rax, [rdx+8]
0x18003d99e  mov     edx, 7F0h
0x18003d9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9a8  test    eax, eax
0x18003d9aa  jnz     short loc_18003D9BC
0x18003d9ac  lea     rcx, stru_1801F8A30
0x18003d9b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9ba  jmp     short loc_18003D9C3
0x18003d9bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003d9c3  cmp     [rcx+8], r12b
0x18003d9c7  jz      short loc_18003D9EA
0x18003d9c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d9ce  cmp     [rax+7CCh], esi
0x18003d9d4  jz      short loc_18003D9EA
0x18003d9d6  mov     r9d, esi; int
0x18003d9d9  mov     r8d, 53h ; 'S'; int
0x18003d9df  mov     rdx, rbx; char *
0x18003d9e2  mov     rcx, rax; this
0x18003d9e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d9ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d9f1  jb      short loc_18003DA12
0x18003d9f3  mov     edx, 0Eh
0x18003d9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9ff  mov     r9, r15
0x18003da02  mov     r8, rdi
0x18003da05  mov     [rsp+58h+var_38], esi
0x18003da09  mov     rcx, [rcx+10h]
0x18003da0d  call    WPP_SF_qD
0x18003da12  lea     rcx, [rbp+arg_18]
0x18003da16  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x18003da1b  xor     ecx, ecx; pv
0x18003da1d  call    cs:__imp_CoTaskMemFree
0x18003da23  xor     ecx, ecx; pv
0x18003da25  call    cs:__imp_CoTaskMemFree
0x18003da2b  jmp     loc_18003E2A8
0x18003da30  lea     rdx, [rbp+PerformanceCount]; unsigned __int8 *
0x18003da34  mov     byte ptr [rbp+PerformanceCount], r12b
0x18003da38  mov     rcx, r15; struct IMFAttributes *
0x18003da3b  call    ?ValidateCodecPackage@@YAJPEAUIMFAttributes@@PEAE@Z; ValidateCodecPackage(IMFAttributes *,uchar *)
0x18003da40  mov     esi, eax
0x18003da42  test    eax, eax
0x18003da44  jns     loc_18003DAD2
0x18003da4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da51  test    rcx, rcx
0x18003da54  jnz     short loc_18003DA94
0x18003da56  mov     rax, cs:stru_1801FC290.__vftable
0x18003da5d  lea     rcx, stru_1801FC290
0x18003da64  mov     edx, 7F0h
0x18003da69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da70  mov     rax, [rax+8]
0x18003da74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da79  test    eax, eax
0x18003da7b  jnz     short loc_18003DA8D
0x18003da7d  lea     rcx, stru_1801F8A30
0x18003da84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da8b  jmp     short loc_18003DA94
0x18003da8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003da94  cmp     [rcx+8], r12b
0x18003da98  jz      short loc_18003DABB
0x18003da9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003da9f  cmp     [rax+7CCh], esi
0x18003daa5  jz      short loc_18003DABB
0x18003daa7  mov     r9d, esi; int
0x18003daaa  mov     r8d, 56h ; 'V'; int
0x18003dab0  mov     rdx, rbx; char *
0x18003dab3  mov     rcx, rax; this
0x18003dab6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003dabb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dac2  jb      loc_18003DA12
0x18003dac8  mov     edx, 0Fh
0x18003dacd  jmp     loc_18003D9F8
0x18003dad2  cmp     byte ptr [rbp+PerformanceCount], r12b
0x18003dad6  jnz     loc_18003DB69
0x18003dadc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dae3  mov     esi, 0C00DB3B3h
0x18003dae8  test    rcx, rcx
0x18003daeb  jnz     short loc_18003DB2B
0x18003daed  mov     rax, cs:stru_1801FC290.__vftable
0x18003daf4  lea     rcx, stru_1801FC290
0x18003dafb  mov     edx, 7F0h
0x18003db00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db07  mov     rax, [rax+8]
0x18003db0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db10  test    eax, eax
0x18003db12  jnz     short loc_18003DB24
0x18003db14  lea     rcx, stru_1801F8A30
0x18003db1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db22  jmp     short loc_18003DB2B
0x18003db24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003db2b  cmp     [rcx+8], r12b
0x18003db2f  jz      short loc_18003DB52
0x18003db31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003db36  cmp     [rax+7CCh], esi
0x18003db3c  jz      short loc_18003DB52
0x18003db3e  mov     r9d, esi; int
0x18003db41  mov     r8d, 59h ; 'Y'; int
0x18003db47  mov     rdx, rbx; char *
0x18003db4a  mov     rcx, rax; this
0x18003db4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003db52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003db59  jb      loc_18003DA12
0x18003db5f  mov     edx, 10h
0x18003db64  jmp     loc_18003D9F8
0x18003db69  xor     r9d, r9d
0x18003db6c  lea     r8, [rbp+var_28]
0x18003db70  lea     rdx, MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID
0x18003db77  mov     rcx, r15
0x18003db7a  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x18003db7f  mov     esi, eax
0x18003db81  test    eax, eax
0x18003db83  jns     loc_18003DC3C
0x18003db89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db90  test    rcx, rcx
0x18003db93  jnz     short loc_18003DBD3
0x18003db95  mov     rax, cs:stru_1801FC290.__vftable
0x18003db9c  lea     rcx, stru_1801FC290
0x18003dba3  mov     edx, 7F0h
0x18003dba8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dbaf  mov     rax, [rax+8]
0x18003dbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbb8  test    eax, eax
0x18003dbba  jnz     short loc_18003DBCC
0x18003dbbc  lea     rcx, stru_1801F8A30
0x18003dbc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dbca  jmp     short loc_18003DBD3
0x18003dbcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003dbd3  cmp     [rcx+8], r12b
0x18003dbd7  jz      short loc_18003DBFA
0x18003dbd9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003dbde  cmp     [rax+7CCh], esi
0x18003dbe4  jz      short loc_18003DBFA
0x18003dbe6  mov     r9d, esi; int
0x18003dbe9  mov     r8d, 5Ch ; '\'; int
0x18003dbef  mov     rdx, rbx; char *
0x18003dbf2  mov     rcx, rax; this
0x18003dbf5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003dbfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dc01  jb      short loc_18003DC22
0x18003dc03  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc0a  mov     edx, 11h
0x18003dc0f  mov     r9, r15
0x18003dc12  mov     [rsp+58h+var_38], esi
0x18003dc16  mov     r8, rdi
0x18003dc19  mov     rcx, [rcx+10h]
0x18003dc1d  call    WPP_SF_qD
0x18003dc22  lea     rcx, [rbp+arg_18]
0x18003dc26  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x18003dc2b  xor     ecx, ecx; pv
0x18003dc2d  call    cs:__imp_CoTaskMemFree
0x18003dc33  mov     rcx, [rbp+var_28]
0x18003dc37  jmp     loc_18003DA25
0x18003dc3c  xor     r9d, r9d
0x18003dc3f  lea     r8, [rbp+pv]
0x18003dc43  lea     rdx, MF_MEDIA_EXTENSION_ABSOLUTE_DLLPATH
0x18003dc4a  mov     rcx, r15
0x18003dc4d  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x18003dc52  mov     esi, eax
0x18003dc54  test    eax, eax
0x18003dc56  jns     loc_18003DD07
0x18003dc5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc63  test    rcx, rcx
0x18003dc66  jnz     short loc_18003DCA6
0x18003dc68  mov     rax, cs:stru_1801FC290.__vftable
0x18003dc6f  lea     rcx, stru_1801FC290
0x18003dc76  mov     edx, 7F0h
0x18003dc7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc82  mov     rax, [rax+8]
0x18003dc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc8b  test    eax, eax
0x18003dc8d  jnz     short loc_18003DC9F
0x18003dc8f  lea     rcx, stru_1801F8A30
0x18003dc96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc9d  jmp     short loc_18003DCA6
0x18003dc9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003dca6  cmp     [rcx+8], r12b
0x18003dcaa  jz      short loc_18003DCCD
0x18003dcac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003dcb1  cmp     [rax+7CCh], esi
0x18003dcb7  jz      short loc_18003DCCD
0x18003dcb9  mov     r9d, esi; int
0x18003dcbc  mov     r8d, 5Dh ; ']'; int
0x18003dcc2  mov     rdx, rbx; char *
0x18003dcc5  mov     rcx, rax; this
0x18003dcc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003dccd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dcd4  jb      short loc_18003DCF5
0x18003dcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dcdd  mov     edx, 12h
0x18003dce2  mov     r9, r15
0x18003dce5  mov     [rsp+58h+var_38], esi
0x18003dce9  mov     r8, rdi
0x18003dcec  mov     rcx, [rcx+10h]
0x18003dcf0  call    WPP_SF_qD
0x18003dcf5  lea     rcx, [rbp+arg_18]
0x18003dcf9  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x18003dcfe  mov     rcx, [rbp+pv]
0x18003dd02  jmp     loc_18003DC2D
0x18003dd07  call    IsMountMediaCodecAppServicePackagePresent
0x18003dd0c  mov     rdi, [rbp+pv]
0x18003dd10  test    al, al
0x18003dd12  jz      loc_18003DEC7
0x18003dd18  xor     r9d, r9d
0x18003dd1b  mov     qword ptr [rbp+PerformanceCount], r12
0x18003dd1f  lea     r8, [rbp+PerformanceCount]
0x18003dd23  mov     rcx, r15
0x18003dd26  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME
0x18003dd2d  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x18003dd32  mov     esi, eax
0x18003dd34  test    eax, eax
0x18003dd36  jns     loc_18003DDF4
0x18003dd3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd43  test    rcx, rcx
0x18003dd46  jnz     short loc_18003DD86
0x18003dd48  mov     rax, cs:stru_1801FC290.__vftable
0x18003dd4f  lea     rcx, stru_1801FC290
0x18003dd56  mov     edx, 7F0h
0x18003dd5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd62  mov     rax, [rax+8]
0x18003dd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd6b  test    eax, eax
0x18003dd6d  jnz     short loc_18003DD7F
0x18003dd6f  lea     rcx, stru_1801F8A30
0x18003dd76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd7d  jmp     short loc_18003DD86
0x18003dd7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003dd86  cmp     [rcx+8], r12b
0x18003dd8a  jz      short loc_18003DDAD
0x18003dd8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003dd91  cmp     [rax+7CCh], esi
0x18003dd97  jz      short loc_18003DDAD
0x18003dd99  mov     r9d, esi; int
0x18003dd9c  mov     r8d, 62h ; 'b'; int
0x18003dda2  mov     rdx, rbx; char *
0x18003dda5  mov     rcx, rax; this
0x18003dda8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ddad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ddb4  jb      short loc_18003DDD9
  ... truncated ...
```
