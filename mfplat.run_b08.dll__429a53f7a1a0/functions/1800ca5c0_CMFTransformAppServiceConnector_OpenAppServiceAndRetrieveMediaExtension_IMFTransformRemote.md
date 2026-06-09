# CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension(IMFTransformRemote * *)

- ea: `0x1800ca5c0`
- end: `0x1800cb5b5`
- name: `?OpenAppServiceAndRetrieveMediaExtension@CMFTransformAppServiceConnector@@QEAAJPEAPEAUIMFTransformRemote@@@Z`
- size: `4085`
- prototype: `__int64 __fastcall(CMFTransformAppServiceConnector *__hidden this, struct IMFTransformRemote **)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b2bf8`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800a0074`
- `0x1800ca5c0`
- `0x180113cdc`
- `0x1801200d0`
- `0x180121581`
- `0x1801250c8`
- `0x180125108`
- `0x18014c084`
- `0x18015921c`
- `0x180159574`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca5f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca5f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cb586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cb586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb110`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb521`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb521`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800cb058`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800cb058`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800cb1f7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800cb1f7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800cb101`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800cb101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb530`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800cb20f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800cb20f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800cb37d`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800cb37d`

## string_xrefs

- `0x1800ca600`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800ca91c`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800ca9cc`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800caa93`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cab4f`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cabf5`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cacdb`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cad88`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cae4d`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800caf40`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb020`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb0d2`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb18c`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb282`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb339`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb3f0`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cb4e1`: `CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension`
- `0x1800cac43`: `MediaExtensionResponseHresult`
- `0x1800caea8`: `MediaExtension`

## pseudocode

```c
__int64 __fastcall CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension(
        CMFTransformAppServiceConnector *this,
        struct IMFTransformRemote **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  int v5; // ebx
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, __int64 *); // rbx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING__ *, __int64 *); // rbx
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING__ *, __int64 *); // rbx
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  HGLOBAL v42; // rax
  void *v43; // rdi
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  void *v46; // rax
  signed int LastError; // eax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  CallStackScopeTrace v60; // [rsp+30h] [rbp-79h] BYREF
  LPSTREAM pStm; // [rsp+38h] [rbp-71h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-69h] BYREF
  __int64 v63; // [rsp+48h] [rbp-61h] BYREF
  int v64; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v65; // [rsp+54h] [rbp-55h] BYREF
  int v66; // [rsp+58h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-49h] BYREF
  __int64 v68; // [rsp+68h] [rbp-41h] BYREF
  __int64 v69; // [rsp+70h] [rbp-39h] BYREF
  __int64 v70; // [rsp+78h] [rbp-31h] BYREF
  __int64 v71; // [rsp+80h] [rbp-29h] BYREF
  void *Src; // [rsp+88h] [rbp-21h] BYREF
  __int64 v73; // [rsp+90h] [rbp-19h] BYREF
  LPSTREAM v74; // [rsp+98h] [rbp-11h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v75; // [rsp+A0h] [rbp-9h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v71 = 0;
  v73 = 0;
  v70 = 0;
  v66 = 0;
  v69 = 0;
  v68 = 0;
  v63 = 0;
  Src = 0;
  ppv = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    &v60,
    "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
    389);
  v75.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v75,
    L"Windows.Foundation.Collections.PropertySet",
    0x2Bu,
    0x2Au);
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
         v75.hstr_,
         &v73);
  if ( v5 < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    v75.hstr_ = 0;
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
      if ( ThreadRelativeContext->m_result != v5 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
          389,
          v5);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v8 = 53;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
      goto LABEL_208;
    }
    goto LABEL_208;
  }
  v5 = CMFAppServiceConnectorBase::OpenConnection(this, 0);
  if ( v5 >= 0 )
  {
    v11 = *((_QWORD *)this + 8);
    v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    v5 = v12(v11, v73, &v71);
    if ( v5 < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v13->m_fEnabled )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( v14->m_result != v5 )
          CallStackContext::TraceFailure(
            v14,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            393,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 55;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this);
    v5 = BlockOnCompletionAndGetResults<Windows::ApplicationModel::AppService::AppServiceResponse *,Windows::ApplicationModel::AppService::IAppServiceResponse>(
           v71,
           &v70);
    if ( v5 < 0 )
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v15 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v15->m_fEnabled )
      {
        v16 = CallStackTracing::GetThreadRelativeContext(v15);
        if ( v16->m_result != v5 )
          CallStackContext::TraceFailure(
            v16,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            396,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 57;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v70 + 56LL))(v70, &v66);
    if ( v5 < 0 )
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
        if ( v18->m_result != v5 )
          CallStackContext::TraceFailure(
            v18,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            397,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 58;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    if ( v66 )
    {
      if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v66);
      v19 = CallStackTracing::s_wpInstance;
      v5 = -1072843855;
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
        if ( v20->m_result != -1072843855 )
          CallStackContext::TraceFailure(
            v20,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            402,
            -1072843855);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 60;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    v21 = v70;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    v5 = v22(v21, &v69);
    if ( v5 < 0 )
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
        if ( v24->m_result != v5 )
          CallStackContext::TraceFailure(
            v24,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            405,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 61;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    v5 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v69,
           &v68);
    if ( v5 < 0 )
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
        if ( v26->m_result != v5 )
          CallStackContext::TraceFailure(
            v26,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            406,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 62;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    v27 = v68;
    v64 = 0;
    v28 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, __int64 *))(*(_QWORD *)v68 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v75.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v75, L"MediaExtensionResponseHresult", 0x1Eu, 0x1Du);
    v5 = v28(v27, v75.hstr_, &v63);
    if ( v5 < 0 )
    {
      v29 = CallStackTracing::s_wpInstance;
      v75.hstr_ = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v29->m_fEnabled )
      {
        v30 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( v30->m_result != v5 )
          CallStackContext::TraceFailure(
            v30,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            409,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 63;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v63 + 88LL))(v63, &v64);
    if ( v5 < 0 )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v31 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v31->m_fEnabled )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(v31);
        if ( v32->m_result != v5 )
          CallStackContext::TraceFailure(
            v32,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            410,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 64;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v64);
    v5 = v64;
    if ( v64 < 0 )
    {
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v33 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v33->m_fEnabled )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(v33);
        if ( v34->m_result != v5 )
          CallStackContext::TraceFailure(
            v34,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            413,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 66;
        goto LABEL_11;
      }
      goto LABEL_208;
    }
    ppstm = 0;
    pStm = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v35 = v68;
    v36 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, __int64 *))(*(_QWORD *)v68 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v75.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v75, L"MediaExtension", 0xFu, 0xEu);
    v5 = v36(v35, v75.hstr_, &v63);
    if ( v5 < 0 )
    {
      v37 = CallStackTracing::s_wpInstance;
      v75.hstr_ = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v37 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v37->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(v37);
        if ( v38->m_result != v5 )
          CallStackContext::TraceFailure(
            v38,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            420,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_129;
      v39 = 67;
LABEL_128:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
LABEL_129:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pStm);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
      goto LABEL_208;
    }
    v65 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *, void **))(*(_QWORD *)v63 + 240LL))(v63, &v65, &Src);
    if ( v5 < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v40->m_fEnabled )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( v41->m_result != v5 )
          CallStackContext::TraceFailure(
            v41,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            423,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_129;
      v39 = 68;
      goto LABEL_128;
    }
    v42 = GlobalAlloc(2u, 4LL * v65);
    v43 = v42;
    if ( !v42 )
    {
      v44 = CallStackTracing::s_wpInstance;
      v5 = -2147024882;
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
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            426,
            -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_129;
      v39 = 69;
      goto LABEL_128;
    }
    v46 = GlobalLock(v42);
    if ( v46 )
    {
      memcpy_0(v46, Src, 4LL * v65);
      GlobalUnlock(v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
      v5 = CreateStreamOnHGlobal(v43, 0, &ppstm);
      if ( v5 >= 0 )
      {
        v74 = ppstm;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pStm);
        v5 = Microsoft::WRL::Details::MakeAndInitialize<CStreamWrapper,IStream,IStream *>(&pStm, &v74);
        if ( v5 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          v5 = CoUnmarshalInterface(pStm, &GUID_07915118_45df_442b_8a3f_f7826a6370ab, &ppv);
          if ( v5 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pStm);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
            if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
              WPP_SF_qq(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                74,
                &WPP_29e89521b84936885e6d012356985b16_Traceguids,
                this,
                ppv);
            v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IMFTransformRemote **))ppv)(
                   ppv,
                   &GUID_212ff881_ffc0_48db_b083_057a109386d8,
                   a2);
            if ( v5 < 0 )
            {
              v57 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v57 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v57 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v57->m_fEnabled )
              {
                v58 = CallStackTracing::GetThreadRelativeContext(v57);
                if ( v58->m_result != v5 )
                  CallStackContext::TraceFailure(
                    v58,
                    "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
                    444,
                    v5);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  75,
                  &WPP_29e89521b84936885e6d012356985b16_Traceguids,
                  this,
                  v5);
            }
            goto LABEL_207;
          }
          v55 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v55 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v55 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v55->m_fEnabled )
          {
            v56 = CallStackTracing::GetThreadRelativeContext(v55);
            if ( v56->m_result != v5 )
              CallStackContext::TraceFailure(
                v56,
                "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
                438,
                v5);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
LABEL_164:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pStm);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
LABEL_207:
            GlobalFree(v43);
            goto LABEL_208;
          }
          v50 = 73;
        }
        else
        {
          v53 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v53 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v53->m_fEnabled )
          {
            v54 = CallStackTracing::GetThreadRelativeContext(v53);
            if ( v54->m_result != v5 )
              CallStackContext::TraceFailure(
                v54,
                "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
                437,
                v5);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_164;
          v50 = 72;
        }
      }
      else
      {
        v51 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v51 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v51->m_fEnabled )
        {
          v52 = CallStackTracing::GetThreadRelativeContext(v51);
          if ( v52->m_result != v5 )
            CallStackContext::TraceFailure(
              v52,
              "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
              434,
              v5);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_164;
        v50 = 71;
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v48 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v48 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v48->m_fEnabled )
      {
        v49 = CallStackTracing::GetThreadRelativeContext(v48);
        if ( v5 < 0 && v49->m_result != v5 )
          CallStackContext::TraceFailure(
            v49,
            "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
            429,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_164;
      v50 = 70;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v50, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
    goto LABEL_164;
  }
  v9 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v9 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v9 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v9->m_fEnabled )
  {
    v10 = CallStackTracing::GetThreadRelativeContext(v9);
    if ( v10->m_result != v5 )
      CallStackContext::TraceFailure(
        v10,
        "CMFTransformAppServiceConnector::OpenAppServiceAndRetrieveMediaExtension",
        391,
        v5);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v8 = 54;
    goto LABEL_11;
  }
LABEL_208:
  if ( Src )
    CoTaskMemFree(Src);
  CallStackScopeTrace::~CallStackScopeTrace(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  if ( v2 )
    LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ca5c0  mov     [rsp-8+arg_10], rbx
0x1800ca5c5  push    rbp
0x1800ca5c6  push    rsi
0x1800ca5c7  push    rdi
0x1800ca5c8  push    r12
0x1800ca5ca  push    r13
0x1800ca5cc  push    r14
0x1800ca5ce  push    r15
0x1800ca5d0  lea     rbp, [rsp-27h]
0x1800ca5d5  sub     rsp, 0D0h
0x1800ca5dc  mov     rax, cs:__security_cookie
0x1800ca5e3  xor     rax, rsp
0x1800ca5e6  mov     [rbp+57h+var_40], rax
0x1800ca5ea  lea     r12, [rcx+18h]
0x1800ca5ee  mov     r14, rcx
0x1800ca5f1  mov     rcx, r12; lpCriticalSection
0x1800ca5f4  mov     r15, rdx
0x1800ca5f7  call    cs:__imp_EnterCriticalSection
0x1800ca5fd  xor     r13d, r13d
0x1800ca600  lea     rsi, aCmftransformap; "CMFTransformAppServiceConnector::OpenAp"...
0x1800ca607  mov     edi, 185h
0x1800ca60c  mov     [rbp+57h+var_80], r13
0x1800ca610  mov     r8d, edi; int
0x1800ca613  mov     [rbp+57h+var_70], r13
0x1800ca617  mov     rdx, rsi; char *
0x1800ca61a  mov     [rbp+57h+var_88], r13
0x1800ca61e  lea     rcx, [rbp+57h+var_D0]; this
0x1800ca622  mov     [rbp+57h+var_A8], r13d
0x1800ca626  mov     [rbp+57h+var_90], r13
0x1800ca62a  mov     [rbp+57h+var_98], r13
0x1800ca62e  mov     [rbp+57h+var_B8], r13
0x1800ca632  mov     [rbp+57h+Src], r13
0x1800ca636  mov     [rbp+57h+ppv], r13
0x1800ca63a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ca63f  lea     r9d, [r13+2Ah]; unsigned int
0x1800ca643  mov     [rbp+57h+var_60.hstr_], r13
0x1800ca647  lea     r8d, [r13+2Bh]; unsigned int
0x1800ca64b  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x1800ca652  lea     rcx, [rbp+57h+var_60]; this
0x1800ca656  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ca65b  mov     rcx, [rbp+57h+var_60.hstr_]
0x1800ca65f  lea     rdx, [rbp+57h+var_70]
0x1800ca663  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x1800ca668  mov     ebx, eax
0x1800ca66a  test    eax, eax
0x1800ca66c  jns     loc_1800CA71C
0x1800ca672  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca679  mov     [rbp+57h+var_60.hstr_], r13
0x1800ca67d  test    rcx, rcx
0x1800ca680  jnz     short loc_1800CA6C3
0x1800ca682  mov     rcx, cs:stru_1801FC290.__vftable
0x1800ca689  lea     r8, stru_1801FC290
0x1800ca690  mov     edx, 7F0h
0x1800ca695  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca69c  mov     rax, [rcx+8]
0x1800ca6a0  mov     rcx, r8
0x1800ca6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca6a8  test    eax, eax
0x1800ca6aa  jnz     short loc_1800CA6BC
0x1800ca6ac  lea     rcx, stru_1801F8A30
0x1800ca6b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca6ba  jmp     short loc_1800CA6C3
0x1800ca6bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ca6c3  cmp     [rcx+8], r13b
0x1800ca6c7  jz      short loc_1800CA6E7
0x1800ca6c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca6ce  cmp     [rax+7CCh], ebx
0x1800ca6d4  jz      short loc_1800CA6E7
0x1800ca6d6  mov     r9d, ebx; int
0x1800ca6d9  mov     r8d, edi; int
0x1800ca6dc  mov     rdx, rsi; char *
0x1800ca6df  mov     rcx, rax; this
0x1800ca6e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca6e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca6ee  jb      loc_1800CB527
0x1800ca6f4  mov     edx, 35h ; '5'
0x1800ca6f9  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1800ca700  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca707  mov     r9, r14
0x1800ca70a  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800ca70e  mov     rcx, [rcx+10h]
0x1800ca712  call    WPP_SF_qD
0x1800ca717  jmp     loc_1800CB527
0x1800ca71c  xor     edx, edx; bool
0x1800ca71e  mov     rcx, r14; this
0x1800ca721  call    ?OpenConnection@CMFAppServiceConnectorBase@@IEAAJ_N@Z; CMFAppServiceConnectorBase::OpenConnection(bool)
0x1800ca726  mov     ebx, eax
0x1800ca728  test    eax, eax
0x1800ca72a  jns     loc_1800CA7BB
0x1800ca730  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca737  test    rcx, rcx
0x1800ca73a  jnz     short loc_1800CA77D
0x1800ca73c  mov     rax, cs:stru_1801FC290.__vftable
0x1800ca743  lea     r8, stru_1801FC290
0x1800ca74a  mov     edx, 7F0h
0x1800ca74f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca756  mov     rcx, r8
0x1800ca759  mov     rax, [rax+8]
0x1800ca75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca762  test    eax, eax
0x1800ca764  jnz     short loc_1800CA776
0x1800ca766  lea     rcx, stru_1801F8A30
0x1800ca76d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca774  jmp     short loc_1800CA77D
0x1800ca776  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ca77d  cmp     [rcx+8], r13b
0x1800ca781  jz      short loc_1800CA7A4
0x1800ca783  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca788  cmp     [rax+7CCh], ebx
0x1800ca78e  jz      short loc_1800CA7A4
0x1800ca790  mov     r9d, ebx; int
0x1800ca793  mov     r8d, 187h; int
0x1800ca799  mov     rdx, rsi; char *
0x1800ca79c  mov     rcx, rax; this
0x1800ca79f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca7a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca7ab  jb      loc_1800CB527
0x1800ca7b1  mov     edx, 36h ; '6'
0x1800ca7b6  jmp     loc_1800CA6F9
0x1800ca7bb  mov     rdi, [r14+40h]
0x1800ca7bf  lea     rcx, [rbp+57h+var_80]
0x1800ca7c3  mov     rax, [rdi]
0x1800ca7c6  mov     rbx, [rax+58h]
0x1800ca7ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ca7cf  mov     rdx, [rbp+57h+var_70]
0x1800ca7d3  lea     r8, [rbp+57h+var_80]
0x1800ca7d7  mov     rcx, rdi
0x1800ca7da  mov     rax, rbx
0x1800ca7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca7e2  mov     ebx, eax
0x1800ca7e4  test    eax, eax
0x1800ca7e6  jns     loc_1800CA877
0x1800ca7ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca7f3  test    rcx, rcx
0x1800ca7f6  jnz     short loc_1800CA839
0x1800ca7f8  mov     rax, cs:stru_1801FC290.__vftable
0x1800ca7ff  lea     r8, stru_1801FC290
0x1800ca806  mov     edx, 7F0h
0x1800ca80b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca812  mov     rcx, r8
0x1800ca815  mov     rax, [rax+8]
0x1800ca819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca81e  test    eax, eax
0x1800ca820  jnz     short loc_1800CA832
0x1800ca822  lea     rcx, stru_1801F8A30
0x1800ca829  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca830  jmp     short loc_1800CA839
0x1800ca832  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ca839  cmp     [rcx+8], r13b
0x1800ca83d  jz      short loc_1800CA860
0x1800ca83f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca844  cmp     [rax+7CCh], ebx
0x1800ca84a  jz      short loc_1800CA860
0x1800ca84c  mov     r9d, ebx; int
0x1800ca84f  mov     r8d, 189h; int
0x1800ca855  mov     rdx, rsi; char *
0x1800ca858  mov     rcx, rax; this
0x1800ca85b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca860  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca867  jb      loc_1800CB527
0x1800ca86d  mov     edx, 37h ; '7'
0x1800ca872  jmp     loc_1800CA6F9
0x1800ca877  cmp     cs:byte_1801FD289, 10h
0x1800ca87e  lea     rsi, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1800ca885  jb      short loc_1800CA8A2
0x1800ca887  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca88e  mov     edx, 38h ; '8'
0x1800ca893  mov     r9, r14
0x1800ca896  mov     r8, rsi
0x1800ca899  mov     rcx, [rcx+38h]
0x1800ca89d  call    WPP_SF_q
0x1800ca8a2  mov     rcx, [rbp+57h+var_80]
0x1800ca8a6  lea     rdx, [rbp+57h+var_88]
0x1800ca8aa  call    ??$BlockOnCompletionAndGetResults@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@UIAppServiceResponse@234@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIAppServiceResponse@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::ApplicationModel::AppService::AppServiceResponse *,Windows::ApplicationModel::AppService::IAppServiceResponse>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse>>,tagCOWAIT_FLAGS,void *)
0x1800ca8af  mov     ebx, eax
0x1800ca8b1  test    eax, eax
0x1800ca8b3  jns     loc_1800CA94B
0x1800ca8b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca8c0  test    rcx, rcx
0x1800ca8c3  jnz     short loc_1800CA906
0x1800ca8c5  mov     rax, cs:stru_1801FC290.__vftable
0x1800ca8cc  lea     r8, stru_1801FC290
0x1800ca8d3  mov     edx, 7F0h
0x1800ca8d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca8df  mov     rcx, r8
0x1800ca8e2  mov     rax, [rax+8]
0x1800ca8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca8eb  test    eax, eax
0x1800ca8ed  jnz     short loc_1800CA8FF
0x1800ca8ef  lea     rcx, stru_1801F8A30
0x1800ca8f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca8fd  jmp     short loc_1800CA906
0x1800ca8ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ca906  cmp     [rcx+8], r13b
0x1800ca90a  jz      short loc_1800CA931
0x1800ca90c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca911  cmp     [rax+7CCh], ebx
0x1800ca917  jz      short loc_1800CA931
0x1800ca919  mov     r9d, ebx; int
0x1800ca91c  lea     rdx, aCmftransformap; "CMFTransformAppServiceConnector::OpenAp"...
0x1800ca923  mov     r8d, 18Ch; int
0x1800ca929  mov     rcx, rax; this
0x1800ca92c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca931  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca938  jb      loc_1800CB527
0x1800ca93e  mov     edx, 39h ; '9'
0x1800ca943  mov     r8, rsi
0x1800ca946  jmp     loc_1800CA700
0x1800ca94b  mov     rcx, [rbp+57h+var_88]
0x1800ca94f  lea     rdx, [rbp+57h+var_A8]
0x1800ca953  mov     rax, [rcx]
0x1800ca956  mov     rax, [rax+38h]
0x1800ca95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca95f  mov     ebx, eax
0x1800ca961  test    eax, eax
0x1800ca963  jns     loc_1800CA9F8
0x1800ca969  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca970  test    rcx, rcx
0x1800ca973  jnz     short loc_1800CA9B6
0x1800ca975  mov     rax, cs:stru_1801FC290.__vftable
0x1800ca97c  lea     r8, stru_1801FC290
0x1800ca983  mov     edx, 7F0h
0x1800ca988  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca98f  mov     rcx, r8
0x1800ca992  mov     rax, [rax+8]
0x1800ca996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca99b  test    eax, eax
0x1800ca99d  jnz     short loc_1800CA9AF
0x1800ca99f  lea     rcx, stru_1801F8A30
0x1800ca9a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca9ad  jmp     short loc_1800CA9B6
0x1800ca9af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ca9b6  cmp     [rcx+8], r13b
0x1800ca9ba  jz      short loc_1800CA9E1
0x1800ca9bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca9c1  cmp     [rax+7CCh], ebx
0x1800ca9c7  jz      short loc_1800CA9E1
0x1800ca9c9  mov     r9d, ebx; int
0x1800ca9cc  lea     rdx, aCmftransformap; "CMFTransformAppServiceConnector::OpenAp"...
0x1800ca9d3  mov     r8d, 18Dh; int
0x1800ca9d9  mov     rcx, rax; this
0x1800ca9dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca9e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca9e8  jb      loc_1800CB527
0x1800ca9ee  mov     edx, 3Ah ; ':'
0x1800ca9f3  jmp     loc_1800CA943
0x1800ca9f8  mov     eax, [rbp+57h+var_A8]
0x1800ca9fb  test    eax, eax
0x1800ca9fd  jz      loc_1800CAABF
0x1800caa03  cmp     cs:byte_1801FD289, 10h
0x1800caa0a  jb      short loc_1800CAA2B
0x1800caa0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caa13  mov     edx, 3Bh ; ';'
0x1800caa18  mov     r9, r14
0x1800caa1b  mov     dword ptr [rsp+100h+var_E0], eax
0x1800caa1f  mov     r8, rsi
0x1800caa22  mov     rcx, [rcx+38h]
0x1800caa26  call    WPP_SF_qD
0x1800caa2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa32  mov     ebx, 0C00DB3B1h
0x1800caa37  test    rcx, rcx
0x1800caa3a  jnz     short loc_1800CAA7D
0x1800caa3c  mov     rax, cs:stru_1801FC290.__vftable
0x1800caa43  lea     r8, stru_1801FC290
0x1800caa4a  mov     edx, 7F0h
0x1800caa4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa56  mov     rcx, r8
0x1800caa59  mov     rax, [rax+8]
0x1800caa5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caa62  test    eax, eax
0x1800caa64  jnz     short loc_1800CAA76
0x1800caa66  lea     rcx, stru_1801F8A30
0x1800caa6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa74  jmp     short loc_1800CAA7D
0x1800caa76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800caa7d  cmp     [rcx+8], r13b
0x1800caa81  jz      short loc_1800CAAA8
0x1800caa83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800caa88  cmp     [rax+7CCh], ebx
0x1800caa8e  jz      short loc_1800CAAA8
0x1800caa90  mov     r9d, ebx; int
0x1800caa93  lea     rdx, aCmftransformap; "CMFTransformAppServiceConnector::OpenAp"...
0x1800caa9a  mov     r8d, 192h; int
0x1800caaa0  mov     rcx, rax; this
0x1800caaa3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800caaa8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800caaaf  jb      loc_1800CB527
0x1800caab5  mov     edx, 3Ch ; '<'
0x1800caaba  jmp     loc_1800CA943
0x1800caabf  mov     rdi, [rbp+57h+var_88]
0x1800caac3  lea     rcx, [rbp+57h+var_90]
0x1800caac7  mov     rax, [rdi]
0x1800caaca  mov     rbx, [rax+30h]
0x1800caace  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800caad3  lea     rdx, [rbp+57h+var_90]
0x1800caad7  mov     rcx, rdi
0x1800caada  mov     rax, rbx
0x1800caadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caae2  mov     ebx, eax
0x1800caae4  test    eax, eax
  ... truncated ...
```
