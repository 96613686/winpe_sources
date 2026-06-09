# RendererEffectWrapper::ConnectToAppService(ushort *,int)

- ea: `0x1800444ec`
- end: `0x18004510c`
- name: `?ConnectToAppService@RendererEffectWrapper@@QEAAJPEAGH@Z`
- size: `3104`
- prototype: `__int64 __fastcall(RendererEffectWrapper *__hidden this, PCNZWCH sourceString, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800300ac`
- `0x1800b4210`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001b3c4`
- `0x180025b08`
- `0x180027338`
- `0x1800282cc`
- `0x18003639c`
- `0x1800364d0`
- `0x180041c9c`
- `0x1800444ec`
- `0x180045114`
- `0x180045184`
- `0x1800451c4`
- `0x180054140`
- `0x1800b2df8`
- `0x1800b2f2c`
- `0x1800b2fc4`
- `0x1800b3190`
- `0x1800b3270`
- `0x1800b3404`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18004487f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18004487f`
- `api-ms-win-appmodel-runtime-l1-1-2!AppPolicyGetWindowingModel` at `0x180044b68`
- `api-ms-win-appmodel-runtime-l1-1-2!AppPolicyGetWindowingModel` at `0x180044b68`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x1800446ba`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x1800446ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004458e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800446d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800447c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004489f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004494c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800449f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ad3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044c73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044d55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044f99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004458e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800446d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800447c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004489f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004494c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800449f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ad3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044c73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044d55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044f99`

## string_xrefs

- `0x180044519`: `RendererEffectWrapper::ConnectToAppService`
- `0x18004481f`: `RendererEffectWrapper::ConnectToAppService`
- `0x1800448f6`: `RendererEffectWrapper::ConnectToAppService`
- `0x1800449a3`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044a50`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044b2a`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044c08`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044cca`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044dac`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044efa`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044ff0`: `RendererEffectWrapper::ConnectToAppService`
- `0x180044864`: `Windows.ApplicationModel.AppService.AppServiceConnection`

## pseudocode

```c
__int64 __fastcall RendererEffectWrapper::ConnectToAppService(
        RendererEffectWrapper *this,
        PCNZWCH sourceString,
        int a3)
{
  unsigned int *v6; // r8
  int AssociatedAppFamilyName; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  _QWORD *v19; // r12
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64, __int64, char *); // rbx
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v40)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 (__fastcall *v44)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, GUID *, __int64 *); // rbx
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdi
  void (__fastcall ***v55)(_QWORD, GUID *, char *); // rsi
  void (__fastcall *v56)(_QWORD, GUID *, char *); // rbx
  __int64 v57; // rbx
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rax
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdi
  __int64 v69; // [rsp+30h] [rbp-59h] BYREF
  AppPolicyWindowingModel policy[2]; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v71[8]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v72; // [rsp+48h] [rbp-41h] BYREF
  HSTRING string; // [rsp+50h] [rbp-39h] BYREF
  __int64 v74; // [rsp+58h] [rbp-31h] BYREF
  PCNZWCH sourceStringa; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v76[2]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v77; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v79; // [rsp+98h] [rbp+Fh]

  v77 = 0;
  v74 = 0;
  v72 = 0;
  sourceStringa = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v71,
    "RendererEffectWrapper::ConnectToAppService",
    817);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved1 = &sourceStringa;
  hstringHeader.Reserved.Reserved2[16] = 1;
  AssociatedAppFamilyName = RendererEffectWrapper::GetAssociatedAppFamilyName(
                              this,
                              (unsigned __int16 **)&hstringHeader.Reserved.Reserved2[8],
                              v6);
  wil::details::out_param_ptr_t<unsigned short * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_ptr_t<unsigned short * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
  if ( AssociatedAppFamilyName < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != AssociatedAppFamilyName )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "RendererEffectWrapper::ConnectToAppService",
          817,
          AssociatedAppFamilyName);
    }
    if ( g_wppLevels )
    {
      v11 = 93;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
        this,
        AssociatedAppFamilyName);
      goto LABEL_156;
    }
    goto LABEL_156;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 94, &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids, this);
  v69 = 0;
  *(_QWORD *)policy = 0;
  v12 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
          &string,
          sourceString);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(
    &v69,
    v12);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  v13 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
          &string,
          sourceStringa);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(
    policy,
    v13);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  if ( a3 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    AssociatedAppFamilyName = GetMediaExtensionCommunicationFactory(&v74);
    if ( AssociatedAppFamilyName < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v16,
            "RendererEffectWrapper::ConnectToAppService",
            828,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
        goto LABEL_28;
      v17 = 95;
LABEL_27:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
        this,
        AssociatedAppFamilyName);
LABEL_28:
      Windows::Internal::String::~String((Windows::Internal::String *)policy);
      Windows::Internal::String::~String((Windows::Internal::String *)&v69);
      goto LABEL_156;
    }
    v18 = v74;
    v19 = (_QWORD *)((char *)this + 200);
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, char *))(*(_QWORD *)v74 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 200);
    LOBYTE(v21) = 1;
    AssociatedAppFamilyName = v20(v18, *(_QWORD *)policy, v69, v21, (char *)this + 200);
    if ( AssociatedAppFamilyName < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v24,
            "RendererEffectWrapper::ConnectToAppService",
            834,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
        goto LABEL_28;
      v17 = 96;
      goto LABEL_27;
    }
  }
  else
  {
    v19 = (_QWORD *)((char *)this + 200);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 200);
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.AppService.AppServiceConnection",
      0x39u,
      0x38u);
    AssociatedAppFamilyName = RoActivateInstance(v79, (char *)this + 200);
    if ( AssociatedAppFamilyName < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      v79 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v27,
            "RendererEffectWrapper::ConnectToAppService",
            838,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
        goto LABEL_28;
      v17 = 97;
      goto LABEL_27;
    }
    AssociatedAppFamilyName = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v19 + 56LL))(*v19, v69);
    if ( AssociatedAppFamilyName < 0 )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v30,
            "RendererEffectWrapper::ConnectToAppService",
            839,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
        goto LABEL_28;
      v17 = 98;
      goto LABEL_27;
    }
    AssociatedAppFamilyName = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v19 + 72LL))(
                                *v19,
                                *(_QWORD *)policy);
    if ( AssociatedAppFamilyName < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v33,
            "RendererEffectWrapper::ConnectToAppService",
            840,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
        goto LABEL_28;
      v17 = 99;
      goto LABEL_27;
    }
  }
  Windows::Internal::String::~String((Windows::Internal::String *)policy);
  Windows::Internal::String::~String((Windows::Internal::String *)&v69);
  if ( !a3 )
  {
    policy[0] = AppPolicyWindowingModel_None;
    AppPolicyGetWindowingModel((HANDLE)0xFFFFFFFFFFFFFFFALL, policy);
    v39 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v19;
    if ( policy[0] == AppPolicyWindowingModel_Universal )
    {
      v40 = (*v39)[10];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      AssociatedAppFamilyName = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v40)(
                                  v39,
                                  &v72);
      if ( AssociatedAppFamilyName < 0 )
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != AssociatedAppFamilyName )
            CallStackContext::TraceFailure(
              v43,
              "RendererEffectWrapper::ConnectToAppService",
              853,
              AssociatedAppFamilyName);
        }
        if ( g_wppLevels )
        {
          v11 = 101;
          goto LABEL_12;
        }
        goto LABEL_156;
      }
LABEL_122:
      v54 = *v19;
      *(_QWORD *)policy = v54;
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
      if ( !*((_QWORD *)this + 23) )
      {
        v55 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 19);
        v56 = **v55;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 184);
        v56(v55, &GUID_604d33d7_cf23_41d5_8224_5bbbb1a87475, (char *)this + 184);
      }
      v69 = *((_QWORD *)this + 23);
      v57 = v69;
      Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(&v69);
      v76[0] = v57;
      Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(v76);
      v76[1] = v54;
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
      AssociatedAppFamilyName = StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus__Windows::Foundation::IAsyncOperation_enum_Windows::ApplicationModel::AppService::AppServiceConnectionStatus___lambda_333a8c70c04fe2d5e5b64a58284e33ae___(
                                  v72,
                                  v76);
      lambda_333a8c70c04fe2d5e5b64a58284e33ae_::__lambda_333a8c70c04fe2d5e5b64a58284e33ae_(v76);
      if ( AssociatedAppFamilyName >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(policy);
        v61 = *(_QWORD *)this;
        string = (HSTRING)this;
        (*(void (__fastcall **)(RendererEffectWrapper *))(v61 + 8))(this);
        v69 = 0;
        AssociatedAppFamilyName = Microsoft::WRL::AsWeak<IInspectable>(this, &v69);
        if ( AssociatedAppFamilyName >= 0 )
        {
          v65 = lambda_2cba588fe41229ebb1a536b1086f2b76_::_lambda_2cba588fe41229ebb1a536b1086f2b76_(
                  &hstringHeader,
                  &v69,
                  this);
          Microsoft::WRL::Callback_Windows::Foundation::ITypedEventHandler_Windows::ApplicationModel::AppService::AppServiceConnection___Windows::ApplicationModel::AppService::AppServiceClosedEventArgs_____lambda_2cba588fe41229ebb1a536b1086f2b76___(
            v76,
            v65);
          lambda_2cba588fe41229ebb1a536b1086f2b76_::__lambda_2cba588fe41229ebb1a536b1086f2b76_(&hstringHeader);
          v66 = *v19;
          v67 = v76[0];
          *(_QWORD *)policy = 0;
          AssociatedAppFamilyName = (*(__int64 (__fastcall **)(__int64, _QWORD, AppPolicyWindowingModel *))(*(_QWORD *)v66 + 112LL))(
                                      v66,
                                      v76[0],
                                      policy);
          *((_QWORD *)this + 90) = *(_QWORD *)policy;
          if ( v67 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
        }
        else
        {
          v62 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v63;
            if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
            {
              v62 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v62 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v62 + 8) )
          {
            v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
            if ( *((_DWORD *)v64 + 499) != AssociatedAppFamilyName )
              CallStackContext::TraceFailure(
                v64,
                "RendererEffectWrapper::ConnectToAppService",
                887,
                AssociatedAppFamilyName);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              105,
              &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
              this,
              AssociatedAppFamilyName);
        }
        if ( v69 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      }
      else
      {
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v59;
          if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
          {
            v58 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v58 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
          if ( *((_DWORD *)v60 + 499) != AssociatedAppFamilyName )
            CallStackContext::TraceFailure(
              v60,
              "RendererEffectWrapper::ConnectToAppService",
              880,
              AssociatedAppFamilyName);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            104,
            &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
            this,
            AssociatedAppFamilyName);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(policy);
      }
      goto LABEL_156;
    }
    v69 = 0;
    v44 = **v39;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    AssociatedAppFamilyName = v44(v39, &GUID_65219584_f9cb_4ae3_81f9_a28a6ca450d9, &v69);
    if ( AssociatedAppFamilyName >= 0 )
    {
      v49 = v69;
      v50 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v69 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      AssociatedAppFamilyName = v50(v49, &GUID_0d0e6663_2639_5a9a_9cbc_30d7d4ce533b, &v72);
      if ( AssociatedAppFamilyName >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        goto LABEL_122;
      }
      v51 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v52;
        if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
        {
          v51 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v51 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
        if ( *((_DWORD *)v53 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v53,
            "RendererEffectWrapper::ConnectToAppService",
            859,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
      {
LABEL_109:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        goto LABEL_156;
      }
      v48 = 103;
    }
    else
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != AssociatedAppFamilyName )
          CallStackContext::TraceFailure(
            v47,
            "RendererEffectWrapper::ConnectToAppService",
            858,
            AssociatedAppFamilyName);
      }
      if ( !g_wppLevels )
        goto LABEL_109;
      v48 = 102;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v48,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      this,
      AssociatedAppFamilyName);
    goto LABEL_109;
  }
  v34 = v74;
  v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v74 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  AssociatedAppFamilyName = v35(v34, *v19, &v72);
  if ( AssociatedAppFamilyName >= 0 )
    goto LABEL_122;
  v36 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v37;
    if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v36 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v36 + 8) )
  {
    v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
    if ( *((_DWORD *)v38 + 499) != AssociatedAppFamilyName )
      CallStackContext::TraceFailure(v38, "RendererEffectWrapper::ConnectToAppService", 849, AssociatedAppFamilyName);
  }
  if ( g_wppLevels )
  {
    v11 = 100;
    goto LABEL_12;
  }
LABEL_156:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v71);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceStringa);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
  return (unsigned int)AssociatedAppFamilyName;
}

```

## disassembly

```asm
0x1800444ec  mov     [rsp-8+arg_10], rbx
0x1800444f1  push    rbp
0x1800444f2  push    rsi
0x1800444f3  push    rdi
0x1800444f4  push    r12
0x1800444f6  push    r13
0x1800444f8  push    r14
0x1800444fa  push    r15
0x1800444fc  lea     rbp, [rsp-27h]
0x180044501  sub     rsp, 0B0h
0x180044508  mov     rax, cs:__security_cookie
0x18004450f  xor     rax, rsp
0x180044512  mov     [rbp+57h+var_40], rax
0x180044516  xor     r13d, r13d
0x180044519  lea     r12, aRenderereffect_2; "RendererEffectWrapper::ConnectToAppServ"...
0x180044520  mov     esi, r8d
0x180044523  mov     [rbp+57h+var_68], r13
0x180044527  mov     rdi, rdx
0x18004452a  mov     [rbp+57h+var_88], r13
0x18004452e  mov     r14, rcx
0x180044531  mov     [rbp+57h+var_98], r13
0x180044535  mov     r15d, 331h
0x18004453b  mov     [rbp+57h+sourceString], r13
0x18004453f  mov     r8d, r15d; int
0x180044542  lea     rcx, [rbp+57h+var_A0]; this
0x180044546  mov     rdx, r12; char *
0x180044549  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004454e  lea     rax, [rbp+57h+sourceString]
0x180044552  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180044556  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]; unsigned __int16 **
0x18004455a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18004455e  mov     rcx, r14; this
0x180044561  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180044565  call    ?GetAssociatedAppFamilyName@RendererEffectWrapper@@QEAAJPEAPEAGPEAI@Z; RendererEffectWrapper::GetAssociatedAppFamilyName(ushort * *,uint *)
0x18004456a  lea     rcx, [rbp+57h+hstringHeader]
0x18004456e  mov     ebx, eax
0x180044570  call    ??1?$out_param_ptr_t@PEAPEAGV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_ptr_t<ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180044575  mov     eax, ebx
0x180044577  shr     eax, 1Fh
0x18004457a  test    al, al
0x18004457c  jz      loc_18004462C
0x180044582  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044589  test    rcx, rcx
0x18004458c  jnz     short loc_1800445CF
0x18004458e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044594  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004459b  mov     rcx, rax
0x18004459e  test    rax, rax
0x1800445a1  jz      short loc_1800445C1
0x1800445a3  mov     rax, [rax]
0x1800445a6  mov     edx, 7F0h
0x1800445ab  mov     rax, [rax+8]
0x1800445af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b4  test    eax, eax
0x1800445b6  jz      short loc_1800445C1
0x1800445b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800445bf  jmp     short loc_1800445CF
0x1800445c1  lea     rcx, qword_180153440; this
0x1800445c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800445cf  cmp     [rcx+8], r13b
0x1800445d3  jz      short loc_1800445F7
0x1800445d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800445da  test    ebx, ebx
0x1800445dc  jns     short loc_1800445F7
0x1800445de  cmp     [rax+7CCh], ebx
0x1800445e4  jz      short loc_1800445F7
0x1800445e6  mov     r9d, ebx; int
0x1800445e9  mov     r8d, r15d; int
0x1800445ec  mov     rdx, r12; char *
0x1800445ef  mov     rcx, rax; this
0x1800445f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800445f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800445fe  jb      loc_1800450B6
0x180044604  mov     edx, 5Dh ; ']'
0x180044609  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x180044610  mov     rcx, cs:WPP_GLOBAL_Control
0x180044617  mov     r9, r14
0x18004461a  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18004461e  mov     rcx, [rcx+10h]
0x180044622  call    WPP_SF_qD
0x180044627  jmp     loc_1800450B6
0x18004462c  cmp     cs:byte_180153DE0, 10h
0x180044633  lea     r15, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x18004463a  jb      short loc_18004465A
0x18004463c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044643  mov     edx, 5Eh ; '^'
0x180044648  mov     r9, r14
0x18004464b  mov     r8, r15
0x18004464e  mov     rcx, [rcx+150h]
0x180044655  call    WPP_SF_q
0x18004465a  mov     rdx, rdi; sourceString
0x18004465d  mov     [rbp+57h+var_B0], r13
0x180044661  lea     rcx, [rbp+57h+string]; string
0x180044665  mov     qword ptr [rbp+57h+policy], r13
0x180044669  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004466e  mov     rdx, rax
0x180044671  lea     rcx, [rbp+57h+var_B0]
0x180044675  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x18004467a  lea     rcx, [rbp+57h+string]; this
0x18004467e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044683  mov     rdx, [rbp+57h+sourceString]; sourceString
0x180044687  lea     rcx, [rbp+57h+string]; string
0x18004468b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180044690  mov     rdx, rax
0x180044693  lea     rcx, [rbp+57h+policy]
0x180044697  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x18004469c  lea     rcx, [rbp+57h+string]; this
0x1800446a0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800446a5  test    esi, esi
0x1800446a7  jz      loc_18004484B
0x1800446ad  lea     rcx, [rbp+57h+var_88]
0x1800446b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800446b6  lea     rcx, [rbp+57h+var_88]
0x1800446ba  call    cs:__imp_GetMediaExtensionCommunicationFactory
0x1800446c0  mov     ebx, eax
0x1800446c2  test    eax, eax
0x1800446c4  jns     loc_18004477D
0x1800446ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800446d1  test    rcx, rcx
0x1800446d4  jnz     short loc_180044717
0x1800446d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800446dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800446e3  mov     rcx, rax
0x1800446e6  test    rax, rax
0x1800446e9  jz      short loc_180044709
0x1800446eb  mov     rax, [rax]
0x1800446ee  mov     edx, 7F0h
0x1800446f3  mov     rax, [rax+8]
0x1800446f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446fc  test    eax, eax
0x1800446fe  jz      short loc_180044709
0x180044700  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044707  jmp     short loc_180044717
0x180044709  lea     rcx, qword_180153440; this
0x180044710  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044717  cmp     [rcx+8], r13b
0x18004471b  jz      short loc_18004473E
0x18004471d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044722  cmp     [rax+7CCh], ebx
0x180044728  jz      short loc_18004473E
0x18004472a  mov     r9d, ebx; int
0x18004472d  mov     r8d, 33Ch; int
0x180044733  mov     rdx, r12; char *
0x180044736  mov     rcx, rax; this
0x180044739  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004473e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044745  jb      short loc_180044766
0x180044747  mov     edx, 5Fh ; '_'
0x18004474c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044753  mov     r9, r14
0x180044756  mov     r8, r15
0x180044759  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18004475d  mov     rcx, [rcx+10h]
0x180044761  call    WPP_SF_qD
0x180044766  lea     rcx, [rbp+57h+policy]; this
0x18004476a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004476f  lea     rcx, [rbp+57h+var_B0]; this
0x180044773  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044778  jmp     loc_1800450B6
0x18004477d  mov     rdi, [rbp+57h+var_88]
0x180044781  lea     r12, [r14+0C8h]
0x180044788  mov     rcx, r12
0x18004478b  mov     rax, [rdi]
0x18004478e  mov     rbx, [rax+48h]
0x180044792  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044797  mov     r8, [rbp+57h+var_B0]
0x18004479b  mov     r9b, 1
0x18004479e  mov     rdx, qword ptr [rbp+57h+policy]
0x1800447a2  mov     rcx, rdi
0x1800447a5  mov     rax, rbx
0x1800447a8  mov     [rsp+0E0h+var_C0], r12
0x1800447ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447b2  mov     ebx, eax
0x1800447b4  test    eax, eax
0x1800447b6  jns     loc_180044A7C
0x1800447bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800447c3  test    rcx, rcx
0x1800447c6  jnz     short loc_180044809
0x1800447c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800447ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800447d5  mov     rcx, rax
0x1800447d8  test    rax, rax
0x1800447db  jz      short loc_1800447FB
0x1800447dd  mov     rax, [rax]
0x1800447e0  mov     edx, 7F0h
0x1800447e5  mov     rax, [rax+8]
0x1800447e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447ee  test    eax, eax
0x1800447f0  jz      short loc_1800447FB
0x1800447f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800447f9  jmp     short loc_180044809
0x1800447fb  lea     rcx, qword_180153440; this
0x180044802  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044809  cmp     [rcx+8], r13b
0x18004480d  jz      short loc_180044834
0x18004480f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044814  cmp     [rax+7CCh], ebx
0x18004481a  jz      short loc_180044834
0x18004481c  mov     r9d, ebx; int
0x18004481f  lea     rdx, aRenderereffect_2; "RendererEffectWrapper::ConnectToAppServ"...
0x180044826  mov     r8d, 342h; int
0x18004482c  mov     rcx, rax; this
0x18004482f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044834  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004483b  jb      loc_180044766
0x180044841  mov     edx, 60h ; '`'
0x180044846  jmp     loc_18004474C
0x18004484b  lea     r12, [r14+0C8h]
0x180044852  mov     rcx, r12
0x180044855  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004485a  mov     r9d, 38h ; '8'; unsigned int
0x180044860  mov     [rbp+57h+var_48], r13
0x180044864  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; "Windows.ApplicationModel.AppService.App"...
0x18004486b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004486f  lea     r8d, [r9+1]; unsigned int
0x180044873  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180044878  mov     rcx, [rbp+57h+var_48]
0x18004487c  mov     rdx, r12
0x18004487f  call    cs:__imp_RoActivateInstance
0x180044885  mov     ebx, eax
0x180044887  test    eax, eax
0x180044889  jns     loc_180044922
0x18004488f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044896  mov     [rbp+57h+var_48], r13
0x18004489a  test    rcx, rcx
0x18004489d  jnz     short loc_1800448E0
0x18004489f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800448a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448ac  mov     rcx, rax
0x1800448af  test    rax, rax
0x1800448b2  jz      short loc_1800448D2
0x1800448b4  mov     rax, [rax]
0x1800448b7  mov     edx, 7F0h
0x1800448bc  mov     rax, [rax+8]
0x1800448c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448c5  test    eax, eax
0x1800448c7  jz      short loc_1800448D2
0x1800448c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448d0  jmp     short loc_1800448E0
0x1800448d2  lea     rcx, qword_180153440; this
0x1800448d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448e0  cmp     [rcx+8], r13b
0x1800448e4  jz      short loc_18004490B
0x1800448e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800448eb  cmp     [rax+7CCh], ebx
0x1800448f1  jz      short loc_18004490B
0x1800448f3  mov     r9d, ebx; int
0x1800448f6  lea     rdx, aRenderereffect_2; "RendererEffectWrapper::ConnectToAppServ"...
0x1800448fd  mov     r8d, 346h; int
0x180044903  mov     rcx, rax; this
0x180044906  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004490b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044912  jb      loc_180044766
0x180044918  mov     edx, 61h ; 'a'
0x18004491d  jmp     loc_18004474C
0x180044922  mov     rcx, [r12]
0x180044926  mov     rdx, [rbp+57h+var_B0]
0x18004492a  mov     rax, [rcx]
0x18004492d  mov     rax, [rax+38h]
0x180044931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044936  mov     ebx, eax
0x180044938  test    eax, eax
0x18004493a  jns     loc_1800449CF
0x180044940  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044947  test    rcx, rcx
0x18004494a  jnz     short loc_18004498D
0x18004494c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044952  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044959  mov     rcx, rax
0x18004495c  test    rax, rax
0x18004495f  jz      short loc_18004497F
0x180044961  mov     rax, [rax]
0x180044964  mov     edx, 7F0h
0x180044969  mov     rax, [rax+8]
0x18004496d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044972  test    eax, eax
0x180044974  jz      short loc_18004497F
0x180044976  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004497d  jmp     short loc_18004498D
0x18004497f  lea     rcx, qword_180153440; this
0x180044986  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004498d  cmp     [rcx+8], r13b
0x180044991  jz      short loc_1800449B8
0x180044993  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044998  cmp     [rax+7CCh], ebx
0x18004499e  jz      short loc_1800449B8
0x1800449a0  mov     r9d, ebx; int
0x1800449a3  lea     rdx, aRenderereffect_2; "RendererEffectWrapper::ConnectToAppServ"...
0x1800449aa  mov     r8d, 347h; int
0x1800449b0  mov     rcx, rax; this
0x1800449b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800449b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800449bf  jb      loc_180044766
0x1800449c5  mov     edx, 62h ; 'b'
0x1800449ca  jmp     loc_18004474C
0x1800449cf  mov     rcx, [r12]
0x1800449d3  mov     rdx, qword ptr [rbp+57h+policy]
0x1800449d7  mov     rax, [rcx]
0x1800449da  mov     rax, [rax+48h]
0x1800449de  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
