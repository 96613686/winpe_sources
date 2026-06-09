# CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled(uchar *)

- ea: `0x1800b82b0`
- end: `0x1800b90bc`
- name: `?OpenAppServiceAndCheckEnabled@CMFEnabledCheckAppServiceConnector@@QEAAJPEAE@Z`
- size: `3596`
- prototype: `__int64 __fastcall(CMFEnabledCheckAppServiceConnector *this, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180117200`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180033dc8`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800a0074`
- `0x1800b82b0`
- `0x180113cdc`
- `0x1801200d0`
- `0x1801250c8`
- `0x18014bec8`
- `0x18014c084`
- `0x18015921c`
- `0x18015a920`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b82e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b82e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b908d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b908d`

## string_xrefs

- `0x1800b82f0`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b88af`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b898f`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8a73`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8b44`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8bf1`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8cbc`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8d78`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8e2a`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8f2a`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8fd7`: `CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled`
- `0x1800b8e92`: `MediaExtensionResponseHresult`
- `0x1800b87fb`: `Command`

## pseudocode

```c
__int64 __fastcall CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled(
        CMFEnabledCheckAppServiceConnector *this,
        bool *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  int v5; // ebx
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 *v13; // rcx
  _QWORD *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING__ *, __int64 *); // rbx
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, __int64 *); // rbx
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  _QWORD *v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(_QWORD *, HSTRING__ *, __int64, CallStackScopeTrace *); // rdi
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  _QWORD *v32; // rsi
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 (__fastcall *v35)(_QWORD *, HSTRING__ *, __int64, CallStackScopeTrace *); // rdi
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64, __int64 *); // rbx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64 *); // rbx
  CallStackTracing *v50; // rcx
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rcx
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, HSTRING__ *, __int64 *); // rbx
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  CallStackTracing *v59; // rcx
  struct CallStackContext *v60; // rax
  CallStackScopeTrace v62; // [rsp+30h] [rbp-59h] BYREF
  __int64 v63; // [rsp+38h] [rbp-51h] BYREF
  __int64 v64; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v65; // [rsp+48h] [rbp-41h] BYREF
  __int64 v66; // [rsp+50h] [rbp-39h] BYREF
  int v67; // [rsp+58h] [rbp-31h] BYREF
  __int64 v68; // [rsp+60h] [rbp-29h] BYREF
  __int64 v69; // [rsp+68h] [rbp-21h] BYREF
  __int64 v70; // [rsp+70h] [rbp-19h] BYREF
  __int64 v71; // [rsp+78h] [rbp-11h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v72; // [rsp+80h] [rbp-9h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *a2 = 0;
  v71 = 0;
  v70 = 0;
  v69 = 0;
  v68 = 0;
  v67 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    &v62,
    "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
    496);
  v72.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v72,
    L"Windows.Foundation.Collections.PropertySet",
    0x2Bu,
    0x2Au);
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
         v72.hstr_,
         &v70);
  if ( v5 < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    v72.hstr_ = 0;
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
          "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
          496,
          v5);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v8 = 80;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
      goto LABEL_175;
    }
    goto LABEL_175;
  }
  v5 = CMFAppServiceConnectorBase::OpenConnection(this, 0);
  if ( v5 >= 0 )
  {
    v65 = 0;
    v5 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v70,
           &v65);
    if ( v5 < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v11->m_fEnabled )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( v12->m_result != v5 )
          CallStackContext::TraceFailure(
            v12,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            503,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
      goto LABEL_32;
    }
    v63 = 0;
    v64 = 0;
    v66 = 0;
    v14 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&v72,
                      L"Windows.Foundation.PropertyValue");
    v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           *v14,
           &v63);
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
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            507,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_44;
      v17 = 83;
LABEL_43:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
LABEL_32:
      v13 = (__int64 *)&v65;
LABEL_174:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v13);
      goto LABEL_175;
    }
    v18 = v63;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, __int64 *))(*(_QWORD *)v63 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v72.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v72, L"IsEnabled", 0xAu, 9u);
    v5 = v19(v18, v72.hstr_, &v64);
    if ( v5 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      v72.hstr_ = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v20->m_fEnabled )
      {
        v21 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( v21->m_result != v5 )
          CallStackContext::TraceFailure(
            v21,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            508,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_44;
      v17 = 84;
      goto LABEL_43;
    }
    v22 = v63;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v5 = v23(v22, *((_QWORD *)this + 25), &v66);
    if ( v5 < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v24->m_fEnabled )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( v25->m_result != v5 )
          CallStackContext::TraceFailure(
            v25,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            509,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_44;
      v17 = 85;
      goto LABEL_43;
    }
    v26 = v65;
    v27 = v64;
    v62 = 0;
    v28 = *v65;
    v72.hstr_ = 0;
    v29 = *(__int64 (__fastcall **)(_QWORD *, HSTRING__ *, __int64, CallStackScopeTrace *))(v28 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v72, L"Command", 8u, 7u);
    v5 = v29(v26, v72.hstr_, v27, &v62);
    if ( v5 < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
      v72.hstr_ = 0;
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
        if ( v31->m_result != v5 )
          CallStackContext::TraceFailure(
            v31,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            512,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_44;
      v17 = 86;
      goto LABEL_43;
    }
    v32 = v65;
    v33 = v66;
    v34 = *v65;
    v72.hstr_ = 0;
    v35 = *(__int64 (__fastcall **)(_QWORD *, HSTRING__ *, __int64, CallStackScopeTrace *))(v34 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v72, L"ACID", 5u, 4u);
    v5 = v35(v32, v72.hstr_, v33, &v62);
    if ( v5 < 0 )
    {
      v36 = CallStackTracing::s_wpInstance;
      v72.hstr_ = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v36 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v36->m_fEnabled )
      {
        v37 = CallStackTracing::GetThreadRelativeContext(v36);
        if ( v37->m_result != v5 )
          CallStackContext::TraceFailure(
            v37,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            513,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_44;
      v17 = 87;
      goto LABEL_43;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v65);
    v38 = *((_QWORD *)this + 8);
    v39 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    v5 = v39(v38, v70, &v71);
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
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            516,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 88;
        goto LABEL_11;
      }
      goto LABEL_175;
    }
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 89, WPP_29e89521b84936885e6d012356985b16_Traceguids, this);
    v5 = BlockOnCompletionAndGetResults<Windows::ApplicationModel::AppService::AppServiceResponse *,Windows::ApplicationModel::AppService::IAppServiceResponse>(
           v71,
           &v68);
    if ( v5 < 0 )
    {
      v42 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v42 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v42->m_fEnabled )
      {
        v43 = CallStackTracing::GetThreadRelativeContext(v42);
        if ( v43->m_result != v5 )
          CallStackContext::TraceFailure(
            v43,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            519,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 90;
        goto LABEL_11;
      }
      goto LABEL_175;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v68 + 56LL))(v68, &v67);
    if ( v5 < 0 )
    {
      v44 = CallStackTracing::s_wpInstance;
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
        if ( v45->m_result != v5 )
          CallStackContext::TraceFailure(
            v45,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            520,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 91;
        goto LABEL_11;
      }
      goto LABEL_175;
    }
    if ( v67 )
    {
      if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 92, WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v67);
      v46 = CallStackTracing::s_wpInstance;
      v5 = -1072843855;
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
        if ( v47->m_result != -1072843855 )
          CallStackContext::TraceFailure(
            v47,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            525,
            -1072843855);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 93;
        goto LABEL_11;
      }
      goto LABEL_175;
    }
    v48 = v68;
    v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    v5 = v49(v48, &v69);
    if ( v5 < 0 )
    {
      v50 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v50 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v50->m_fEnabled )
      {
        v51 = CallStackTracing::GetThreadRelativeContext(v50);
        if ( v51->m_result != v5 )
          CallStackContext::TraceFailure(
            v51,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            528,
            v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 94;
        goto LABEL_11;
      }
      goto LABEL_175;
    }
    v64 = 0;
    v63 = 0;
    LODWORD(v65) = 0;
    v5 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v69,
           &v64);
    if ( v5 >= 0 )
    {
      v55 = v64;
      v56 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, __int64 *))(*(_QWORD *)v64 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      v72.hstr_ = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v72, L"MediaExtensionResponseHresult", 0x1Eu, 0x1Du);
      v5 = v56(v55, v72.hstr_, &v63);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v63 + 88LL))(v63, &v65);
        if ( v5 >= 0 )
        {
          if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              98,
              WPP_29e89521b84936885e6d012356985b16_Traceguids,
              this,
              (_DWORD)v65);
          *a2 = (int)v65 >= 0;
          goto LABEL_173;
        }
        v59 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v59 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v59->m_fEnabled )
        {
          v60 = CallStackTracing::GetThreadRelativeContext(v59);
          if ( v60->m_result != v5 )
            CallStackContext::TraceFailure(
              v60,
              "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
              538,
              v5);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
LABEL_173:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
          v13 = &v64;
          goto LABEL_174;
        }
        v54 = 97;
      }
      else
      {
        v57 = CallStackTracing::s_wpInstance;
        v72.hstr_ = 0;
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
              "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
              537,
              v5);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_173;
        v54 = 96;
      }
    }
    else
    {
      v52 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v52 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v52->m_fEnabled )
      {
        v53 = CallStackTracing::GetThreadRelativeContext(v52);
        if ( v53->m_result != v5 )
          CallStackContext::TraceFailure(
            v53,
            "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled",
            536,
            v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_173;
      v54 = 95;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v54, WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v5);
    goto LABEL_173;
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
      CallStackContext::TraceFailure(v10, "CMFEnabledCheckAppServiceConnector::OpenAppServiceAndCheckEnabled", 498, v5);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v8 = 81;
    goto LABEL_11;
  }
LABEL_175:
  if ( *((_QWORD *)this + 8) )
    CMFAppServiceConnectorBase::CloseConnection(this);
  CallStackScopeTrace::~CallStackScopeTrace(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  if ( v2 )
    LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b82b0  mov     [rsp-8+arg_10], rbx
0x1800b82b5  push    rbp
0x1800b82b6  push    rsi
0x1800b82b7  push    rdi
0x1800b82b8  push    r12
0x1800b82ba  push    r13
0x1800b82bc  push    r14
0x1800b82be  push    r15
0x1800b82c0  lea     rbp, [rsp-27h]
0x1800b82c5  sub     rsp, 0B0h
0x1800b82cc  mov     rax, cs:__security_cookie
0x1800b82d3  xor     rax, rsp
0x1800b82d6  mov     [rbp+57h+var_40], rax
0x1800b82da  lea     r12, [rcx+18h]
0x1800b82de  mov     r14, rcx
0x1800b82e1  mov     rcx, r12; lpCriticalSection
0x1800b82e4  mov     r15, rdx
0x1800b82e7  call    cs:__imp_EnterCriticalSection
0x1800b82ed  xor     r13d, r13d
0x1800b82f0  lea     rsi, aCmfenabledchec; "CMFEnabledCheckAppServiceConnector::Ope"...
0x1800b82f7  mov     edi, 1F0h
0x1800b82fc  mov     [r15], r13b
0x1800b82ff  mov     r8d, edi; int
0x1800b8302  mov     [rbp+57h+var_68], r13
0x1800b8306  mov     rdx, rsi; char *
0x1800b8309  mov     [rbp+57h+var_70], r13
0x1800b830d  lea     rcx, [rbp+57h+var_B0]; this
0x1800b8311  mov     [rbp+57h+var_78], r13
0x1800b8315  mov     [rbp+57h+var_80], r13
0x1800b8319  mov     [rbp+57h+var_88], r13d
0x1800b831d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b8322  lea     r9d, [r13+2Ah]; unsigned int
0x1800b8326  mov     [rbp+57h+var_60.hstr_], r13
0x1800b832a  lea     r8d, [r13+2Bh]; unsigned int
0x1800b832e  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x1800b8335  lea     rcx, [rbp+57h+var_60]; this
0x1800b8339  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b833e  mov     rcx, [rbp+57h+var_60.hstr_]
0x1800b8342  lea     rdx, [rbp+57h+var_70]
0x1800b8346  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x1800b834b  mov     ebx, eax
0x1800b834d  test    eax, eax
0x1800b834f  jns     loc_1800B83FF
0x1800b8355  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b835c  mov     [rbp+57h+var_60.hstr_], r13
0x1800b8360  test    rcx, rcx
0x1800b8363  jnz     short loc_1800B83A6
0x1800b8365  mov     rcx, cs:stru_1801FC290.__vftable
0x1800b836c  lea     r8, stru_1801FC290
0x1800b8373  mov     edx, 7F0h
0x1800b8378  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b837f  mov     rax, [rcx+8]
0x1800b8383  mov     rcx, r8
0x1800b8386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b838b  test    eax, eax
0x1800b838d  jnz     short loc_1800B839F
0x1800b838f  lea     rcx, stru_1801F8A30
0x1800b8396  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b839d  jmp     short loc_1800B83A6
0x1800b839f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b83a6  cmp     [rcx+8], r13b
0x1800b83aa  jz      short loc_1800B83CA
0x1800b83ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b83b1  cmp     [rax+7CCh], ebx
0x1800b83b7  jz      short loc_1800B83CA
0x1800b83b9  mov     r9d, ebx; int
0x1800b83bc  mov     r8d, edi; int
0x1800b83bf  mov     rdx, rsi; char *
0x1800b83c2  mov     rcx, rax; this
0x1800b83c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b83ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b83d1  jb      loc_1800B904A
0x1800b83d7  mov     edx, 50h ; 'P'
0x1800b83dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b83e3  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1800b83ea  mov     r9, r14
0x1800b83ed  mov     [rsp+0E0h+var_C0], ebx
0x1800b83f1  mov     rcx, [rcx+10h]
0x1800b83f5  call    WPP_SF_qD
0x1800b83fa  jmp     loc_1800B904A
0x1800b83ff  xor     edx, edx; bool
0x1800b8401  mov     rcx, r14; this
0x1800b8404  call    ?OpenConnection@CMFAppServiceConnectorBase@@IEAAJ_N@Z; CMFAppServiceConnectorBase::OpenConnection(bool)
0x1800b8409  mov     ebx, eax
0x1800b840b  test    eax, eax
0x1800b840d  jns     loc_1800B849E
0x1800b8413  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b841a  test    rcx, rcx
0x1800b841d  jnz     short loc_1800B8460
0x1800b841f  mov     rax, cs:stru_1801FC290.__vftable
0x1800b8426  lea     r8, stru_1801FC290
0x1800b842d  mov     edx, 7F0h
0x1800b8432  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8439  mov     rcx, r8
0x1800b843c  mov     rax, [rax+8]
0x1800b8440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8445  test    eax, eax
0x1800b8447  jnz     short loc_1800B8459
0x1800b8449  lea     rcx, stru_1801F8A30
0x1800b8450  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8457  jmp     short loc_1800B8460
0x1800b8459  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b8460  cmp     [rcx+8], r13b
0x1800b8464  jz      short loc_1800B8487
0x1800b8466  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b846b  cmp     [rax+7CCh], ebx
0x1800b8471  jz      short loc_1800B8487
0x1800b8473  mov     r9d, ebx; int
0x1800b8476  mov     r8d, 1F2h; int
0x1800b847c  mov     rdx, rsi; char *
0x1800b847f  mov     rcx, rax; this
0x1800b8482  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b8487  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b848e  jb      loc_1800B904A
0x1800b8494  mov     edx, 51h ; 'Q'
0x1800b8499  jmp     loc_1800B83DC
0x1800b849e  lea     rdx, [rbp+57h+var_98]
0x1800b84a2  mov     [rbp+57h+var_98], r13
0x1800b84a6  lea     rcx, [rbp+57h+var_70]
0x1800b84aa  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800b84af  mov     ebx, eax
0x1800b84b1  test    eax, eax
0x1800b84b3  jns     loc_1800B8562
0x1800b84b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b84c0  test    rcx, rcx
0x1800b84c3  jnz     short loc_1800B8506
0x1800b84c5  mov     rax, cs:stru_1801FC290.__vftable
0x1800b84cc  lea     r8, stru_1801FC290
0x1800b84d3  mov     edx, 7F0h
0x1800b84d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b84df  mov     rcx, r8
0x1800b84e2  mov     rax, [rax+8]
0x1800b84e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b84eb  test    eax, eax
0x1800b84ed  jnz     short loc_1800B84FF
0x1800b84ef  lea     rcx, stru_1801F8A30
0x1800b84f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b84fd  jmp     short loc_1800B8506
0x1800b84ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b8506  cmp     [rcx+8], r13b
0x1800b850a  jz      short loc_1800B852D
0x1800b850c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b8511  cmp     [rax+7CCh], ebx
0x1800b8517  jz      short loc_1800B852D
0x1800b8519  mov     r9d, ebx; int
0x1800b851c  mov     r8d, 1F7h; int
0x1800b8522  mov     rdx, rsi; char *
0x1800b8525  mov     rcx, rax; this
0x1800b8528  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b852d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b8534  jb      short loc_1800B8559
0x1800b8536  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b853d  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1800b8544  mov     edx, 52h ; 'R'
0x1800b8549  mov     [rsp+0E0h+var_C0], ebx
0x1800b854d  mov     r9, r14
0x1800b8550  mov     rcx, [rcx+10h]
0x1800b8554  call    WPP_SF_qD
0x1800b8559  lea     rcx, [rbp+57h+var_98]
0x1800b855d  jmp     loc_1800B9045
0x1800b8562  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800b8569  mov     [rbp+57h+var_A8], r13
0x1800b856d  lea     rcx, [rbp+57h+var_60]; string
0x1800b8571  mov     [rbp+57h+var_A0], r13
0x1800b8575  mov     [rbp+57h+var_90], r13
0x1800b8579  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x1800b857e  lea     rdx, [rbp+57h+var_A8]
0x1800b8582  mov     rcx, [rax]
0x1800b8585  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1800b858a  mov     ebx, eax
0x1800b858c  test    eax, eax
0x1800b858e  jns     loc_1800B8654
0x1800b8594  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b859b  test    rcx, rcx
0x1800b859e  jnz     short loc_1800B85E1
0x1800b85a0  mov     rax, cs:stru_1801FC290.__vftable
0x1800b85a7  lea     r8, stru_1801FC290
0x1800b85ae  mov     edx, 7F0h
0x1800b85b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b85ba  mov     rcx, r8
0x1800b85bd  mov     rax, [rax+8]
0x1800b85c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b85c6  test    eax, eax
0x1800b85c8  jnz     short loc_1800B85DA
0x1800b85ca  lea     rcx, stru_1801F8A30
0x1800b85d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b85d8  jmp     short loc_1800B85E1
0x1800b85da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b85e1  cmp     [rcx+8], r13b
0x1800b85e5  jz      short loc_1800B8608
0x1800b85e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b85ec  cmp     [rax+7CCh], ebx
0x1800b85f2  jz      short loc_1800B8608
0x1800b85f4  mov     r9d, ebx; int
0x1800b85f7  mov     r8d, 1FBh; int
0x1800b85fd  mov     rdx, rsi; char *
0x1800b8600  mov     rcx, rax; this
0x1800b8603  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b8608  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b860f  jb      short loc_1800B8634
0x1800b8611  mov     edx, 53h ; 'S'
0x1800b8616  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b861d  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1800b8624  mov     r9, r14
0x1800b8627  mov     [rsp+0E0h+var_C0], ebx
0x1800b862b  mov     rcx, [rcx+10h]
0x1800b862f  call    WPP_SF_qD
0x1800b8634  lea     rcx, [rbp+57h+var_90]
0x1800b8638  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b863d  lea     rcx, [rbp+57h+var_A0]
0x1800b8641  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b8646  lea     rcx, [rbp+57h+var_A8]
0x1800b864a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b864f  jmp     loc_1800B8559
0x1800b8654  mov     rdi, [rbp+57h+var_A8]
0x1800b8658  lea     rcx, [rbp+57h+var_A0]
0x1800b865c  mov     rax, [rdi]
0x1800b865f  mov     rbx, [rax+90h]
0x1800b8666  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b866b  mov     r9d, 9; unsigned int
0x1800b8671  mov     [rbp+57h+var_60.hstr_], r13
0x1800b8675  lea     rdx, aIsenabled; "IsEnabled"
0x1800b867c  lea     rcx, [rbp+57h+var_60]; this
0x1800b8680  lea     r8d, [r9+1]; unsigned int
0x1800b8684  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b8689  mov     rdx, [rbp+57h+var_60.hstr_]
0x1800b868d  lea     r8, [rbp+57h+var_A0]
0x1800b8691  mov     rcx, rdi
0x1800b8694  mov     rax, rbx
0x1800b8697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b869c  mov     ebx, eax
0x1800b869e  test    eax, eax
0x1800b86a0  jns     loc_1800B8735
0x1800b86a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b86ad  mov     [rbp+57h+var_60.hstr_], r13
0x1800b86b1  test    rcx, rcx
0x1800b86b4  jnz     short loc_1800B86F7
0x1800b86b6  mov     rax, cs:stru_1801FC290.__vftable
0x1800b86bd  lea     r8, stru_1801FC290
0x1800b86c4  mov     edx, 7F0h
0x1800b86c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b86d0  mov     rcx, r8
0x1800b86d3  mov     rax, [rax+8]
0x1800b86d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b86dc  test    eax, eax
0x1800b86de  jnz     short loc_1800B86F0
0x1800b86e0  lea     rcx, stru_1801F8A30
0x1800b86e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b86ee  jmp     short loc_1800B86F7
0x1800b86f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b86f7  cmp     [rcx+8], r13b
0x1800b86fb  jz      short loc_1800B871E
0x1800b86fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b8702  cmp     [rax+7CCh], ebx
0x1800b8708  jz      short loc_1800B871E
0x1800b870a  mov     r9d, ebx; int
0x1800b870d  mov     r8d, 1FCh; int
0x1800b8713  mov     rdx, rsi; char *
0x1800b8716  mov     rcx, rax; this
0x1800b8719  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b871e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b8725  jb      loc_1800B8634
0x1800b872b  mov     edx, 54h ; 'T'
0x1800b8730  jmp     loc_1800B8616
0x1800b8735  mov     rdi, [rbp+57h+var_A8]
0x1800b8739  lea     rcx, [rbp+57h+var_90]
0x1800b873d  mov     rax, [rdi]
0x1800b8740  mov     rbx, [rax+90h]
0x1800b8747  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b874c  mov     rdx, [r14+0C8h]
0x1800b8753  lea     r8, [rbp+57h+var_90]
0x1800b8757  mov     rcx, rdi
0x1800b875a  mov     rax, rbx
0x1800b875d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8762  mov     ebx, eax
0x1800b8764  test    eax, eax
0x1800b8766  jns     loc_1800B87F7
0x1800b876c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8773  test    rcx, rcx
0x1800b8776  jnz     short loc_1800B87B9
0x1800b8778  mov     rax, cs:stru_1801FC290.__vftable
0x1800b877f  lea     r8, stru_1801FC290
0x1800b8786  mov     edx, 7F0h
0x1800b878b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8792  mov     rcx, r8
0x1800b8795  mov     rax, [rax+8]
0x1800b8799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b879e  test    eax, eax
0x1800b87a0  jnz     short loc_1800B87B2
0x1800b87a2  lea     rcx, stru_1801F8A30
0x1800b87a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b87b0  jmp     short loc_1800B87B9
0x1800b87b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b87b9  cmp     [rcx+8], r13b
0x1800b87bd  jz      short loc_1800B87E0
0x1800b87bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b87c4  cmp     [rax+7CCh], ebx
0x1800b87ca  jz      short loc_1800B87E0
0x1800b87cc  mov     r9d, ebx; int
0x1800b87cf  mov     r8d, 1FDh; int
  ... truncated ...
```
