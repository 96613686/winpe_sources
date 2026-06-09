# CMFMediaSourceAppServiceConnector::OnResponseReceived(long,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *)

- ea: `0x180109b54`
- end: `0x18010a81d`
- name: `?OnResponseReceived@CMFMediaSourceAppServiceConnector@@AEAAXJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@Z`
- size: `3273`
- prototype: `void __fastcall(CMFMediaSourceAppServiceConnector *this, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180165590`

## callees

- `0x180004870`
- `0x180011454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800a0074`
- `0x180109b54`
- `0x18010a824`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180109b8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180109b8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010a7f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010a7f0`

## string_xrefs

- `0x180109b96`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x180109c35`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a030`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a0d6`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a1bc`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a269`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a332`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a3f9`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a4bb`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a56c`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a606`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a6b7`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a755`: `CMFMediaSourceAppServiceConnector::OnResponseReceived`
- `0x18010a124`: `MediaExtensionResponseHresult`

## pseudocode

```c
void __fastcall CMFMediaSourceAppServiceConnector::OnResponseReceived(
        CMFMediaSourceAppServiceConnector *this,
        int a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v9; // ebx
  _GUID *v10; // rax
  _GUID v11; // xmm0
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  struct CallStackContext *v14; // rax
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING__ *, __int64 *); // rbx
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, Microsoft::WRL::Wrappers::HStringReference *); // rbx
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  void *Reserved1; // rbx
  __int64 (__fastcall *v42)(void *, GUID *, __int64 *); // rdi
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  CallStackScopeTrace v53; // [rsp+30h] [rbp-49h] BYREF
  __int64 v54; // [rsp+38h] [rbp-41h] BYREF
  int v55; // [rsp+40h] [rbp-39h] BYREF
  int v56; // [rsp+44h] [rbp-35h] BYREF
  int v57; // [rsp+48h] [rbp-31h] BYREF
  int v58; // [rsp+4Ch] [rbp-2Dh] BYREF
  __int64 v59; // [rsp+50h] [rbp-29h] BYREF
  __int64 v60; // [rsp+58h] [rbp-21h] BYREF
  __int64 v61; // [rsp+60h] [rbp-19h] BYREF
  __int64 v62; // [rsp+68h] [rbp-11h] BYREF
  __int64 v63; // [rsp+70h] [rbp-9h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v64; // [rsp+78h] [rbp-1h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v59 = 0;
  v56 = 0;
  v61 = 0;
  v62 = 0;
  v60 = 0;
  v63 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v53, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 729);
  v7 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 27) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 296LL))(*((_QWORD *)this + 27));
    v10 = (_GUID *)(*(__int64 (__fastcall **)(_QWORD, Microsoft::WRL::Wrappers::HStringReference *))(**((_QWORD **)this + 27) + 280LL))(
                     *((_QWORD *)this + 27),
                     &v64);
    v7 = CallStackTracing::s_wpInstance;
    v11 = *v10;
    ThreadRelativeContext->m_instanceId = v9;
    ThreadRelativeContext->m_sessionId = v11;
  }
  if ( !*((_QWORD *)this + 26) )
  {
    a2 = -1072875795;
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
      v12 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v12->m_result != -1072875795 )
        CallStackContext::TraceFailure(v12, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 729, -1072875795);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v13 = 123;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, a2);
      goto LABEL_171;
    }
    goto LABEL_171;
  }
  if ( a2 >= 0 )
  {
    v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    a2 = v15(a3, &v59);
    if ( a2 < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v16->m_fEnabled )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( v17->m_result != a2 )
          CallStackContext::TraceFailure(v17, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 733, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 125;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    a2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v59 + 56LL))(v59, &v56);
    if ( a2 < 0 )
    {
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v18 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v18->m_fEnabled )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( v19->m_result != a2 )
          CallStackContext::TraceFailure(v19, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 734, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 126;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    if ( v56 )
    {
      if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 127, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v56);
      v20 = CallStackTracing::s_wpInstance;
      a2 = -1072843855;
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
        if ( v21->m_result != -1072843855 )
          CallStackContext::TraceFailure(v21, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 739, -1072843855);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 128;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    v22 = v59;
    v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    a2 = v23(v22, &v61);
    if ( a2 < 0 )
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
        if ( v25->m_result != a2 )
          CallStackContext::TraceFailure(v25, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 742, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 129;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    a2 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v61,
           &v62);
    if ( a2 < 0 )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v26->m_fEnabled )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( v27->m_result != a2 )
          CallStackContext::TraceFailure(v27, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 743, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 130;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    v28 = v62;
    v55 = 0;
    v29 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    v64.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v64, L"MediaExtensionResponseHresult", 0x1Eu, 0x1Du);
    a2 = v29(v28, v64.hstr_, &v60);
    if ( a2 < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
      v64.hstr_ = 0;
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
        if ( v31->m_result != a2 )
          CallStackContext::TraceFailure(v31, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 746, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 131;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    a2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 88LL))(v60, &v55);
    if ( a2 < 0 )
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
        if ( v33->m_result != a2 )
          CallStackContext::TraceFailure(v33, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 747, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 132;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 133, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v55);
    a2 = v55;
    if ( v55 < 0 )
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
        if ( v35->m_result != a2 )
          CallStackContext::TraceFailure(v35, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 750, a2);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 134;
        goto LABEL_14;
      }
      goto LABEL_171;
    }
    v36 = *((_QWORD *)this + 26);
    v64.header_.Reserved.Reserved1 = 0;
    v54 = 0;
    v37 = *(__int64 (__fastcall **)(__int64, Microsoft::WRL::Wrappers::HStringReference *))(*(_QWORD *)v36 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    a2 = v37(v36, &v64);
    if ( a2 >= 0 )
    {
      Reserved1 = v64.header_.Reserved.Reserved1;
      v42 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v64.header_.Reserved.Reserved1;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      a2 = v42(Reserved1, &GUID_a5dd08a8_6a2e_4746_894f_55a1afa4be9e, &v54);
      if ( a2 >= 0 )
      {
        v57 = 0;
        a2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v54 + 48LL))(v54, &v57);
        if ( a2 >= 0 )
        {
          a2 = v57;
          if ( v57 >= 0 )
          {
            v58 = 0;
            a2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v54 + 56LL))(v54, &v58);
            if ( a2 >= 0 )
            {
              if ( v58 )
                goto LABEL_170;
              v51 = CallStackTracing::s_wpInstance;
              a2 = -1072875842;
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
                if ( v52->m_result != -1072875842 )
                  CallStackContext::TraceFailure(
                    v52,
                    "CMFMediaSourceAppServiceConnector::OnResponseReceived",
                    769,
                    -1072875842);
              }
              if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                goto LABEL_170;
              v40 = 140;
            }
            else
            {
              v49 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v49 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v49->m_fEnabled )
              {
                v50 = CallStackTracing::GetThreadRelativeContext(v49);
                if ( v50->m_result != a2 )
                  CallStackContext::TraceFailure(v50, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 766, a2);
              }
              if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                goto LABEL_170;
              v40 = 139;
            }
          }
          else
          {
            v47 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v47 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v47 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v47->m_fEnabled )
            {
              v48 = CallStackTracing::GetThreadRelativeContext(v47);
              if ( v48->m_result != a2 )
                CallStackContext::TraceFailure(v48, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 762, a2);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_170;
            v40 = 138;
          }
        }
        else
        {
          v45 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v45 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v45 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v45->m_fEnabled )
          {
            v46 = CallStackTracing::GetThreadRelativeContext(v45);
            if ( v46->m_result != a2 )
              CallStackContext::TraceFailure(v46, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 761, a2);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_170;
          v40 = 137;
        }
      }
      else
      {
        v43 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v43 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v43->m_fEnabled )
        {
          v44 = CallStackTracing::GetThreadRelativeContext(v43);
          if ( v44->m_result != a2 )
            CallStackContext::TraceFailure(v44, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 757, a2);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_170;
        v40 = 136;
      }
    }
    else
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v38->m_fEnabled )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(v38);
        if ( v39->m_result != a2 )
          CallStackContext::TraceFailure(v39, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 756, a2);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_170;
      v40 = 135;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, a2);
LABEL_170:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    goto LABEL_171;
  }
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
    v14 = CallStackTracing::GetThreadRelativeContext(v7);
    if ( v14->m_result != a2 )
      CallStackContext::TraceFailure(v14, "CMFMediaSourceAppServiceConnector::OnResponseReceived", 731, a2);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v13 = 124;
    goto LABEL_14;
  }
LABEL_171:
  CMFMediaSourceAppServiceConnector::SignalMediaSourceCreation(this, a2);
  CallStackScopeTrace::~CallStackScopeTrace(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  if ( v3 )
    LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180109b54  mov     [rsp-8+arg_18], rbx
0x180109b59  push    rbp
0x180109b5a  push    rsi
0x180109b5b  push    rdi
0x180109b5c  push    r12
0x180109b5e  push    r13
0x180109b60  push    r14
0x180109b62  push    r15
0x180109b64  lea     rbp, [rsp-27h]
0x180109b69  sub     rsp, 0A0h
0x180109b70  mov     rax, cs:__security_cookie
0x180109b77  xor     rax, rsp
0x180109b7a  mov     [rbp+57h+var_38], rax
0x180109b7e  lea     r12, [rcx+18h]
0x180109b82  mov     r14, rcx
0x180109b85  mov     rcx, r12; lpCriticalSection
0x180109b88  mov     r15, r8
0x180109b8b  mov     esi, edx
0x180109b8d  call    cs:__imp_EnterCriticalSection
0x180109b93  xor     r13d, r13d
0x180109b96  lea     rdi, aCmfmediasource_3; "CMFMediaSourceAppServiceConnector::OnRe"...
0x180109b9d  mov     rdx, rdi; char *
0x180109ba0  mov     [rbp+57h+var_80], r13
0x180109ba4  mov     r8d, 2D9h; int
0x180109baa  mov     [rbp+57h+var_8C], r13d
0x180109bae  lea     rcx, [rbp+57h+var_A0]; this
0x180109bb2  mov     [rbp+57h+var_70], r13
0x180109bb6  mov     [rbp+57h+var_68], r13
0x180109bba  mov     [rbp+57h+var_78], r13
0x180109bbe  mov     [rbp+57h+var_60], r13
0x180109bc2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180109bc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180109bce  cmp     [rcx+8], r13b
0x180109bd2  jz      short loc_180109C3C
0x180109bd4  cmp     [r14+0D8h], r13
0x180109bdb  jz      short loc_180109C3C
0x180109bdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180109be2  mov     rdx, [r14+0D8h]
0x180109be9  mov     rdi, rax
0x180109bec  mov     rcx, [rdx]
0x180109bef  mov     rax, [rcx+128h]
0x180109bf6  mov     rcx, rdx
0x180109bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109bfe  mov     r8, [r14+0D8h]
0x180109c05  lea     rdx, [rbp+57h+var_58]
0x180109c09  mov     ebx, eax
0x180109c0b  mov     rcx, [r8]
0x180109c0e  mov     rax, [rcx+118h]
0x180109c15  mov     rcx, r8
0x180109c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180109c24  movups  xmm0, xmmword ptr [rax]
0x180109c27  mov     [rdi+7E0h], ebx
0x180109c2d  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180109c35  lea     rdi, aCmfmediasource_3; "CMFMediaSourceAppServiceConnector::OnRe"...
0x180109c3c  cmp     [r14+0D0h], r13
0x180109c43  jnz     loc_180109CF0
0x180109c49  mov     esi, 0C00D36EDh
0x180109c4e  test    rcx, rcx
0x180109c51  jnz     short loc_180109C94
0x180109c53  mov     rax, cs:stru_1801FC290.__vftable
0x180109c5a  lea     r8, stru_1801FC290
0x180109c61  mov     edx, 7F0h
0x180109c66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180109c6d  mov     rcx, r8
0x180109c70  mov     rax, [rax+8]
0x180109c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c79  test    eax, eax
0x180109c7b  jnz     short loc_180109C8D
0x180109c7d  lea     rcx, stru_1801F8A30
0x180109c84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180109c8b  jmp     short loc_180109C94
0x180109c8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180109c94  cmp     [rcx+8], r13b
0x180109c98  jz      short loc_180109CBB
0x180109c9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180109c9f  cmp     [rax+7CCh], esi
0x180109ca5  jz      short loc_180109CBB
0x180109ca7  mov     r9d, esi; int
0x180109caa  mov     r8d, 2D9h; int
0x180109cb0  mov     rdx, rdi; char *
0x180109cb3  mov     rcx, rax; this
0x180109cb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180109cbb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180109cc2  jb      loc_18010A7A8
0x180109cc8  mov     edx, 7Bh ; '{'
0x180109ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180109cd4  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180109cdb  mov     r9, r14
0x180109cde  mov     [rsp+0D0h+var_B0], esi
0x180109ce2  mov     rcx, [rcx+10h]
0x180109ce6  call    WPP_SF_qD
0x180109ceb  jmp     loc_18010A7A8
0x180109cf0  test    esi, esi
0x180109cf2  jns     loc_180109D7C
0x180109cf8  test    rcx, rcx
0x180109cfb  jnz     short loc_180109D3E
0x180109cfd  mov     rax, cs:stru_1801FC290.__vftable
0x180109d04  lea     r8, stru_1801FC290
0x180109d0b  mov     edx, 7F0h
0x180109d10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180109d17  mov     rcx, r8
0x180109d1a  mov     rax, [rax+8]
0x180109d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d23  test    eax, eax
0x180109d25  jnz     short loc_180109D37
0x180109d27  lea     rcx, stru_1801F8A30
0x180109d2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180109d35  jmp     short loc_180109D3E
0x180109d37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180109d3e  cmp     [rcx+8], r13b
0x180109d42  jz      short loc_180109D65
0x180109d44  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180109d49  cmp     [rax+7CCh], esi
0x180109d4f  jz      short loc_180109D65
0x180109d51  mov     r9d, esi; int
0x180109d54  mov     r8d, 2DBh; int
0x180109d5a  mov     rdx, rdi; char *
0x180109d5d  mov     rcx, rax; this
0x180109d60  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180109d65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180109d6c  jb      loc_18010A7A8
0x180109d72  mov     edx, 7Ch ; '|'
0x180109d77  jmp     loc_180109CCD
0x180109d7c  mov     rax, [r15]
0x180109d7f  lea     rcx, [rbp+57h+var_80]
0x180109d83  mov     rbx, [rax+40h]
0x180109d87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180109d8c  lea     rdx, [rbp+57h+var_80]
0x180109d90  mov     rcx, r15
0x180109d93  mov     rax, rbx
0x180109d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d9b  mov     esi, eax
0x180109d9d  test    eax, eax
0x180109d9f  jns     loc_180109E30
0x180109da5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180109dac  test    rcx, rcx
0x180109daf  jnz     short loc_180109DF2
0x180109db1  mov     rcx, cs:stru_1801FC290.__vftable
0x180109db8  lea     r8, stru_1801FC290
0x180109dbf  mov     edx, 7F0h
0x180109dc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180109dcb  mov     rax, [rcx+8]
0x180109dcf  mov     rcx, r8
0x180109dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109dd7  test    eax, eax
0x180109dd9  jnz     short loc_180109DEB
0x180109ddb  lea     rcx, stru_1801F8A30
0x180109de2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180109de9  jmp     short loc_180109DF2
0x180109deb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180109df2  cmp     [rcx+8], r13b
0x180109df6  jz      short loc_180109E19
0x180109df8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180109dfd  cmp     [rax+7CCh], esi
0x180109e03  jz      short loc_180109E19
0x180109e05  mov     r9d, esi; int
0x180109e08  mov     r8d, 2DDh; int
0x180109e0e  mov     rdx, rdi; char *
0x180109e11  mov     rcx, rax; this
0x180109e14  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180109e19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180109e20  jb      loc_18010A7A8
0x180109e26  mov     edx, 7Dh ; '}'
0x180109e2b  jmp     loc_180109CCD
0x180109e30  mov     rcx, [rbp+57h+var_80]
0x180109e34  lea     rdx, [rbp+57h+var_8C]
0x180109e38  mov     rax, [rcx]
0x180109e3b  mov     rax, [rax+38h]
0x180109e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109e44  mov     esi, eax
0x180109e46  test    eax, eax
0x180109e48  jns     loc_180109ED9
0x180109e4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180109e55  test    rcx, rcx
0x180109e58  jnz     short loc_180109E9B
0x180109e5a  mov     rax, cs:stru_1801FC290.__vftable
0x180109e61  lea     r8, stru_1801FC290
0x180109e68  mov     edx, 7F0h
0x180109e6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180109e74  mov     rcx, r8
0x180109e77  mov     rax, [rax+8]
0x180109e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109e80  test    eax, eax
0x180109e82  jnz     short loc_180109E94
0x180109e84  lea     rcx, stru_1801F8A30
0x180109e8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180109e92  jmp     short loc_180109E9B
0x180109e94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180109e9b  cmp     [rcx+8], r13b
0x180109e9f  jz      short loc_180109EC2
0x180109ea1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180109ea6  cmp     [rax+7CCh], esi
0x180109eac  jz      short loc_180109EC2
0x180109eae  mov     r9d, esi; int
0x180109eb1  mov     r8d, 2DEh; int
0x180109eb7  mov     rdx, rdi; char *
0x180109eba  mov     rcx, rax; this
0x180109ebd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180109ec2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180109ec9  jb      loc_18010A7A8
0x180109ecf  mov     edx, 7Eh ; '~'
0x180109ed4  jmp     loc_180109CCD
0x180109ed9  mov     eax, [rbp+57h+var_8C]
0x180109edc  test    eax, eax
0x180109ede  jz      loc_180109FA0
0x180109ee4  cmp     cs:byte_1801FD289, 10h
0x180109eeb  jb      short loc_180109F10
0x180109eed  mov     rcx, cs:WPP_GLOBAL_Control
0x180109ef4  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180109efb  mov     edx, 7Fh
0x180109f00  mov     [rsp+0D0h+var_B0], eax
0x180109f04  mov     r9, r14
0x180109f07  mov     rcx, [rcx+38h]
0x180109f0b  call    WPP_SF_qD
0x180109f10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180109f17  mov     esi, 0C00DB3B1h
0x180109f1c  test    rcx, rcx
0x180109f1f  jnz     short loc_180109F62
0x180109f21  mov     rax, cs:stru_1801FC290.__vftable
0x180109f28  lea     r8, stru_1801FC290
0x180109f2f  mov     edx, 7F0h
0x180109f34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180109f3b  mov     rcx, r8
0x180109f3e  mov     rax, [rax+8]
0x180109f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f47  test    eax, eax
0x180109f49  jnz     short loc_180109F5B
0x180109f4b  lea     rcx, stru_1801F8A30
0x180109f52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180109f59  jmp     short loc_180109F62
0x180109f5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180109f62  cmp     [rcx+8], r13b
0x180109f66  jz      short loc_180109F89
0x180109f68  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180109f6d  cmp     [rax+7CCh], esi
0x180109f73  jz      short loc_180109F89
0x180109f75  mov     r9d, esi; int
0x180109f78  mov     r8d, 2E3h; int
0x180109f7e  mov     rdx, rdi; char *
0x180109f81  mov     rcx, rax; this
0x180109f84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180109f89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180109f90  jb      loc_18010A7A8
0x180109f96  mov     edx, 80h
0x180109f9b  jmp     loc_180109CCD
0x180109fa0  mov     rdi, [rbp+57h+var_80]
0x180109fa4  lea     rcx, [rbp+57h+var_70]
0x180109fa8  mov     rax, [rdi]
0x180109fab  mov     rbx, [rax+30h]
0x180109faf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180109fb4  lea     rdx, [rbp+57h+var_70]
0x180109fb8  mov     rcx, rdi
0x180109fbb  mov     rax, rbx
0x180109fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109fc3  mov     esi, eax
0x180109fc5  test    eax, eax
0x180109fc7  jns     loc_18010A05C
0x180109fcd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180109fd4  test    rcx, rcx
0x180109fd7  jnz     short loc_18010A01A
0x180109fd9  mov     rax, cs:stru_1801FC290.__vftable
0x180109fe0  lea     r8, stru_1801FC290
0x180109fe7  mov     edx, 7F0h
0x180109fec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180109ff3  mov     rcx, r8
0x180109ff6  mov     rax, [rax+8]
0x180109ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109fff  test    eax, eax
0x18010a001  jnz     short loc_18010A013
0x18010a003  lea     rcx, stru_1801F8A30
0x18010a00a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010a011  jmp     short loc_18010A01A
0x18010a013  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010a01a  cmp     [rcx+8], r13b
0x18010a01e  jz      short loc_18010A045
0x18010a020  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010a025  cmp     [rax+7CCh], esi
0x18010a02b  jz      short loc_18010A045
0x18010a02d  mov     r9d, esi; int
0x18010a030  lea     rdx, aCmfmediasource_3; "CMFMediaSourceAppServiceConnector::OnRe"...
0x18010a037  mov     r8d, 2E6h; int
0x18010a03d  mov     rcx, rax; this
0x18010a040  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010a045  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010a04c  jb      loc_18010A7A8
0x18010a052  mov     edx, 81h
0x18010a057  jmp     loc_180109CCD
0x18010a05c  lea     rdx, [rbp+57h+var_68]
0x18010a060  lea     rcx, [rbp+57h+var_70]
0x18010a064  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18010a069  mov     esi, eax
0x18010a06b  test    eax, eax
0x18010a06d  jns     loc_18010A102
0x18010a073  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010a07a  test    rcx, rcx
0x18010a07d  jnz     short loc_18010A0C0
0x18010a07f  mov     rax, cs:stru_1801FC290.__vftable
0x18010a086  lea     r8, stru_1801FC290
0x18010a08d  mov     edx, 7F0h
  ... truncated ...
```
