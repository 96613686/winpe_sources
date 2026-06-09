# CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync(IMFByteStream *,IMFAsyncCallback *,IUnknown *)

- ea: `0x180106e70`
- end: `0x180107c5c`
- name: `?CreateMediaSourceAsync@CMFMediaSourceAppServiceConnector@@QEAAJPEAUIMFByteStream@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `3564`
- prototype: `__int64 __fastcall(CMFMediaSourceAppServiceConnector *__hidden this, struct IMFByteStream *, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180102d10`

## callees

- `0x180004870`
- `0x180011454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800ae2bc`
- `0x1800b0ba8`
- `0x1800e97cc`
- `0x180106e70`
- `0x180107c70`
- `0x180113cdc`
- `0x1801200d0`
- `0x180130e5c`
- `0x18015908c`
- `0x1801590dc`
- `0x180159264`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180106eaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180106eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180107c34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180107c34`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x180107b41`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x180107b41`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18010701d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18010701d`

## string_xrefs

- `0x180106eb2`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180106fb8`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107094`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107152`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x1801071f8`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x1801072b1`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107377`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107473`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107528`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x1801075df`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x18010769d`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107754`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107877`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107928`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107a06`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107ab2`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`
- `0x180107bb6`: `CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync`

## pseudocode

```c
__int64 __fastcall CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync(
        CMFMediaSourceAppServiceConnector *this,
        struct IMFByteStream *a2,
        IRtwqAsyncCallback *a3,
        struct IUnknown *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r13
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v10; // ebx
  _GUID v11; // xmm0
  int ActivationFactory; // ebx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  HSTRING__ *hstr; // rbx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, IUnknown **); // rbx
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  __int64 v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  void *Reserved1; // rdi
  __int64 (__fastcall *v32)(void *, __int64 *); // rbx
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  HRESULT (__stdcall *QueryInterface)(IMFByteStream *, const IID *const, void **); // rbx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  struct IMFByteStreamVtbl *lpVtbl; // rax
  HRESULT (__stdcall *v45)(IMFByteStream *, const IID *const, void **); // rbx
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  __int64 *v50; // rax
  __int64 v51; // rdi
  void *v52; // rcx
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  CallStackScopeTrace v60; // [rsp+30h] [rbp-59h] BYREF
  double v61; // [rsp+38h] [rbp-51h] BYREF
  __int64 v62; // [rsp+40h] [rbp-49h] BYREF
  __int64 v63; // [rsp+48h] [rbp-41h] BYREF
  IUnknown *appObject; // [rsp+50h] [rbp-39h] BYREF
  int v65; // [rsp+58h] [rbp-31h] BYREF
  __int64 v66; // [rsp+60h] [rbp-29h] BYREF
  __int64 v67; // [rsp+68h] [rbp-21h] BYREF
  __int64 v68; // [rsp+70h] [rbp-19h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v69; // [rsp+78h] [rbp-11h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v66 = 0;
  appObject = 0;
  v68 = 0;
  v67 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v60, "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync", 793);
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 27) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 296LL))(*((_QWORD *)this + 27));
    v11 = *(_GUID *)(*(__int64 (__fastcall **)(_QWORD, Microsoft::WRL::Wrappers::HStringReference *))(**((_QWORD **)this + 27) + 280LL))(
                      *((_QWORD *)this + 27),
                      &v69);
    ThreadRelativeContext->m_instanceId = v10;
    ThreadRelativeContext->m_sessionId = v11;
  }
  ActivationFactory = CMFAppServiceConnectorBase::OpenConnection(this, 1);
  if ( ActivationFactory < 0 )
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
      if ( v14->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v14,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          793,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_172;
    v15 = 141;
    goto LABEL_171;
  }
  v69.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v69,
    L"Windows.Media.Core.MediaStreamSource",
    0x25u,
    0x24u);
  hstr = v69.hstr_;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  ActivationFactory = RoGetActivationFactory(hstr, &GUID_00000035_0000_0000_c000_000000000046, &v66);
  if ( ActivationFactory < 0 )
  {
    v17 = CallStackTracing::s_wpInstance;
    v69.hstr_ = 0;
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
      if ( v18->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v18,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          798,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_172;
    v15 = 142;
    goto LABEL_171;
  }
  v19 = v66;
  v20 = *(__int64 (__fastcall **)(__int64, IUnknown **))(*(_QWORD *)v66 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&appObject);
  ActivationFactory = v20(v19, &appObject);
  if ( ActivationFactory < 0 )
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
      if ( v22->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v22,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          799,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_172;
    v15 = 143;
    goto LABEL_171;
  }
  ActivationFactory = Microsoft::WRL::ComPtr<Windows::Media::Core::IMediaStreamSource>::As<Windows::Media::Core::IMediaStreamSource3>(
                        &appObject,
                        &v68);
  if ( ActivationFactory < 0 )
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
      if ( v24->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v24,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          800,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_172;
    v15 = 144;
    goto LABEL_171;
  }
  v69.header_.Reserved.Reserved1 = (char *)this + 224;
  v25 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v69);
  ActivationFactory = Microsoft::WRL::AsWeak<Windows::Media::Core::IMediaStreamSource>(appObject, v25);
  if ( ActivationFactory < 0 )
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
      if ( v27->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v27,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          801,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_172;
    v15 = 145;
    goto LABEL_171;
  }
  v69.header_.Reserved.Reserved1 = 0;
  v62 = 0;
  v61 = 0.0;
  v63 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  ActivationFactory = MFMediaSourceFromMSS(
                        appObject,
                        &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
                        &v69.header_.Reserved.Reserved1);
  if ( ActivationFactory < 0 )
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
      if ( v29->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v29,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          811,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_65;
    v30 = 146;
LABEL_64:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      &WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      ActivationFactory);
LABEL_65:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    goto LABEL_172;
  }
  Reserved1 = v69.header_.Reserved.Reserved1;
  v32 = *(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v69.header_.Reserved.Reserved1 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  ActivationFactory = v32(Reserved1, &v62);
  if ( ActivationFactory < 0 )
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
      if ( v34->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v34,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          812,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_65;
    v30 = 147;
    goto LABEL_64;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  ActivationFactory = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CMFAppServiceConnectorBase,Microsoft::WRL::FtmBase>>(
                        this,
                        &GUID_00000000_0000_0000_c000_000000000046,
                        &v61);
  if ( ActivationFactory < 0 )
  {
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
      if ( v36->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v36,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          814,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_65;
    v30 = 148;
    goto LABEL_64;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, void *, double))(*(_QWORD *)v62 + 216LL))(
                        v62,
                        &MF_MEDIASTREAMSOURCE_APP_SERVICE_CONNECTION,
                        COERCE_DOUBLE(*(_QWORD *)&v61));
  if ( ActivationFactory < 0 )
  {
    v37 = CallStackTracing::s_wpInstance;
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
      if ( v38->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v38,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          815,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_65;
    v30 = 149;
    goto LABEL_64;
  }
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  ActivationFactory = ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))QueryInterface)(
                        a2,
                        &GUID_00000000_0000_0000_c000_000000000046,
                        &v63);
  if ( ActivationFactory < 0 )
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
      if ( v41->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v41,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          818,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_65;
    v30 = 150;
    goto LABEL_64;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v62 + 216LL))(
                        v62,
                        &MF_MEDIASTREAMSOURCE_APP_SERVICE_BYTESTREAM,
                        v63);
  if ( ActivationFactory < 0 )
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
      if ( v43->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v43,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          819,
          ActivationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_65;
    v30 = 151;
    goto LABEL_64;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  lpVtbl = a2->lpVtbl;
  v65 = 0;
  ((void (__fastcall *)(struct IMFByteStream *, int *))lpVtbl->GetCapabilities)(a2, &v65);
  if ( (v65 & 0x1000) != 0
    || (v45 = a2->lpVtbl->QueryInterface,
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67),
        ((int (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))v45)(
          a2,
          &GUID_6d66d782_1d4f_4db7_8c63_cb8c77f1ef5e,
          &v67) >= 0) )
  {
    ActivationFactory = ((__int64 (__fastcall *)(IUnknown *, __int64))appObject->__vftable[8].QueryInterface)(
                          appObject,
                          20000000);
    if ( ActivationFactory < 0 )
    {
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
        if ( v49->m_result != ActivationFactory )
          CallStackContext::TraceFailure(
            v49,
            "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
            831,
            ActivationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_172;
      v15 = 152;
      goto LABEL_171;
    }
  }
  else
  {
    ActivationFactory = ((__int64 (__fastcall *)(IUnknown *, _QWORD))appObject->__vftable[8].QueryInterface)(
                          appObject,
                          0);
    if ( ActivationFactory < 0 )
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
        if ( v47->m_result != ActivationFactory )
          CallStackContext::TraceFailure(
            v47,
            "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
            836,
            ActivationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_172;
      v15 = 153;
      goto LABEL_171;
    }
  }
  v61 = DOUBLE_8_0;
  v50 = (__int64 *)Microsoft::WRL::Details::Make<CReference<double>,double>(&v69, &v61);
  v51 = *v50;
  *v50 = 0;
  v52 = v69.header_.Reserved.Reserved1;
  if ( v69.header_.Reserved.Reserved1 )
  {
    v69.header_.Reserved.Reserved1 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v52 + 16LL))(v52);
  }
  if ( !v51 )
  {
    v53 = CallStackTracing::s_wpInstance;
    ActivationFactory = -2147024882;
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
      if ( v54->m_result != -2147024882 )
        CallStackContext::TraceFailure(
          v54,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          842,
          -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_172;
    v15 = 154;
    goto LABEL_171;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 48LL))(v68, v51);
  if ( ActivationFactory < 0 )
  {
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
      if ( v56->m_result != ActivationFactory )
        CallStackContext::TraceFailure(
          v56,
          "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
          843,
          ActivationFactory);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        155,
        &WPP_29e89521b84936885e6d012356985b16_Traceguids,
        this,
        ActivationFactory);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    goto LABEL_172;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  Microsoft::WRL::ComPtr<IMFByteStream>::operator=((char *)this + 200, a2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 208);
  ActivationFactory = RtwqCreateAsyncResult(appObject, a3, a4, (IRtwqAsyncResult **)this + 26);
  if ( ActivationFactory >= 0 )
    goto LABEL_173;
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
    if ( v58->m_result != ActivationFactory )
      CallStackContext::TraceFailure(
        v58,
        "CMFMediaSourceAppServiceConnector::CreateMediaSourceAsync",
        847,
        ActivationFactory);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v15 = 156;
LABEL_171:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      ActivationFactory);
  }
LABEL_172:
  CMFMediaSourceAppServiceConnector::CloseConnection(this);
LABEL_173:
  CallStackScopeTrace::~CallStackScopeTrace(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&appObject);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  if ( v4 )
    LeaveCriticalSection(v4);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180106e70  push    rbp
0x180106e72  push    rbx
0x180106e73  push    rsi
0x180106e74  push    rdi
0x180106e75  push    r12
0x180106e77  push    r13
0x180106e79  push    r14
0x180106e7b  push    r15
0x180106e7d  lea     rbp, [rsp-1Fh]
0x180106e82  sub     rsp, 0A8h
0x180106e89  mov     rax, cs:__security_cookie
0x180106e90  xor     rax, rsp
0x180106e93  mov     [rbp+57h+var_48], rax
0x180106e97  lea     r13, [rcx+18h]
0x180106e9b  mov     rsi, rcx
0x180106e9e  mov     rcx, r13; lpCriticalSection
0x180106ea1  mov     r12, r9
0x180106ea4  mov     r15, r8
0x180106ea7  mov     r14, rdx
0x180106eaa  call    cs:__imp_EnterCriticalSection
0x180106eb0  xor     edi, edi
0x180106eb2  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x180106eb9  mov     r8d, 319h; int
0x180106ebf  mov     [rbp+57h+var_80], rdi
0x180106ec3  lea     rcx, [rbp+57h+var_B0]; this
0x180106ec7  mov     [rbp+57h+appObject], rdi
0x180106ecb  mov     [rbp+57h+var_70], rdi
0x180106ecf  mov     [rbp+57h+var_78], rdi
0x180106ed3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180106ed8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180106edf  cmp     [rcx+8], dil
0x180106ee3  jz      short loc_180106F41
0x180106ee5  cmp     [rsi+0D8h], rdi
0x180106eec  jz      short loc_180106F41
0x180106eee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180106ef3  mov     rdx, [rsi+0D8h]
0x180106efa  mov     rdi, rax
0x180106efd  mov     rcx, [rdx]
0x180106f00  mov     rax, [rcx+128h]
0x180106f07  mov     rcx, rdx
0x180106f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f0f  mov     r8, [rsi+0D8h]
0x180106f16  lea     rdx, [rbp+57h+var_68]
0x180106f1a  mov     ebx, eax
0x180106f1c  mov     rcx, [r8]
0x180106f1f  mov     rax, [rcx+118h]
0x180106f26  mov     rcx, r8
0x180106f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f2e  movups  xmm0, xmmword ptr [rax]
0x180106f31  mov     [rdi+7E0h], ebx
0x180106f37  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180106f3f  xor     edi, edi
0x180106f41  mov     dl, 1; bool
0x180106f43  mov     rcx, rsi; this
0x180106f46  call    ?OpenConnection@CMFAppServiceConnectorBase@@IEAAJ_N@Z; CMFAppServiceConnectorBase::OpenConnection(bool)
0x180106f4b  mov     ebx, eax
0x180106f4d  test    eax, eax
0x180106f4f  jns     loc_180106FE4
0x180106f55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180106f5c  test    rcx, rcx
0x180106f5f  jnz     short loc_180106FA2
0x180106f61  mov     rcx, cs:stru_1801FC290.__vftable
0x180106f68  lea     r8, stru_1801FC290
0x180106f6f  mov     edx, 7F0h
0x180106f74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180106f7b  mov     rax, [rcx+8]
0x180106f7f  mov     rcx, r8
0x180106f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f87  test    eax, eax
0x180106f89  jnz     short loc_180106F9B
0x180106f8b  lea     rcx, stru_1801F8A30
0x180106f92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180106f99  jmp     short loc_180106FA2
0x180106f9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180106fa2  cmp     [rcx+8], dil
0x180106fa6  jz      short loc_180106FCD
0x180106fa8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180106fad  cmp     [rax+7CCh], ebx
0x180106fb3  jz      short loc_180106FCD
0x180106fb5  mov     r9d, ebx; int
0x180106fb8  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x180106fbf  mov     r8d, 319h; int
0x180106fc5  mov     rcx, rax; this
0x180106fc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180106fcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180106fd4  jb      loc_180107BF7
0x180106fda  mov     edx, 8Dh
0x180106fdf  jmp     loc_180107BD9
0x180106fe4  mov     r9d, 24h ; '$'; unsigned int
0x180106fea  mov     [rbp+57h+var_68.hstr_], rdi
0x180106fee  lea     rdx, ?RuntimeClass_Windows_Media_Core_MediaStreamSource@@3QBGB; "Windows.Media.Core.MediaStreamSource"
0x180106ff5  lea     rcx, [rbp+57h+var_68]; this
0x180106ff9  lea     r8d, [r9+1]; unsigned int
0x180106ffd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180107002  mov     rbx, [rbp+57h+var_68.hstr_]
0x180107006  lea     rcx, [rbp+57h+var_80]
0x18010700a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010700f  lea     r8, [rbp+57h+var_80]
0x180107013  mov     rcx, rbx
0x180107016  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18010701d  call    cs:__imp_RoGetActivationFactory
0x180107023  mov     ebx, eax
0x180107025  test    eax, eax
0x180107027  jns     loc_1801070C0
0x18010702d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107034  mov     [rbp+57h+var_68.hstr_], rdi
0x180107038  test    rcx, rcx
0x18010703b  jnz     short loc_18010707E
0x18010703d  mov     rax, cs:stru_1801FC290.__vftable
0x180107044  lea     r8, stru_1801FC290
0x18010704b  mov     edx, 7F0h
0x180107050  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180107057  mov     rcx, r8
0x18010705a  mov     rax, [rax+8]
0x18010705e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107063  test    eax, eax
0x180107065  jnz     short loc_180107077
0x180107067  lea     rcx, stru_1801F8A30
0x18010706e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107075  jmp     short loc_18010707E
0x180107077  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010707e  cmp     [rcx+8], dil
0x180107082  jz      short loc_1801070A9
0x180107084  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180107089  cmp     [rax+7CCh], ebx
0x18010708f  jz      short loc_1801070A9
0x180107091  mov     r9d, ebx; int
0x180107094  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x18010709b  mov     r8d, 31Eh; int
0x1801070a1  mov     rcx, rax; this
0x1801070a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801070a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801070b0  jb      loc_180107BF7
0x1801070b6  mov     edx, 8Eh
0x1801070bb  jmp     loc_180107BD9
0x1801070c0  mov     rdi, [rbp+57h+var_80]
0x1801070c4  lea     rcx, [rbp+57h+appObject]
0x1801070c8  mov     rax, [rdi]
0x1801070cb  mov     rbx, [rax+30h]
0x1801070cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801070d4  lea     rdx, [rbp+57h+appObject]
0x1801070d8  mov     rcx, rdi
0x1801070db  mov     rax, rbx
0x1801070de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801070e3  xor     edi, edi
0x1801070e5  mov     ebx, eax
0x1801070e7  test    eax, eax
0x1801070e9  jns     loc_18010717E
0x1801070ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801070f6  test    rcx, rcx
0x1801070f9  jnz     short loc_18010713C
0x1801070fb  mov     rax, cs:stru_1801FC290.__vftable
0x180107102  lea     r8, stru_1801FC290
0x180107109  mov     edx, 7F0h
0x18010710e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180107115  mov     rcx, r8
0x180107118  mov     rax, [rax+8]
0x18010711c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107121  test    eax, eax
0x180107123  jnz     short loc_180107135
0x180107125  lea     rcx, stru_1801F8A30
0x18010712c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107133  jmp     short loc_18010713C
0x180107135  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010713c  cmp     [rcx+8], dil
0x180107140  jz      short loc_180107167
0x180107142  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180107147  cmp     [rax+7CCh], ebx
0x18010714d  jz      short loc_180107167
0x18010714f  mov     r9d, ebx; int
0x180107152  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x180107159  mov     r8d, 31Fh; int
0x18010715f  mov     rcx, rax; this
0x180107162  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180107167  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010716e  jb      loc_180107BF7
0x180107174  mov     edx, 8Fh
0x180107179  jmp     loc_180107BD9
0x18010717e  lea     rdx, [rbp+57h+var_70]
0x180107182  lea     rcx, [rbp+57h+appObject]
0x180107186  call    ??$As@UIMediaStreamSource3@Core@Media@Windows@@@?$ComPtr@UIMediaStreamSource@Core@Media@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMediaStreamSource3@Core@Media@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Media::Core::IMediaStreamSource>::As<Windows::Media::Core::IMediaStreamSource3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::Core::IMediaStreamSource3>>)
0x18010718b  mov     ebx, eax
0x18010718d  test    eax, eax
0x18010718f  jns     loc_180107224
0x180107195  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010719c  test    rcx, rcx
0x18010719f  jnz     short loc_1801071E2
0x1801071a1  mov     rax, cs:stru_1801FC290.__vftable
0x1801071a8  lea     r8, stru_1801FC290
0x1801071af  mov     edx, 7F0h
0x1801071b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1801071bb  mov     rcx, r8
0x1801071be  mov     rax, [rax+8]
0x1801071c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801071c7  test    eax, eax
0x1801071c9  jnz     short loc_1801071DB
0x1801071cb  lea     rcx, stru_1801F8A30
0x1801071d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801071d9  jmp     short loc_1801071E2
0x1801071db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801071e2  cmp     [rcx+8], dil
0x1801071e6  jz      short loc_18010720D
0x1801071e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801071ed  cmp     [rax+7CCh], ebx
0x1801071f3  jz      short loc_18010720D
0x1801071f5  mov     r9d, ebx; int
0x1801071f8  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x1801071ff  mov     r8d, 320h; int
0x180107205  mov     rcx, rax; this
0x180107208  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010720d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180107214  jb      loc_180107BF7
0x18010721a  mov     edx, 90h
0x18010721f  jmp     loc_180107BD9
0x180107224  lea     rax, [rsi+0E0h]
0x18010722b  lea     rcx, [rbp+57h+var_68]
0x18010722f  mov     qword ptr [rbp+57h+var_68.header_.Reserved], rax
0x180107233  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180107238  mov     rcx, [rbp+57h+appObject]
0x18010723c  mov     rdx, rax
0x18010723f  call    ??$AsWeak@UIMediaStreamSource@Core@Media@Windows@@@WRL@Microsoft@@YAJPEAUIMediaStreamSource@Core@Media@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Media::Core::IMediaStreamSource>(Windows::Media::Core::IMediaStreamSource *,Microsoft::WRL::WeakRef *)
0x180107244  mov     ebx, eax
0x180107246  test    eax, eax
0x180107248  jns     loc_1801072DD
0x18010724e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180107255  test    rcx, rcx
0x180107258  jnz     short loc_18010729B
0x18010725a  mov     rax, cs:stru_1801FC290.__vftable
0x180107261  lea     r8, stru_1801FC290
0x180107268  mov     edx, 7F0h
0x18010726d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180107274  mov     rcx, r8
0x180107277  mov     rax, [rax+8]
0x18010727b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107280  test    eax, eax
0x180107282  jnz     short loc_180107294
0x180107284  lea     rcx, stru_1801F8A30
0x18010728b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107292  jmp     short loc_18010729B
0x180107294  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010729b  cmp     [rcx+8], dil
0x18010729f  jz      short loc_1801072C6
0x1801072a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801072a6  cmp     [rax+7CCh], ebx
0x1801072ac  jz      short loc_1801072C6
0x1801072ae  mov     r9d, ebx; int
0x1801072b1  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x1801072b8  mov     r8d, 321h; int
0x1801072be  mov     rcx, rax; this
0x1801072c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801072c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801072cd  jb      loc_180107BF7
0x1801072d3  mov     edx, 91h
0x1801072d8  jmp     loc_180107BD9
0x1801072dd  lea     rcx, [rbp+57h+var_68]
0x1801072e1  mov     qword ptr [rbp+57h+var_68.header_.Reserved], rdi
0x1801072e5  mov     [rbp+57h+var_A0], rdi
0x1801072e9  mov     [rbp+57h+var_A8], rdi
0x1801072ed  mov     [rbp+57h+var_98], rdi
0x1801072f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801072f6  mov     rcx, [rbp+57h+appObject]; struct IUnknown *
0x1801072fa  lea     r8, [rbp+57h+var_68]; void **
0x1801072fe  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8; struct _GUID *
0x180107305  call    ?MFMediaSourceFromMSS@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; MFMediaSourceFromMSS(IUnknown *,_GUID const &,void * *)
0x18010730a  mov     ebx, eax
0x18010730c  test    eax, eax
0x18010730e  jns     loc_1801073E1
0x180107314  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010731b  test    rcx, rcx
0x18010731e  jnz     short loc_180107361
0x180107320  mov     rax, cs:stru_1801FC290.__vftable
0x180107327  lea     r8, stru_1801FC290
0x18010732e  mov     edx, 7F0h
0x180107333  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010733a  mov     rcx, r8
0x18010733d  mov     rax, [rax+8]
0x180107341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107346  test    eax, eax
0x180107348  jnz     short loc_18010735A
0x18010734a  lea     rcx, stru_1801F8A30
0x180107351  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180107358  jmp     short loc_180107361
0x18010735a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180107361  cmp     [rcx+8], dil
0x180107365  jz      short loc_18010738C
0x180107367  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010736c  cmp     [rax+7CCh], ebx
0x180107372  jz      short loc_18010738C
0x180107374  mov     r9d, ebx; int
0x180107377  lea     rdx, aCmfmediasource_7; "CMFMediaSourceAppServiceConnector::Crea"...
0x18010737e  mov     r8d, 32Bh; int
0x180107384  mov     rcx, rax; this
0x180107387  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010738c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180107393  jb      short loc_1801073B8
0x180107395  mov     edx, 92h
0x18010739a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801073a1  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1801073a8  mov     r9, rsi
0x1801073ab  mov     [rsp+0E0h+var_C0], ebx
  ... truncated ...
```
