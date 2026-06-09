# CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted(long,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *)

- ea: `0x180108a10`
- end: `0x180109b4d`
- name: `?OnConnectionOpenOperationCompleted@CMFMediaSourceAppServiceConnector@@EEAAXJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@Z`
- size: `4413`
- prototype: `__int64 __fastcall(CMFMediaSourceAppServiceConnector *this, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004870`
- `0x180011454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180033dc8`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800a0074`
- `0x1800c5a2c`
- `0x180108a10`
- `0x18010a824`
- `0x1801200d0`
- `0x180120ecc`
- `0x1801250c8`
- `0x18014c084`
- `0x18015931c`
- `0x180165544`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180108a49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180108a49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180109b20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180109b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180109511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180109511`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801094ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801094ff`
- `RTWorkQ!RtwqCancelWorkItem` at `0x180108bac`
- `RTWorkQ!RtwqCancelWorkItem` at `0x180108bac`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180109175`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180109175`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18010945c`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18010945c`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180109234`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1801092f1`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180109234`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1801092f1`

## string_xrefs

- `0x180108a4f`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180108ad6`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180109027`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180109133`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x1801091e8`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x1801092a7`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180109364`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180109427`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x1801094cf`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x18010958d`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x1801096d3`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x1801097a0`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180109888`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x18010997c`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x180109a75`: `CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted`
- `0x1801097d1`: `MediaSourceExtension`

## pseudocode

```c
void __fastcall CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted(
        CMFMediaSourceAppServiceConnector *this,
        int HGlobalFromStream,
        __int64 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r13
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v9; // ebx
  _GUID *v10; // rax
  _GUID v11; // xmm0
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  __int64 v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *)); // rbx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v32)(_QWORD, GUID *, LPUNKNOWN *); // rdi
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  LPVOID v45; // r12
  signed int LastError; // eax
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  void *Reserved1; // rdi
  __int64 (__fastcall *v52)(void *, _QWORD, LPVOID, __int64 *); // rbx
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  _QWORD *v55; // rsi
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 (__fastcall *v58)(_QWORD *, HSTRING__ *, __int64, CallStackScopeTrace *); // rdi
  CallStackTracing *v59; // rcx
  struct CallStackContext *v60; // rax
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, __int64, __int64 *); // rbx
  CallStackTracing *v63; // rcx
  struct CallStackContext *v64; // rax
  __int64 v65; // rdi
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // rbx
  CallStackTracing *v67; // rcx
  struct CallStackContext *v68; // rax
  CallStackScopeTrace v69; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v70; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v71; // [rsp+40h] [rbp-C0h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v73; // [rsp+50h] [rbp-B0h] BYREF
  CMFMediaSourceAppServiceConnector *v74; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v75)(_QWORD, GUID *, LPUNKNOWN *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  LPUNKNOWN pUnk; // [rsp+70h] [rbp-90h] BYREF
  int v78; // [rsp+78h] [rbp-88h] BYREF
  HGLOBAL phglobal; // [rsp+80h] [rbp-80h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v80; // [rsp+88h] [rbp-78h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v81; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v82[16]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v83; // [rsp+E0h] [rbp-20h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  phglobal = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    &v69,
    "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
    614);
  v7 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 27) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 296LL))(*((_QWORD *)this + 27));
    v10 = (_GUID *)(*(__int64 (__fastcall **)(_QWORD, Microsoft::WRL::Wrappers::HStringReference *))(**((_QWORD **)this + 27) + 280LL))(
                     *((_QWORD *)this + 27),
                     &v80);
    v7 = CallStackTracing::s_wpInstance;
    v11 = *v10;
    ThreadRelativeContext->m_instanceId = v9;
    ThreadRelativeContext->m_sessionId = v11;
  }
  if ( !*((_QWORD *)this + 26) )
  {
    HGlobalFromStream = -1072875795;
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
        CallStackContext::TraceFailure(
          v12,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          614,
          -1072875795);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_213;
    v13 = 101;
    goto LABEL_14;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)this + 16);
  RtwqCancelWorkItem(*((_QWORD *)this + 17));
  *((_QWORD *)this + 17) = 0;
  if ( HGlobalFromStream < 0 )
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
      if ( v15->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v15,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          622,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_213;
    v13 = 102;
    goto LABEL_14;
  }
  v16 = *a3;
  v78 = 0;
  HGlobalFromStream = (*(__int64 (__fastcall **)(__int64 *, int *))(v16 + 64))(a3, &v78);
  if ( HGlobalFromStream < 0 )
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
      if ( v18->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v18,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          625,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_213;
    v13 = 103;
    goto LABEL_14;
  }
  if ( v78 )
  {
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 104, WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v78);
    v19 = CallStackTracing::s_wpInstance;
    HGlobalFromStream = -1072843856;
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
      if ( v20->m_result != -1072843856 )
        CallStackContext::TraceFailure(
          v20,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          630,
          -1072843856);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_213;
    v13 = 105;
LABEL_14:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      HGlobalFromStream);
LABEL_213:
    CMFMediaSourceAppServiceConnector::SignalMediaSourceCreation(this, HGlobalFromStream);
    goto LABEL_215;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 106, WPP_29e89521b84936885e6d012356985b16_Traceguids, this);
  v71 = 0;
  v74 = this;
  Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalAddRef(&v74);
  v70 = 0;
  v73 = 0;
  v80.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v80,
    L"Windows.Foundation.Collections.PropertySet",
    0x2Bu,
    0x2Au);
  HGlobalFromStream = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                        v80.hstr_,
                        &v70);
  if ( HGlobalFromStream < 0 )
  {
    v21 = CallStackTracing::s_wpInstance;
    v80.hstr_ = 0;
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
      if ( v22->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v22,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          642,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_212;
    v23 = 107;
    goto LABEL_211;
  }
  HGlobalFromStream = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                        &v70,
                        &v73);
  if ( HGlobalFromStream < 0 )
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
      if ( v25->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v25,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          643,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_212;
    v23 = 108;
    goto LABEL_211;
  }
  v26 = *((_QWORD *)this + 26);
  v75 = 0;
  pUnk = 0;
  ppstm = 0;
  v80.header_.Reserved.Reserved1 = 0;
  v76 = 0;
  v27 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *)))(*(_QWORD *)v26 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
  HGlobalFromStream = v27(v26, &v75);
  if ( HGlobalFromStream < 0 )
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
      if ( v29->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v29,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          654,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 109;
LABEL_79:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      HGlobalFromStream);
LABEL_80:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v80);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppstm);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
LABEL_212:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v73);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    goto LABEL_213;
  }
  v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
  v32 = **v75;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pUnk);
  HGlobalFromStream = v32(v31, &GUID_3712d543_45eb_4138_aa62_c01e26f3843f, &pUnk);
  if ( HGlobalFromStream < 0 )
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
      if ( v34->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v34,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          655,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 110;
    goto LABEL_79;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppstm);
  HGlobalFromStream = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( HGlobalFromStream < 0 )
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
      if ( v36->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v36,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          657,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 111;
    goto LABEL_79;
  }
  HGlobalFromStream = CoMarshalInterface(ppstm, &IID_IMFByteStream, *((LPUNKNOWN *)this + 25), 0, 0, 0);
  if ( HGlobalFromStream < 0 )
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
      if ( v38->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v38,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          658,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 112;
    goto LABEL_79;
  }
  HGlobalFromStream = CoMarshalInterface(ppstm, &GUID_3712d543_45eb_4138_aa62_c01e26f3843f, pUnk, 0, 0, 0);
  if ( HGlobalFromStream < 0 )
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
      if ( v40->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v40,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          659,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 113;
    goto LABEL_79;
  }
  memset_0(v82, 0, 0x50u);
  HGlobalFromStream = ppstm->Stat(ppstm, (tagSTATSTG *)v82, 1u);
  if ( HGlobalFromStream < 0 )
  {
    v41 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v41 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v41->m_fEnabled )
    {
      v42 = CallStackTracing::GetThreadRelativeContext(v41);
      if ( v42->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v42,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          662,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 114;
    goto LABEL_79;
  }
  HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
  if ( HGlobalFromStream < 0 )
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
      if ( v44->m_result != HGlobalFromStream )
        CallStackContext::TraceFailure(
          v44,
          "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
          663,
          HGlobalFromStream);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_80;
    v30 = 115;
    goto LABEL_79;
  }
  v45 = GlobalLock(phglobal);
  if ( v45 )
  {
    v81.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v81, L"Windows.Foundation.PropertyValue", 0x21u, 0x20u);
    HGlobalFromStream = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
                          v81.hstr_,
                          &v80);
    if ( HGlobalFromStream < 0 )
    {
      v49 = CallStackTracing::s_wpInstance;
      v81.hstr_ = 0;
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
        if ( v50->m_result != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v50,
            "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
            668,
            HGlobalFromStream);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_80;
      v30 = 117;
      goto LABEL_79;
    }
    Reserved1 = v80.header_.Reserved.Reserved1;
    v52 = *(__int64 (__fastcall **)(void *, _QWORD, LPVOID, __int64 *))(*(_QWORD *)v80.header_.Reserved.Reserved1 + 240LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    HGlobalFromStream = v52(Reserved1, v83 >> 2, v45, &v76);
    if ( HGlobalFromStream < 0 )
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
        if ( v54->m_result != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v54,
            "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
            669,
            HGlobalFromStream);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_80;
      v30 = 118;
      goto LABEL_79;
    }
    v55 = v73;
    v56 = v76;
    v69 = 0;
    v57 = *v73;
    v81.hstr_ = 0;
    v58 = *(__int64 (__fastcall **)(_QWORD *, HSTRING__ *, __int64, CallStackScopeTrace *))(v57 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v81, L"MediaSourceExtension", 0x15u, 0x14u);
    HGlobalFromStream = v58(v55, v81.hstr_, v56, &v69);
    if ( HGlobalFromStream < 0 )
    {
      v59 = CallStackTracing::s_wpInstance;
      v81.hstr_ = 0;
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
        if ( v60->m_result != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v60,
            "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
            672,
            HGlobalFromStream);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_80;
      v30 = 119;
      goto LABEL_79;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v80);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppstm);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    v61 = *((_QWORD *)this + 8);
    v62 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v61 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    HGlobalFromStream = v62(v61, v70, &v71);
    if ( HGlobalFromStream >= 0 )
    {
      v80.header_.Reserved.Reserved1 = this;
      Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalAddRef(&v80);
      v65 = v71;
      Microsoft::WRL::Details::Make__StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::ApplicationModel::AppService::AppServiceResponse____Windows::Foundation::IAsyncOperation_Windows::ApplicationModel::AppService::AppServiceResponse_____lambda_c450870b2ab97fdd4923aa8095ef2cdd____::_2_::FTMEventDelegate__lambda_c450870b2ab97fdd4923aa8095ef2cdd___(
        &v75,
        &v80);
      v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
      if ( v75 )
        HGlobalFromStream = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, LPUNKNOWN *)))(*(_QWORD *)v65 + 48LL))(
                              v65,
                              v75);
      else
        HGlobalFromStream = -2147024882;
      if ( v66 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v66)[2])(v66);
      Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalRelease(&v80);
      if ( HGlobalFromStream >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v73);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
        goto LABEL_215;
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
        if ( v68->m_result != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v68,
            "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
            684,
            HGlobalFromStream);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_212;
      v23 = 121;
    }
    else
    {
      v63 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v63 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v63->m_fEnabled )
      {
        v64 = CallStackTracing::GetThreadRelativeContext(v63);
        if ( v64->m_result != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v64,
            "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
            676,
            HGlobalFromStream);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_212;
      v23 = 120;
    }
LABEL_211:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      HGlobalFromStream);
    goto LABEL_212;
  }
  LastError = GetLastError();
  HGlobalFromStream = LastError;
  if ( LastError > 0 )
    HGlobalFromStream = (unsigned __int16)LastError | 0x80070000;
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
    if ( HGlobalFromStream < 0 && v48->m_result != HGlobalFromStream )
      CallStackContext::TraceFailure(
        v48,
        "CMFMediaSourceAppServiceConnector::OnConnectionOpenOperationCompleted",
        666,
        HGlobalFromStream);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      WPP_29e89521b84936885e6d012356985b16_Traceguids,
      this,
      HGlobalFromStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppstm);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pUnk);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v73);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  if ( HGlobalFromStream < 0 )
    goto LABEL_213;
LABEL_215:
  CallStackScopeTrace::~CallStackScopeTrace(&v69);
  if ( v3 )
    LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180108a10  mov     [rsp-8+arg_18], rbx
0x180108a15  push    rbp
0x180108a16  push    rsi
0x180108a17  push    rdi
0x180108a18  push    r12
0x180108a1a  push    r13
0x180108a1c  push    r14
0x180108a1e  push    r15
0x180108a20  lea     rbp, [rsp-30h]
0x180108a25  sub     rsp, 130h
0x180108a2c  mov     rax, cs:__security_cookie
0x180108a33  xor     rax, rsp
0x180108a36  mov     [rbp+60h+var_40], rax
0x180108a3a  lea     r13, [rcx+18h]
0x180108a3e  mov     r14, rcx
0x180108a41  mov     rcx, r13; lpCriticalSection
0x180108a44  mov     r15, r8
0x180108a47  mov     esi, edx
0x180108a49  call    cs:__imp_EnterCriticalSection
0x180108a4f  lea     rbx, aCmfmediasource_6; "CMFMediaSourceAppServiceConnector::OnCo"...
0x180108a56  xor     r12d, r12d
0x180108a59  mov     rdx, rbx; char *
0x180108a5c  mov     [rbp+60h+phglobal], r12
0x180108a60  mov     r8d, 266h; int
0x180108a66  lea     rcx, [rsp+160h+var_130]; this
0x180108a6b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180108a70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108a77  cmp     [rcx+8], r12b
0x180108a7b  jz      short loc_180108AE5
0x180108a7d  cmp     [r14+0D8h], r12
0x180108a84  jz      short loc_180108AE5
0x180108a86  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108a8b  mov     rdx, [r14+0D8h]
0x180108a92  mov     rdi, rax
0x180108a95  mov     rcx, [rdx]
0x180108a98  mov     rax, [rcx+128h]
0x180108a9f  mov     rcx, rdx
0x180108aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108aa7  mov     r8, [r14+0D8h]
0x180108aae  lea     rdx, [rbp+60h+var_D8]
0x180108ab2  mov     ebx, eax
0x180108ab4  mov     rcx, [r8]
0x180108ab7  mov     rax, [rcx+118h]
0x180108abe  mov     rcx, r8
0x180108ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108ac6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180108acd  movups  xmm0, xmmword ptr [rax]
0x180108ad0  mov     [rdi+7E0h], ebx
0x180108ad6  lea     rbx, aCmfmediasource_6; "CMFMediaSourceAppServiceConnector::OnCo"...
0x180108add  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180108ae5  cmp     [r14+0D0h], r12
0x180108aec  jnz     loc_180108B99
0x180108af2  mov     esi, 0C00D36EDh
0x180108af7  test    rcx, rcx
0x180108afa  jnz     short loc_180108B3D
0x180108afc  mov     rax, cs:stru_1801FC290.__vftable
0x180108b03  lea     r8, stru_1801FC290
0x180108b0a  mov     edx, 7F0h
0x180108b0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180108b16  mov     rcx, r8
0x180108b19  mov     rax, [rax+8]
0x180108b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108b22  test    eax, eax
0x180108b24  jnz     short loc_180108B36
0x180108b26  lea     rcx, stru_1801F8A30
0x180108b2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180108b34  jmp     short loc_180108B3D
0x180108b36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108b3d  cmp     [rcx+8], r12b
0x180108b41  jz      short loc_180108B64
0x180108b43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108b48  cmp     [rax+7CCh], esi
0x180108b4e  jz      short loc_180108B64
0x180108b50  mov     r9d, esi; int
0x180108b53  mov     r8d, 266h; int
0x180108b59  mov     rdx, rbx; char *
0x180108b5c  mov     rcx, rax; this
0x180108b5f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180108b64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180108b6b  jb      loc_180109ADA
0x180108b71  mov     edx, 65h ; 'e'
0x180108b76  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180108b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180108b84  mov     r9, r14
0x180108b87  mov     dword ptr [rsp+160h+pvDestContext], esi
0x180108b8b  mov     rcx, [rcx+10h]
0x180108b8f  call    WPP_SF_qD
0x180108b94  jmp     loc_180109ADA
0x180108b99  lea     rcx, [r14+80h]
0x180108ba0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108ba5  mov     rcx, [r14+88h]; Key
0x180108bac  call    cs:__imp_RtwqCancelWorkItem
0x180108bb2  mov     [r14+88h], r12
0x180108bb9  test    esi, esi
0x180108bbb  jns     loc_180108C4C
0x180108bc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180108bc8  test    rcx, rcx
0x180108bcb  jnz     short loc_180108C0E
0x180108bcd  mov     rax, cs:stru_1801FC290.__vftable
0x180108bd4  lea     r8, stru_1801FC290
0x180108bdb  mov     edx, 7F0h
0x180108be0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180108be7  mov     rcx, r8
0x180108bea  mov     rax, [rax+8]
0x180108bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108bf3  test    eax, eax
0x180108bf5  jnz     short loc_180108C07
0x180108bf7  lea     rcx, stru_1801F8A30
0x180108bfe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180108c05  jmp     short loc_180108C0E
0x180108c07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108c0e  cmp     [rcx+8], r12b
0x180108c12  jz      short loc_180108C35
0x180108c14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108c19  cmp     [rax+7CCh], esi
0x180108c1f  jz      short loc_180108C35
0x180108c21  mov     r9d, esi; int
0x180108c24  mov     r8d, 26Eh; int
0x180108c2a  mov     rdx, rbx; char *
0x180108c2d  mov     rcx, rax; this
0x180108c30  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180108c35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180108c3c  jb      loc_180109ADA
0x180108c42  mov     edx, 66h ; 'f'
0x180108c47  jmp     loc_180108B76
0x180108c4c  mov     rax, [r15]
0x180108c4f  lea     rdx, [rsp+160h+var_E8]
0x180108c54  mov     rcx, r15
0x180108c57  mov     [rsp+160h+var_E8], r12d
0x180108c5c  mov     rax, [rax+40h]
0x180108c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108c65  mov     esi, eax
0x180108c67  test    eax, eax
0x180108c69  jns     loc_180108CFA
0x180108c6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180108c76  test    rcx, rcx
0x180108c79  jnz     short loc_180108CBC
0x180108c7b  mov     rcx, cs:stru_1801FC290.__vftable
0x180108c82  lea     r8, stru_1801FC290
0x180108c89  mov     edx, 7F0h
0x180108c8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180108c95  mov     rax, [rcx+8]
0x180108c99  mov     rcx, r8
0x180108c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108ca1  test    eax, eax
0x180108ca3  jnz     short loc_180108CB5
0x180108ca5  lea     rcx, stru_1801F8A30
0x180108cac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180108cb3  jmp     short loc_180108CBC
0x180108cb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108cbc  cmp     [rcx+8], r12b
0x180108cc0  jz      short loc_180108CE3
0x180108cc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108cc7  cmp     [rax+7CCh], esi
0x180108ccd  jz      short loc_180108CE3
0x180108ccf  mov     r9d, esi; int
0x180108cd2  mov     r8d, 271h; int
0x180108cd8  mov     rdx, rbx; char *
0x180108cdb  mov     rcx, rax; this
0x180108cde  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180108ce3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180108cea  jb      loc_180109ADA
0x180108cf0  mov     edx, 67h ; 'g'
0x180108cf5  jmp     loc_180108B76
0x180108cfa  mov     eax, [rsp+160h+var_E8]
0x180108cfe  test    eax, eax
0x180108d00  jz      loc_180108DC8
0x180108d06  cmp     cs:byte_1801FD289, 10h
0x180108d0d  lea     r15, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180108d14  jb      short loc_180108D35
0x180108d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180108d1d  mov     edx, 68h ; 'h'
0x180108d22  mov     r9, r14
0x180108d25  mov     dword ptr [rsp+160h+pvDestContext], eax
0x180108d29  mov     r8, r15
0x180108d2c  mov     rcx, [rcx+38h]
0x180108d30  call    WPP_SF_qD
0x180108d35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180108d3c  mov     esi, 0C00DB3B0h
0x180108d41  test    rcx, rcx
0x180108d44  jnz     short loc_180108D87
0x180108d46  mov     rax, cs:stru_1801FC290.__vftable
0x180108d4d  lea     r8, stru_1801FC290
0x180108d54  mov     edx, 7F0h
0x180108d59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180108d60  mov     rcx, r8
0x180108d63  mov     rax, [rax+8]
0x180108d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108d6c  test    eax, eax
0x180108d6e  jnz     short loc_180108D80
0x180108d70  lea     rcx, stru_1801F8A30
0x180108d77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180108d7e  jmp     short loc_180108D87
0x180108d80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108d87  cmp     [rcx+8], r12b
0x180108d8b  jz      short loc_180108DAE
0x180108d8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108d92  cmp     [rax+7CCh], esi
0x180108d98  jz      short loc_180108DAE
0x180108d9a  mov     r9d, esi; int
0x180108d9d  mov     r8d, 276h; int
0x180108da3  mov     rdx, rbx; char *
0x180108da6  mov     rcx, rax; this
0x180108da9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180108dae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180108db5  jb      loc_180109ADA
0x180108dbb  mov     edx, 69h ; 'i'
0x180108dc0  mov     r8, r15
0x180108dc3  jmp     loc_180108B7D
0x180108dc8  cmp     cs:byte_1801FD289, 10h
0x180108dcf  lea     r15, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x180108dd6  jb      short loc_180108DF3
0x180108dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180108ddf  mov     edx, 6Ah ; 'j'
0x180108de4  mov     r9, r14
0x180108de7  mov     r8, r15
0x180108dea  mov     rcx, [rcx+38h]
0x180108dee  call    WPP_SF_q
0x180108df3  lea     rcx, [rsp+160h+var_108]
0x180108df8  mov     [rsp+160h+var_120], r12
0x180108dfd  mov     [rsp+160h+var_108], r14
0x180108e02  call    ?InternalAddRef@?$ComPtr@VCMFMediaSourceAppServiceConnector@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CMFMediaSourceAppServiceConnector>::InternalAddRef(void)
0x180108e07  mov     r9d, 2Ah ; '*'; unsigned int
0x180108e0d  mov     [rsp+160h+var_128], r12
0x180108e12  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180108e19  mov     [rsp+160h+var_110], r12
0x180108e1e  lea     rcx, [rbp+60h+var_D8]; this
0x180108e22  mov     [rbp+60h+var_D8.hstr_], r12
0x180108e26  lea     r8d, [r9+1]; unsigned int
0x180108e2a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180108e2f  mov     rcx, [rbp+60h+var_D8.hstr_]
0x180108e33  lea     rdx, [rsp+160h+var_128]
0x180108e38  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180108e3d  mov     esi, eax
0x180108e3f  test    eax, eax
0x180108e41  jns     loc_180108ED6
0x180108e47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180108e4e  mov     [rbp+60h+var_D8.hstr_], r12
0x180108e52  test    rcx, rcx
0x180108e55  jnz     short loc_180108E98
0x180108e57  mov     rax, cs:stru_1801FC290.__vftable
0x180108e5e  lea     r8, stru_1801FC290
0x180108e65  mov     edx, 7F0h
0x180108e6a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180108e71  mov     rcx, r8
0x180108e74  mov     rax, [rax+8]
0x180108e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108e7d  test    eax, eax
0x180108e7f  jnz     short loc_180108E91
0x180108e81  lea     rcx, stru_1801F8A30
0x180108e88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180108e8f  jmp     short loc_180108E98
0x180108e91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108e98  cmp     [rcx+8], r12b
0x180108e9c  jz      short loc_180108EBF
0x180108e9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108ea3  cmp     [rax+7CCh], esi
0x180108ea9  jz      short loc_180108EBF
0x180108eab  mov     r9d, esi; int
0x180108eae  mov     r8d, 282h; int
0x180108eb4  mov     rdx, rbx; char *
0x180108eb7  mov     rcx, rax; this
0x180108eba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180108ebf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180108ec6  jb      loc_180109AB2
0x180108ecc  mov     edx, 6Bh ; 'k'
0x180108ed1  jmp     loc_180109A98
0x180108ed6  lea     rdx, [rsp+160h+var_110]
0x180108edb  lea     rcx, [rsp+160h+var_128]
0x180108ee0  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180108ee5  mov     esi, eax
0x180108ee7  test    eax, eax
0x180108ee9  jns     loc_180108F7A
0x180108eef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180108ef6  test    rcx, rcx
0x180108ef9  jnz     short loc_180108F3C
0x180108efb  mov     rax, cs:stru_1801FC290.__vftable
0x180108f02  lea     r8, stru_1801FC290
0x180108f09  mov     edx, 7F0h
0x180108f0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180108f15  mov     rcx, r8
0x180108f18  mov     rax, [rax+8]
0x180108f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108f21  test    eax, eax
0x180108f23  jnz     short loc_180108F35
0x180108f25  lea     rcx, stru_1801F8A30
0x180108f2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180108f33  jmp     short loc_180108F3C
0x180108f35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180108f3c  cmp     [rcx+8], r12b
0x180108f40  jz      short loc_180108F63
0x180108f42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180108f47  cmp     [rax+7CCh], esi
0x180108f4d  jz      short loc_180108F63
0x180108f4f  mov     r9d, esi; int
0x180108f52  mov     r8d, 283h; int
0x180108f58  mov     rdx, rbx; char *
0x180108f5b  mov     rcx, rax; this
0x180108f5e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180108f63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
