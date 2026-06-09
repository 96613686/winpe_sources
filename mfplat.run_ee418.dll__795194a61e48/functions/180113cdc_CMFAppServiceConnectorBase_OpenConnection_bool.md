# CMFAppServiceConnectorBase::OpenConnection(bool)

- ea: `0x180113cdc`
- end: `0x180114e78`
- name: `?OpenConnection@CMFAppServiceConnectorBase@@IEAAJ_N@Z`
- size: `4508`
- prototype: `__int64 __fastcall(CMFAppServiceConnectorBase *__hidden this, bool)`
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b82b0`
- `0x1800ca5c0`
- `0x180106e70`

## callees

- `0x180004870`
- `0x180014488`
- `0x1800149b0`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x18004e368`
- `0x1800b0ba8`
- `0x180113cdc`
- `0x1801200d0`
- `0x1801211c0`
- `0x1801250c8`
- `0x1801590dc`
- `0x1801593c8`
- `0x180159d80`
- `0x180159f0c`
- `0x180159f60`
- `0x18015a298`
- `0x18015aa34`
- `0x1801abcb4`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180113fbc`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180113fbc`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x180113e1d`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x180113e1d`

## string_xrefs

- `0x180113d06`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180113da8`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180113f5f`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114268`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114334`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x1801143f6`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x1801144e6`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x1801145b4`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x1801146ba`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114782`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114844`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114926`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114a6e`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114b5a`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114c0c`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114ce2`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180114dab`: `CMFAppServiceConnectorBase::OpenConnection`
- `0x180113fa1`: `Windows.ApplicationModel.AppService.AppServiceConnection`

## pseudocode

```c
__int64 __fastcall CMFAppServiceConnectorBase::OpenConnection(CMFAppServiceConnectorBase *this, char a2)
{
  CallStackTracing *v4; // rcx
  HRESULT MediaExtensionCommunicationFactory; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdi
  _QWORD *v12; // rsi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD, __int64, char *); // rbx
  __int64 v14; // r9
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  __int64 (__fastcall ***v23)(_QWORD, GUID *, CMFAppServiceConnectorBase **); // rdi
  __int64 (__fastcall *v24)(_QWORD, GUID *, CMFAppServiceConnectorBase **); // rbx
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  __int64 v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rbx
  CMFAppServiceConnectorBase **v35; // rax
  __int64 v36; // rdi
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, _QWORD); // rbx
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  bool v45; // al
  __int64 (__fastcall ***v46)(_QWORD, GUID *, CMFAppServiceConnectorBase **); // rdi
  __int64 (__fastcall *v47)(_QWORD, GUID *, CMFAppServiceConnectorBase **); // rbx
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  __int64 (__fastcall *v50)(_QWORD, GUID *, CMFAppServiceConnectorBase **); // rbx
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  CMFAppServiceConnectorBase *v54; // rdi
  __int64 (__fastcall *v55)(CMFAppServiceConnectorBase *, GUID *, _QWORD); // rbx
  CallStackTracing *v56; // rcx
  struct CallStackContext *v57; // rax
  __int64 (__fastcall ***v58)(_QWORD, _QWORD, _QWORD); // rbx
  CMFAppServiceConnectorBase **v59; // rdi
  CallStackTracing *v60; // rcx
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 (__fastcall ***v63)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v64)(_QWORD, GUID *, char *); // rsi
  CallStackTracing *v65; // rcx
  struct CallStackContext *v66; // rax
  CallStackTracing *v67; // rcx
  struct CallStackContext *v68; // rax
  __int64 (__fastcall ***v69)(_QWORD, _QWORD, _QWORD); // rdi
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  CallStackTracing *v72; // rcx
  struct CallStackContext *v73; // rax
  __int64 v74; // rcx
  CMFAppServiceConnectorBase *v76; // [rsp+30h] [rbp-49h] BYREF
  CallStackScopeTrace v77; // [rsp+38h] [rbp-41h] BYREF
  __int64 (__fastcall ***v78)(_QWORD, GUID *, char *); // [rsp+40h] [rbp-39h] BYREF
  CMFAppServiceConnectorBase **v79; // [rsp+48h] [rbp-31h] BYREF
  __int64 v80; // [rsp+50h] [rbp-29h] BYREF
  struct Windows::System::IUser *v81; // [rsp+58h] [rbp-21h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v82; // [rsp+60h] [rbp-19h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v77, "CMFAppServiceConnectorBase::OpenConnection", 232);
  v78 = 0;
  v81 = 0;
  v80 = 0;
  if ( (unsigned int)MFIsProcessIntegrityLevelHighOrSystem() )
  {
    v4 = CallStackTracing::s_wpInstance;
    MediaExtensionCommunicationFactory = -1072843856;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v4 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v4->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
      if ( ThreadRelativeContext->m_result != -1072843856 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFAppServiceConnectorBase::OpenConnection",
          243,
          -1072843856);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_238;
    v7 = 28;
    goto LABEL_237;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this);
  if ( *((_BYTE *)this + 120) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    MediaExtensionCommunicationFactory = GetMediaExtensionCommunicationFactory(&v80);
    if ( MediaExtensionCommunicationFactory < 0 )
    {
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v8 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v8->m_fEnabled )
      {
        v9 = CallStackTracing::GetThreadRelativeContext(v8);
        if ( v9->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v9,
            "CMFAppServiceConnectorBase::OpenConnection",
            250,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_238;
      v10 = 30;
      goto LABEL_24;
    }
    v11 = v80;
    v12 = (_QWORD *)((char *)this + 64);
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)v80 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
    LOBYTE(v14) = *((_BYTE *)this + 121);
    MediaExtensionCommunicationFactory = v13(
                                           v11,
                                           *((_QWORD *)this + 11),
                                           *((_QWORD *)this + 10),
                                           v14,
                                           (char *)this + 64);
    if ( MediaExtensionCommunicationFactory < 0 )
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
        if ( v16->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v16,
            "CMFAppServiceConnectorBase::OpenConnection",
            256,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_238;
      v10 = 31;
      goto LABEL_24;
    }
  }
  else
  {
    v12 = (_QWORD *)((char *)this + 64);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
    v82.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v82,
      L"Windows.ApplicationModel.AppService.AppServiceConnection",
      0x39u,
      0x38u);
    MediaExtensionCommunicationFactory = RoActivateInstance(v82.hstr_, (char *)this + 64);
    if ( MediaExtensionCommunicationFactory < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      v82.hstr_ = 0;
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
        if ( v18->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v18,
            "CMFAppServiceConnectorBase::OpenConnection",
            260,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_238;
      v10 = 32;
      goto LABEL_24;
    }
    MediaExtensionCommunicationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v12 + 56LL))(
                                           *v12,
                                           *((_QWORD *)this + 10));
    if ( MediaExtensionCommunicationFactory < 0 )
    {
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
        if ( v20->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v20,
            "CMFAppServiceConnectorBase::OpenConnection",
            262,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_238;
      v10 = 33;
      goto LABEL_24;
    }
    MediaExtensionCommunicationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v12 + 72LL))(
                                           *v12,
                                           *((_QWORD *)this + 11));
    if ( MediaExtensionCommunicationFactory < 0 )
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
        if ( v22->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v22,
            "CMFAppServiceConnectorBase::OpenConnection",
            263,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_238;
      v10 = 34;
      goto LABEL_24;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  if ( (int)GetCurrentUser(&v81) >= 0 && v81 )
  {
    v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, CMFAppServiceConnectorBase **))*v12;
    v76 = 0;
    v24 = **v23;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    MediaExtensionCommunicationFactory = v24(v23, &GUID_8bdfcd5f_2302_4fbd_8061_52511c2f8bf9, &v76);
    if ( MediaExtensionCommunicationFactory < 0 )
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
        if ( v26->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v26,
            "CMFAppServiceConnectorBase::OpenConnection",
            271,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_158;
      v27 = 35;
      goto LABEL_77;
    }
    MediaExtensionCommunicationFactory = (*(__int64 (__fastcall **)(CMFAppServiceConnectorBase *, struct Windows::System::IUser *))(*(_QWORD *)v76 + 64LL))(
                                           v76,
                                           v81);
    if ( MediaExtensionCommunicationFactory < 0 )
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
        if ( v29->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v29,
            "CMFAppServiceConnectorBase::OpenConnection",
            272,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_158;
      v27 = 36;
LABEL_77:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        &WPP_29e89521b84936885e6d012356985b16_Traceguids,
        this,
        MediaExtensionCommunicationFactory);
      goto LABEL_158;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  }
  v76 = 0;
  v79 = &v76;
  v30 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v79);
  MediaExtensionCommunicationFactory = Microsoft::WRL::AsWeak<Windows::Media::Core::IMediaStreamSource>(this, v30);
  if ( MediaExtensionCommunicationFactory < 0 )
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
      if ( v32->m_result != MediaExtensionCommunicationFactory )
        CallStackContext::TraceFailure(
          v32,
          "CMFAppServiceConnectorBase::OpenConnection",
          278,
          MediaExtensionCommunicationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_158;
    v33 = 37;
    goto LABEL_112;
  }
  v34 = lambda_544164bf796fac7e1cd6aaaae74032e1_::_lambda_544164bf796fac7e1cd6aaaae74032e1_(&v82, &v76, this);
  v35 = (CMFAppServiceConnectorBase **)operator new(0x50u, &std::nothrow);
  v79 = v35;
  v36 = 0;
  if ( v35 )
  {
    v36 = Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::ApplicationModel::AppService::AppServiceConnection___Windows::ApplicationModel::AppService::IAppServiceConnection____Windows::Foundation::Internal::AggregateType_Windows::ApplicationModel::AppService::AppServiceClosedEventArgs___Windows::ApplicationModel::AppService::IAppServiceClosedEventArgs_____::___Windows::ApplicationModel::AppService::IAppServiceConnection___Windows::ApplicationModel::AppService::IAppServiceClosedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::ApplicationModel::AppService::AppServiceConnection___Windows::ApplicationModel::AppService::AppServiceClosedEventArgs____Microsoft::WRL::FtmBase___lambda_544164bf796fac7e1cd6aaaae74032e1_____1_Windows::ApplicationModel::AppService::IAppServiceConnection___Windows::ApplicationModel::AppService::IAppServiceClosedEventArgs___::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::ApplicationModel::AppService::AppServiceConnection___Windows::ApplicationModel::AppService::AppServiceClosedEventArgs____Microsoft::WRL::FtmBase___lambda_544164bf796fac7e1cd6aaaae74032e1_____1_Windows::ApplicationModel::AppService::IAppServiceConnection___Windows::ApplicationModel::AppService::IAppServiceClosedEventArgs___(
            v35,
            v34);
    v79 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator__StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus__Windows::Foundation::IAsyncOperation_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus___lambda_373e6b57ace209d42b84316c468ec2a7____::_2_::FTMEventDelegate_::_MakeAllocator__StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus__Windows::Foundation::IAsyncOperation_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus___lambda_373e6b57ace209d42b84316c468ec2a7____::_2_::FTMEventDelegate_(&v79);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
  if ( !v36 )
  {
    v37 = CallStackTracing::s_wpInstance;
    MediaExtensionCommunicationFactory = -2147024882;
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
      if ( v38->m_result != -2147024882 )
        CallStackContext::TraceFailure(v38, "CMFAppServiceConnectorBase::OpenConnection", 293, -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_158;
    v33 = 39;
LABEL_112:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v33,
      &WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      MediaExtensionCommunicationFactory);
    goto LABEL_158;
  }
  MediaExtensionCommunicationFactory = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v12 + 112LL))(
                                         *v12,
                                         v36,
                                         (char *)this + 72);
  if ( MediaExtensionCommunicationFactory < 0 )
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
      if ( v40->m_result != MediaExtensionCommunicationFactory )
        CallStackContext::TraceFailure(
          v40,
          "CMFAppServiceConnectorBase::OpenConnection",
          295,
          MediaExtensionCommunicationFactory);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_29e89521b84936885e6d012356985b16_Traceguids,
        this,
        MediaExtensionCommunicationFactory);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    goto LABEL_158;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  if ( !*((_BYTE *)this + 120) )
  {
    v45 = IsCoreWindowApplication();
    v46 = (__int64 (__fastcall ***)(_QWORD, GUID *, CMFAppServiceConnectorBase **))*v12;
    if ( !v45 )
    {
      v76 = 0;
      v50 = **v46;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      MediaExtensionCommunicationFactory = v50(v46, &GUID_65219584_f9cb_4ae3_81f9_a28a6ca450d9, &v76);
      if ( MediaExtensionCommunicationFactory >= 0 )
      {
        v54 = v76;
        v55 = *(__int64 (__fastcall **)(CMFAppServiceConnectorBase *, GUID *, _QWORD))(*(_QWORD *)v76 + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        MediaExtensionCommunicationFactory = v55(v54, &GUID_0d0e6663_2639_5a9a_9cbc_30d7d4ce533b, &v78);
        if ( MediaExtensionCommunicationFactory >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
          goto LABEL_170;
        }
        v56 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v56 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v56 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v56->m_fEnabled )
        {
          v57 = CallStackTracing::GetThreadRelativeContext(v56);
          if ( v57->m_result != MediaExtensionCommunicationFactory )
            CallStackContext::TraceFailure(
              v57,
              "CMFAppServiceConnectorBase::OpenConnection",
              313,
              MediaExtensionCommunicationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_158;
        v53 = 44;
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
          if ( v52->m_result != MediaExtensionCommunicationFactory )
            CallStackContext::TraceFailure(
              v52,
              "CMFAppServiceConnectorBase::OpenConnection",
              312,
              MediaExtensionCommunicationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_158;
        v53 = 43;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v53,
        &WPP_29e89521b84936885e6d012356985b16_Traceguids,
        this,
        MediaExtensionCommunicationFactory);
LABEL_158:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      goto LABEL_238;
    }
    v47 = (*v46)[10];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    MediaExtensionCommunicationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, CMFAppServiceConnectorBase **), __int64 (__fastcall ****)(_QWORD, GUID *, char *)))v47)(
                                           v46,
                                           &v78);
    if ( MediaExtensionCommunicationFactory >= 0 )
      goto LABEL_170;
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
      if ( v49->m_result != MediaExtensionCommunicationFactory )
        CallStackContext::TraceFailure(
          v49,
          "CMFAppServiceConnectorBase::OpenConnection",
          307,
          MediaExtensionCommunicationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_238;
    v10 = 42;
LABEL_24:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      &WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      MediaExtensionCommunicationFactory);
    goto LABEL_238;
  }
  v41 = v80;
  v42 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v80 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  MediaExtensionCommunicationFactory = v42(v41, *v12, &v78);
  if ( MediaExtensionCommunicationFactory < 0 )
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
      if ( v44->m_result != MediaExtensionCommunicationFactory )
        CallStackContext::TraceFailure(
          v44,
          "CMFAppServiceConnectorBase::OpenConnection",
          303,
          MediaExtensionCommunicationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_238;
    v10 = 41;
    goto LABEL_24;
  }
LABEL_170:
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this);
  if ( a2 )
  {
    v79 = (CMFAppServiceConnectorBase **)this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v79);
    v76 = this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v76);
    v58 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v78;
    Microsoft::WRL::Details::Make__StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus__Windows::Foundation::IAsyncOperation_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus___lambda_373e6b57ace209d42b84316c468ec2a7____::_2_::FTMEventDelegate__lambda_373e6b57ace209d42b84316c468ec2a7___(
      &v79,
      &v76);
    v59 = v79;
    if ( v79 )
      MediaExtensionCommunicationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), CMFAppServiceConnectorBase **))(*v58)[6])(
                                             v58,
                                             v79);
    else
      MediaExtensionCommunicationFactory = -2147024882;
    if ( v59 )
      (*((void (__fastcall **)(CMFAppServiceConnectorBase **))*v59 + 2))(v59);
    if ( v76 )
      (*(void (__fastcall **)(CMFAppServiceConnectorBase *))(*(_QWORD *)v76 + 16LL))(v76);
    if ( MediaExtensionCommunicationFactory >= 0 )
    {
      v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v78;
      v64 = **v78;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 128);
      MediaExtensionCommunicationFactory = v64(v63, &GUID_00000036_0000_0000_c000_000000000046, (char *)this + 128);
      if ( MediaExtensionCommunicationFactory >= 0 )
      {
        MediaExtensionCommunicationFactory = MFScheduleWorkItem(
                                               (IMFAsyncCallback *)this + 2,
                                               0,
                                               -10000,
                                               (MFWORKITEM_KEY *)this + 17);
        if ( MediaExtensionCommunicationFactory >= 0 )
        {
          (*(void (__fastcall **)(CMFAppServiceConnectorBase *))(*(_QWORD *)this + 16LL))(this);
          goto LABEL_242;
        }
        v67 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v67 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v67 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v67->m_fEnabled )
        {
          v68 = CallStackTracing::GetThreadRelativeContext(v67);
          if ( v68->m_result != MediaExtensionCommunicationFactory )
            CallStackContext::TraceFailure(
              v68,
              "CMFAppServiceConnectorBase::OpenConnection",
              333,
              MediaExtensionCommunicationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_191;
        v62 = 48;
      }
      else
      {
        v65 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v65 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v65 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v65->m_fEnabled )
        {
          v66 = CallStackTracing::GetThreadRelativeContext(v65);
          if ( v66->m_result != MediaExtensionCommunicationFactory )
            CallStackContext::TraceFailure(
              v66,
              "CMFAppServiceConnectorBase::OpenConnection",
              329,
              MediaExtensionCommunicationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_191;
        v62 = 47;
      }
    }
    else
    {
      v60 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v60 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v60 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v60->m_fEnabled )
      {
        v61 = CallStackTracing::GetThreadRelativeContext(v60);
        if ( v61->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(
            v61,
            "CMFAppServiceConnectorBase::OpenConnection",
            327,
            MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_191;
      v62 = 46;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v62,
      &WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      MediaExtensionCommunicationFactory);
LABEL_191:
    (*(void (__fastcall **)(CMFAppServiceConnectorBase *))(*(_QWORD *)this + 16LL))(this);
    goto LABEL_238;
  }
  v69 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v78;
  LODWORD(v76) = 0;
  MediaExtensionCommunicationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(v78);
  if ( MediaExtensionCommunicationFactory >= 0 )
    MediaExtensionCommunicationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), CMFAppServiceConnectorBase **))(*v69)[8])(
                                           v69,
                                           &v76);
  if ( MediaExtensionCommunicationFactory < 0 )
  {
    v70 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v70 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v70 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v70->m_fEnabled )
    {
      v71 = CallStackTracing::GetThreadRelativeContext(v70);
      if ( v71->m_result != MediaExtensionCommunicationFactory )
        CallStackContext::TraceFailure(
          v71,
          "CMFAppServiceConnectorBase::OpenConnection",
          338,
          MediaExtensionCommunicationFactory);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_238;
    v10 = 49;
    goto LABEL_24;
  }
  if ( (_DWORD)v76 )
  {
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        50,
        &WPP_29e89521b84936885e6d012356985b16_Traceguids,
        this,
        (_DWORD)v76);
    v72 = CallStackTracing::s_wpInstance;
    MediaExtensionCommunicationFactory = -1072843856;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v72 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v72 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v72->m_fEnabled )
    {
      v73 = CallStackTracing::GetThreadRelativeContext(v72);
      if ( v73->m_result != -1072843856 )
        CallStackContext::TraceFailure(v73, "CMFAppServiceConnectorBase::OpenConnection", 343, -1072843856);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_238;
    v7 = 51;
LABEL_237:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      &WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      -1072843856);
LABEL_238:
    v74 = *((_QWORD *)this + 16);
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 72LL))(v74);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 128);
    }
    goto LABEL_242;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this);
LABEL_242:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  CallStackScopeTrace::~CallStackScopeTrace(&v77);
  return (unsigned int)MediaExtensionCommunicationFactory;
}

```

## disassembly

```asm
0x180113cdc  push    rbp
0x180113cde  push    rbx
0x180113cdf  push    rsi
0x180113ce0  push    rdi
0x180113ce1  push    r12
0x180113ce3  push    r13
0x180113ce5  push    r14
0x180113ce7  push    r15
0x180113ce9  lea     rbp, [rsp-1Fh]
0x180113cee  sub     rsp, 98h
0x180113cf5  mov     rax, cs:__security_cookie
0x180113cfc  xor     rax, rsp
0x180113cff  mov     [rbp+57h+var_50], rax
0x180113d03  mov     r12b, dl
0x180113d06  lea     rdi, aCmfappservicec_0; "CMFAppServiceConnectorBase::OpenConnect"...
0x180113d0d  mov     r14, rcx
0x180113d10  mov     rdx, rdi; char *
0x180113d13  mov     r8d, 0E8h; int
0x180113d19  lea     rcx, [rbp+57h+var_98]; this
0x180113d1d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180113d22  xor     r13d, r13d
0x180113d25  mov     [rbp+57h+var_90], r13
0x180113d29  mov     [rbp+57h+var_78], r13
0x180113d2d  mov     [rbp+57h+var_80], r13
0x180113d31  call    ?MFIsProcessIntegrityLevelHighOrSystem@@YAHXZ; MFIsProcessIntegrityLevelHighOrSystem(void)
0x180113d36  test    eax, eax
0x180113d38  jz      loc_180113DDB
0x180113d3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180113d45  mov     edi, 0C00DB3B0h
0x180113d4a  mov     ebx, edi
0x180113d4c  test    rcx, rcx
0x180113d4f  jnz     short loc_180113D92
0x180113d51  mov     rax, cs:stru_1801FC290.__vftable
0x180113d58  lea     r8, stru_1801FC290
0x180113d5f  mov     edx, 7F0h
0x180113d64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180113d6b  mov     rcx, r8
0x180113d6e  mov     rax, [rax+8]
0x180113d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113d77  test    eax, eax
0x180113d79  jnz     short loc_180113D8B
0x180113d7b  lea     rcx, stru_1801F8A30
0x180113d82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180113d89  jmp     short loc_180113D92
0x180113d8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180113d92  cmp     [rcx+8], r13b
0x180113d96  jz      short loc_180113DBD
0x180113d98  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180113d9d  cmp     [rax+7CCh], edi
0x180113da3  jz      short loc_180113DBD
0x180113da5  mov     r9d, edi; int
0x180113da8  lea     rdx, aCmfappservicec_0; "CMFAppServiceConnectorBase::OpenConnect"...
0x180113daf  mov     r8d, 0F3h; int
0x180113db5  mov     rcx, rax; this
0x180113db8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180113dbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180113dc4  jb      loc_180114DE8
0x180113dca  mov     edx, 1Ch
0x180113dcf  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180113dd6  jmp     loc_180114DD1
0x180113ddb  cmp     cs:byte_1801FD289, 10h
0x180113de2  lea     r15, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180113de9  jb      short loc_180113E06
0x180113deb  mov     rcx, cs:WPP_GLOBAL_Control
0x180113df2  mov     edx, 1Dh
0x180113df7  mov     r9, r14
0x180113dfa  mov     r8, r15
0x180113dfd  mov     rcx, [rcx+38h]
0x180113e01  call    WPP_SF_q
0x180113e06  cmp     [r14+78h], r13b
0x180113e0a  jz      loc_180113F8B
0x180113e10  lea     rcx, [rbp+57h+var_80]
0x180113e14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180113e19  lea     rcx, [rbp+57h+var_80]
0x180113e1d  call    cs:__imp_GetMediaExtensionCommunicationFactory
0x180113e23  mov     ebx, eax
0x180113e25  test    eax, eax
0x180113e27  jns     loc_180113EBF
0x180113e2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180113e34  test    rcx, rcx
0x180113e37  jnz     short loc_180113E7A
0x180113e39  mov     rcx, cs:stru_1801FC290.__vftable
0x180113e40  lea     r8, stru_1801FC290
0x180113e47  mov     edx, 7F0h
0x180113e4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180113e53  mov     rax, [rcx+8]
0x180113e57  mov     rcx, r8
0x180113e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113e5f  test    eax, eax
0x180113e61  jnz     short loc_180113E73
0x180113e63  lea     rcx, stru_1801F8A30
0x180113e6a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180113e71  jmp     short loc_180113E7A
0x180113e73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180113e7a  cmp     [rcx+8], r13b
0x180113e7e  jz      short loc_180113EA1
0x180113e80  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180113e85  cmp     [rax+7CCh], ebx
0x180113e8b  jz      short loc_180113EA1
0x180113e8d  mov     r9d, ebx; int
0x180113e90  mov     r8d, 0FAh; int
0x180113e96  mov     rdx, rdi; char *
0x180113e99  mov     rcx, rax; this
0x180113e9c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180113ea1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180113ea8  jb      loc_180114DE8
0x180113eae  mov     edx, 1Eh
0x180113eb3  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180113eb7  mov     r8, r15
0x180113eba  jmp     loc_180114DD5
0x180113ebf  mov     rdi, [rbp+57h+var_80]
0x180113ec3  lea     rsi, [r14+40h]
0x180113ec7  mov     rcx, rsi
0x180113eca  mov     rax, [rdi]
0x180113ecd  mov     rbx, [rax+48h]
0x180113ed1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180113ed6  mov     r9b, [r14+79h]
0x180113eda  mov     rcx, rdi
0x180113edd  mov     r8, [r14+50h]
0x180113ee1  mov     rax, rbx
0x180113ee4  mov     rdx, [r14+58h]
0x180113ee8  mov     [rsp+0D0h+var_B0], rsi
0x180113eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113ef2  mov     ebx, eax
0x180113ef4  test    eax, eax
0x180113ef6  jns     loc_1801141AB
0x180113efc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180113f03  test    rcx, rcx
0x180113f06  jnz     short loc_180113F49
0x180113f08  mov     rax, cs:stru_1801FC290.__vftable
0x180113f0f  lea     r8, stru_1801FC290
0x180113f16  mov     edx, 7F0h
0x180113f1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180113f22  mov     rcx, r8
0x180113f25  mov     rax, [rax+8]
0x180113f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113f2e  test    eax, eax
0x180113f30  jnz     short loc_180113F42
0x180113f32  lea     rcx, stru_1801F8A30
0x180113f39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180113f40  jmp     short loc_180113F49
0x180113f42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180113f49  cmp     [rcx+8], r13b
0x180113f4d  jz      short loc_180113F74
0x180113f4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180113f54  cmp     [rax+7CCh], ebx
0x180113f5a  jz      short loc_180113F74
0x180113f5c  mov     r9d, ebx; int
0x180113f5f  lea     rdx, aCmfappservicec_0; "CMFAppServiceConnectorBase::OpenConnect"...
0x180113f66  mov     r8d, 100h; int
0x180113f6c  mov     rcx, rax; this
0x180113f6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180113f74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180113f7b  jb      loc_180114DE8
0x180113f81  mov     edx, 1Fh
0x180113f86  jmp     loc_180113EB3
0x180113f8b  lea     rsi, [r14+40h]
0x180113f8f  mov     rcx, rsi
0x180113f92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180113f97  mov     r9d, 38h ; '8'; unsigned int
0x180113f9d  mov     [rbp+57h+var_70.hstr_], r13
0x180113fa1  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; "Windows.ApplicationModel.AppService.App"...
0x180113fa8  lea     rcx, [rbp+57h+var_70]; this
0x180113fac  lea     r8d, [r9+1]; unsigned int
0x180113fb0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180113fb5  mov     rcx, [rbp+57h+var_70.hstr_]
0x180113fb9  mov     rdx, rsi
0x180113fbc  call    cs:__imp_RoActivateInstance
0x180113fc2  mov     ebx, eax
0x180113fc4  test    eax, eax
0x180113fc6  jns     loc_18011405B
0x180113fcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180113fd3  mov     [rbp+57h+var_70.hstr_], r13
0x180113fd7  test    rcx, rcx
0x180113fda  jnz     short loc_18011401D
0x180113fdc  mov     rax, cs:stru_1801FC290.__vftable
0x180113fe3  lea     r8, stru_1801FC290
0x180113fea  mov     edx, 7F0h
0x180113fef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180113ff6  mov     rcx, r8
0x180113ff9  mov     rax, [rax+8]
0x180113ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114002  test    eax, eax
0x180114004  jnz     short loc_180114016
0x180114006  lea     rcx, stru_1801F8A30
0x18011400d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114014  jmp     short loc_18011401D
0x180114016  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011401d  cmp     [rcx+8], r13b
0x180114021  jz      short loc_180114044
0x180114023  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114028  cmp     [rax+7CCh], ebx
0x18011402e  jz      short loc_180114044
0x180114030  mov     r9d, ebx; int
0x180114033  mov     r8d, 104h; int
0x180114039  mov     rdx, rdi; char *
0x18011403c  mov     rcx, rax; this
0x18011403f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114044  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011404b  jb      loc_180114DE8
0x180114051  mov     edx, 20h ; ' '
0x180114056  jmp     loc_180113EB3
0x18011405b  mov     rcx, [rsi]
0x18011405e  mov     rdx, [r14+50h]
0x180114062  mov     rax, [rcx]
0x180114065  mov     rax, [rax+38h]
0x180114069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011406e  mov     ebx, eax
0x180114070  test    eax, eax
0x180114072  jns     loc_180114103
0x180114078  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011407f  test    rcx, rcx
0x180114082  jnz     short loc_1801140C5
0x180114084  mov     rax, cs:stru_1801FC290.__vftable
0x18011408b  lea     r8, stru_1801FC290
0x180114092  mov     edx, 7F0h
0x180114097  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011409e  mov     rcx, r8
0x1801140a1  mov     rax, [rax+8]
0x1801140a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801140aa  test    eax, eax
0x1801140ac  jnz     short loc_1801140BE
0x1801140ae  lea     rcx, stru_1801F8A30
0x1801140b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801140bc  jmp     short loc_1801140C5
0x1801140be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801140c5  cmp     [rcx+8], r13b
0x1801140c9  jz      short loc_1801140EC
0x1801140cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801140d0  cmp     [rax+7CCh], ebx
0x1801140d6  jz      short loc_1801140EC
0x1801140d8  mov     r9d, ebx; int
0x1801140db  mov     r8d, 106h; int
0x1801140e1  mov     rdx, rdi; char *
0x1801140e4  mov     rcx, rax; this
0x1801140e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801140ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801140f3  jb      loc_180114DE8
0x1801140f9  mov     edx, 21h ; '!'
0x1801140fe  jmp     loc_180113EB3
0x180114103  mov     rcx, [rsi]
0x180114106  mov     rdx, [r14+58h]
0x18011410a  mov     rax, [rcx]
0x18011410d  mov     rax, [rax+48h]
0x180114111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114116  mov     ebx, eax
0x180114118  test    eax, eax
0x18011411a  jns     loc_1801141AB
0x180114120  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114127  test    rcx, rcx
0x18011412a  jnz     short loc_18011416D
0x18011412c  mov     rax, cs:stru_1801FC290.__vftable
0x180114133  lea     r8, stru_1801FC290
0x18011413a  mov     edx, 7F0h
0x18011413f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180114146  mov     rcx, r8
0x180114149  mov     rax, [rax+8]
0x18011414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114152  test    eax, eax
0x180114154  jnz     short loc_180114166
0x180114156  lea     rcx, stru_1801F8A30
0x18011415d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114164  jmp     short loc_18011416D
0x180114166  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011416d  cmp     [rcx+8], r13b
0x180114171  jz      short loc_180114194
0x180114173  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114178  cmp     [rax+7CCh], ebx
0x18011417e  jz      short loc_180114194
0x180114180  mov     r9d, ebx; int
0x180114183  mov     r8d, 107h; int
0x180114189  mov     rdx, rdi; char *
0x18011418c  mov     rcx, rax; this
0x18011418f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114194  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011419b  jb      loc_180114DE8
0x1801141a1  mov     edx, 22h ; '"'
0x1801141a6  jmp     loc_180113EB3
0x1801141ab  lea     rcx, [rbp+57h+var_78]
0x1801141af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801141b4  lea     rcx, [rbp+57h+var_78]; struct Windows::System::IUser **
0x1801141b8  call    ?GetCurrentUser@@YAJPEAPEAUIUser@System@Windows@@@Z; GetCurrentUser(Windows::System::IUser * *)
0x1801141bd  test    eax, eax
0x1801141bf  js      loc_180114369
0x1801141c5  cmp     [rbp+57h+var_78], r13
0x1801141c9  jz      loc_180114369
0x1801141cf  mov     rdi, [rsi]
0x1801141d2  lea     rcx, [rbp+57h+var_A0]
0x1801141d6  mov     [rbp+57h+var_A0], r13
0x1801141da  mov     rax, [rdi]
0x1801141dd  mov     rbx, [rax]
0x1801141e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801141e5  lea     r8, [rbp+57h+var_A0]
0x1801141e9  mov     rcx, rdi
0x1801141ec  lea     rdx, _GUID_8bdfcd5f_2302_4fbd_8061_52511c2f8bf9
0x1801141f3  mov     rax, rbx
0x1801141f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801141fb  mov     ebx, eax
0x1801141fd  test    eax, eax
0x1801141ff  jns     loc_1801142B3
  ... truncated ...
```
