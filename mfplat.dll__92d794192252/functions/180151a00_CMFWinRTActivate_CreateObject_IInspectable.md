# CMFWinRTActivate::_CreateObject(IInspectable * *)

- ea: `0x180151a00`
- end: `0x180152364`
- name: `?_CreateObject@CMFWinRTActivate@@AEAAJPEAPEAUIInspectable@@@Z`
- size: `2404`
- prototype: `__int64 __fastcall(struct IMFTransform *this, struct IInspectable **)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d9c80`
- `0x18014c430`

## callees

- `0x180004870`
- `0x180011480`
- `0x18001fce4`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004c634`
- `0x1800a0ac0`
- `0x1800ad378`
- `0x1801200d0`
- `0x180121575`
- `0x18014bf60`
- `0x18014bfac`
- `0x180151a00`
- `0x1801523f0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801522ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801522ed`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180151c4f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180151dfb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180151c4f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180151dfb`

## string_xrefs

- `0x180151dd1`: `Windows.Media.Effects.BasicVideoEffectMediaExtensionWrapper`
- `0x180151c25`: `Windows.Media.Effects.BasicAudioEffectMediaExtensionWrapper`
- `0x180151a2d`: `CMFWinRTActivate::_CreateObject`

## pseudocode

```c
__int64 __fastcall CMFWinRTActivate::_CreateObject(struct IMFTransform *this, struct IInspectable **a2)
{
  struct IMFTransformVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetInputAvailableType)(IMFTransform *, DWORD, DWORD, IMFMediaType **); // rax
  int ActivationFactory; // esi
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  struct IInspectable *v12; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  __int64 v14; // rbx
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, __int64 *); // rbx
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  struct IInspectable *v21; // rbx
  HRESULT (__fastcall *v22)(IUnknown *, const _GUID *, void **); // rdi
  __int64 v23; // rbx
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, __int64 *); // rbx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  __int64 v30; // rcx
  struct IInspectable *v31; // rbx
  HRESULT (__fastcall *v32)(IUnknown *, const _GUID *, void **); // rdi
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  int v37; // edx
  int v38; // r8d
  struct IMFAttributes *v39; // r8
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  char v45; // al
  CallStackScopeTrace v47; // [rsp+30h] [rbp-69h] BYREF
  __int64 v48; // [rsp+38h] [rbp-61h] BYREF
  struct IInspectable *v49; // [rsp+40h] [rbp-59h] BYREF
  struct IMFMediaType *v50; // [rsp+48h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-49h] BYREF
  __int64 v52; // [rsp+58h] [rbp-41h] BYREF
  __int64 v53; // [rsp+60h] [rbp-39h] BYREF
  __int64 v54; // [rsp+68h] [rbp-31h] BYREF
  __int64 v55; // [rsp+70h] [rbp-29h] BYREF
  void *v56; // [rsp+78h] [rbp-21h] BYREF
  int v57; // [rsp+80h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+88h] [rbp-11h] BYREF
  Windows::Internal::StringReference v59; // [rsp+98h] [rbp-1h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v47, "CMFWinRTActivate::_CreateObject", 462);
  *a2 = 0;
  lpVtbl = this->lpVtbl;
  pv = 0;
  v57 = 0;
  v49 = 0;
  GetInputAvailableType = lpVtbl->GetInputAvailableType;
  v56 = 0;
  Buf1 = 0;
  v48 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v52 = 0;
  ActivationFactory = ((__int64 (__fastcall *)(struct IMFTransform *, __int64 *, LPVOID *, int *))GetInputAvailableType)(
                        this,
                        MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID,
                        &pv,
                        &v57);
  if ( ActivationFactory < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( ThreadRelativeContext->m_result != ActivationFactory )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFWinRTActivate::_CreateObject", 479, ActivationFactory);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 57;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
        this,
        ActivationFactory);
      goto LABEL_116;
    }
    goto LABEL_116;
  }
  Windows::Internal::StringReference::_ConstructorHelper(&v59, (const unsigned __int16 *)pv);
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IInspectable>>(v59._hstring, &v49);
  if ( ActivationFactory >= 0 )
  {
    v12 = v49;
    QueryInterface = v49->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    if ( QueryInterface(v12, &GUID_8c062c53_6bc0_48b8_a99a_4b41550f1359, (void **)&v55) < 0 )
    {
      v21 = v49;
      v22 = v49->QueryInterface;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      if ( v22(v21, &GUID_8262c7ef_b360_40be_949b_2ff42ff35693, (void **)&v54) < 0 )
        goto LABEL_65;
      v23 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                         &v59._hstring,
                         L"Windows.Media.Effects.BasicVideoEffectMediaExtensionWrapper");
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      ActivationFactory = RoGetActivationFactory(v23, &GUID_fb8471b9_91dc_465c_b1e7_89ab34ddd8e3, &v52);
      if ( ActivationFactory < 0 )
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
          if ( v25->m_result != ActivationFactory )
            CallStackContext::TraceFailure(v25, "CMFWinRTActivate::_CreateObject", 505, ActivationFactory);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 61;
          goto LABEL_11;
        }
        goto LABEL_116;
      }
      v26 = v52;
      v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v52 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      ActivationFactory = v27(v26, v54, &v48);
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
            CallStackContext::TraceFailure(v29, "CMFWinRTActivate::_CreateObject", 506, ActivationFactory);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 62;
          goto LABEL_11;
        }
        goto LABEL_116;
      }
    }
    else
    {
      v14 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                         &v59._hstring,
                         L"Windows.Media.Effects.BasicAudioEffectMediaExtensionWrapper");
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      ActivationFactory = RoGetActivationFactory(v14, &GUID_f72124a3_03fb_49ef_9009_6d214a5c3740, &v53);
      if ( ActivationFactory < 0 )
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
          if ( v16->m_result != ActivationFactory )
            CallStackContext::TraceFailure(v16, "CMFWinRTActivate::_CreateObject", 496, ActivationFactory);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 59;
          goto LABEL_11;
        }
        goto LABEL_116;
      }
      v17 = v53;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      ActivationFactory = v18(v17, v55, &v48);
      if ( ActivationFactory < 0 )
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
          if ( v20->m_result != ActivationFactory )
            CallStackContext::TraceFailure(v20, "CMFWinRTActivate::_CreateObject", 497, ActivationFactory);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 60;
          goto LABEL_11;
        }
        goto LABEL_116;
      }
    }
    Microsoft::WRL::ComPtr<IInspectable>::operator=<Windows::Media::IMediaExtension>(&v49, &v48);
LABEL_65:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v56);
    if ( (int)CGITPtr::Get((CGITPtr *)&this[19], &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v56) >= 0 )
    {
      v30 = v48;
      if ( !v48 )
      {
        v31 = v49;
        v32 = v49->QueryInterface;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        ActivationFactory = v32(v31, &GUID_07915118_45df_442b_8a3f_f7826a6370ab, (void **)&v48);
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
              CallStackContext::TraceFailure(v34, "CMFWinRTActivate::_CreateObject", 516, ActivationFactory);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v9 = 63;
            goto LABEL_11;
          }
          goto LABEL_116;
        }
        v30 = v48;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v30 + 48LL))(v30, v56);
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
            CallStackContext::TraceFailure(v36, "CMFWinRTActivate::_CreateObject", 518, ActivationFactory);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 64;
          goto LABEL_11;
        }
        goto LABEL_116;
      }
    }
    if ( !((unsigned int (__fastcall *)(struct IMFTransform *, const GUID *, __int128 *))this->lpVtbl->GetOutputStreamAttributes)(
            this,
            &MF_TRANSFORM_CATEGORY_Attribute,
            &Buf1)
      && (!memcmp_0(&Buf1, &MFT_CATEGORY_AUDIO_ENCODER, 0x10u) || !memcmp_0(&Buf1, &MFT_CATEGORY_VIDEO_ENCODER, 0x10u)) )
    {
      v50 = 0;
      ActivationFactory = Microsoft::WRL::ComPtr<IInspectable>::As<IMFTransform>(&v49, &v50);
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
            CallStackContext::TraceFailure(v41, "CMFWinRTActivate::_CreateObject", 527, ActivationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_102;
        v42 = 65;
LABEL_101:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
          this,
          ActivationFactory);
LABEL_102:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v50);
        goto LABEL_116;
      }
      ActivationFactory = MFTActivateHelper::ConfigureEncoderFromActivateAttributes(v50, this, v39);
      if ( ActivationFactory < 0 )
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
          if ( v44->m_result != ActivationFactory )
            CallStackContext::TraceFailure(v44, "CMFWinRTActivate::_CreateObject", 529, ActivationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_102;
        v42 = 66;
        goto LABEL_101;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v50);
    }
    v45 = (char)v49;
    *a2 = v49;
    v49 = 0;
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_qSq(*((_QWORD *)WPP_GLOBAL_Control + 7), v37, v38, (_DWORD)this, (__int64)pv, v45);
    goto LABEL_116;
  }
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
    if ( v11->m_result != ActivationFactory )
      CallStackContext::TraceFailure(v11, "CMFWinRTActivate::_CreateObject", 482, ActivationFactory);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v9 = 58;
    goto LABEL_11;
  }
LABEL_116:
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v49);
  CallStackScopeTrace::~CallStackScopeTrace(&v47);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180151a00  mov     [rsp-8+arg_10], rbx
0x180151a05  push    rbp
0x180151a06  push    rsi
0x180151a07  push    rdi
0x180151a08  push    r12
0x180151a0a  push    r13
0x180151a0c  push    r14
0x180151a0e  push    r15
0x180151a10  lea     rbp, [rsp-27h]
0x180151a15  sub     rsp, 0C0h
0x180151a1c  mov     rax, cs:__security_cookie
0x180151a23  xor     rax, rsp
0x180151a26  mov     [rbp+57h+var_38], rax
0x180151a2a  mov     r15, rdx
0x180151a2d  lea     r13, aCmfwinrtactiva_3; "CMFWinRTActivate::_CreateObject"
0x180151a34  mov     r14, rcx
0x180151a37  mov     rdx, r13; char *
0x180151a3a  mov     r8d, 1CEh; int
0x180151a40  lea     rcx, [rbp+57h+var_C0]; this
0x180151a44  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180151a49  xor     r12d, r12d
0x180151a4c  lea     r9, [rbp+57h+var_70]
0x180151a50  mov     [r15], r12
0x180151a53  lea     r8, [rbp+57h+pv]
0x180151a57  mov     rax, [r14]
0x180151a5a  lea     rdx, MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID
0x180151a61  xorps   xmm0, xmm0
0x180151a64  mov     [rbp+57h+pv], r12
0x180151a68  mov     rcx, r14
0x180151a6b  mov     [rbp+57h+var_70], r12d
0x180151a6f  mov     [rbp+57h+var_B0], r12
0x180151a73  mov     rax, [rax+68h]
0x180151a77  mov     [rbp+57h+var_78], r12
0x180151a7b  movups  [rbp+57h+Buf1], xmm0
0x180151a7f  mov     [rbp+57h+var_B8], r12
0x180151a83  mov     [rbp+57h+var_80], r12
0x180151a87  mov     [rbp+57h+var_88], r12
0x180151a8b  mov     [rbp+57h+var_90], r12
0x180151a8f  mov     [rbp+57h+var_98], r12
0x180151a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151a98  mov     esi, eax
0x180151a9a  test    eax, eax
0x180151a9c  jns     loc_180151B48
0x180151aa2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180151aa9  test    rcx, rcx
0x180151aac  jnz     short loc_180151AEC
0x180151aae  mov     rax, cs:stru_1801FC290.__vftable
0x180151ab5  lea     rcx, stru_1801FC290
0x180151abc  mov     edx, 7F0h
0x180151ac1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151ac8  mov     rax, [rax+8]
0x180151acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151ad1  test    eax, eax
0x180151ad3  jnz     short loc_180151AE5
0x180151ad5  lea     rcx, stru_1801F8A30
0x180151adc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151ae3  jmp     short loc_180151AEC
0x180151ae5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180151aec  cmp     [rcx+8], r12b
0x180151af0  jz      short loc_180151B13
0x180151af2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180151af7  cmp     [rax+7CCh], esi
0x180151afd  jz      short loc_180151B13
0x180151aff  mov     r9d, esi; int
0x180151b02  mov     r8d, 1DFh; int
0x180151b08  mov     rdx, r13; char *
0x180151b0b  mov     rcx, rax; this
0x180151b0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180151b13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180151b1a  jb      loc_1801522E9
0x180151b20  mov     edx, 39h ; '9'
0x180151b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180151b2c  lea     r8, WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids
0x180151b33  mov     r9, r14
0x180151b36  mov     dword ptr [rsp+0F0h+var_D0], esi
0x180151b3a  mov     rcx, [rcx+10h]
0x180151b3e  call    WPP_SF_qD
0x180151b43  jmp     loc_1801522E9
0x180151b48  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x180151b4c  lea     rcx, [rbp+57h+var_58]; this
0x180151b50  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180151b55  mov     rcx, [rbp+57h+var_58._hstring]
0x180151b59  lea     rdx, [rbp+57h+var_B0]
0x180151b5d  call    ??$ActivateInstance@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IInspectable>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x180151b62  mov     esi, eax
0x180151b64  test    eax, eax
0x180151b66  jns     loc_180151BF4
0x180151b6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180151b73  test    rcx, rcx
0x180151b76  jnz     short loc_180151BB6
0x180151b78  mov     rax, cs:stru_1801FC290.__vftable
0x180151b7f  lea     rcx, stru_1801FC290
0x180151b86  mov     edx, 7F0h
0x180151b8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151b92  mov     rax, [rax+8]
0x180151b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b9b  test    eax, eax
0x180151b9d  jnz     short loc_180151BAF
0x180151b9f  lea     rcx, stru_1801F8A30
0x180151ba6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151bad  jmp     short loc_180151BB6
0x180151baf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180151bb6  cmp     [rcx+8], r12b
0x180151bba  jz      short loc_180151BDD
0x180151bbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180151bc1  cmp     [rax+7CCh], esi
0x180151bc7  jz      short loc_180151BDD
0x180151bc9  mov     r9d, esi; int
0x180151bcc  mov     r8d, 1E2h; int
0x180151bd2  mov     rdx, r13; char *
0x180151bd5  mov     rcx, rax; this
0x180151bd8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180151bdd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180151be4  jb      loc_1801522E9
0x180151bea  mov     edx, 3Ah ; ':'
0x180151bef  jmp     loc_180151B25
0x180151bf4  mov     rbx, [rbp+57h+var_B0]
0x180151bf8  lea     rcx, [rbp+57h+var_80]
0x180151bfc  mov     rax, [rbx]
0x180151bff  mov     rdi, [rax]
0x180151c02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180151c07  lea     r8, [rbp+57h+var_80]
0x180151c0b  mov     rcx, rbx
0x180151c0e  lea     rdx, _GUID_8c062c53_6bc0_48b8_a99a_4b41550f1359
0x180151c15  mov     rax, rdi
0x180151c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151c1d  test    eax, eax
0x180151c1f  js      loc_180151DA0
0x180151c25  lea     rdx, ?RuntimeClass_Windows_Media_Effects_BasicAudioEffectMediaExtensionWrapper@@3QBGB; "Windows.Media.Effects.BasicAudioEffectM"...
0x180151c2c  lea     rcx, [rbp+57h+var_58]; string
0x180151c30  call    ??$?0$0DM@@StringReference@Internal@Windows@@QEAA@AEAY0DM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[60])
0x180151c35  lea     rcx, [rbp+57h+var_90]
0x180151c39  mov     rbx, [rax]
0x180151c3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180151c41  lea     r8, [rbp+57h+var_90]
0x180151c45  mov     rcx, rbx
0x180151c48  lea     rdx, _GUID_f72124a3_03fb_49ef_9009_6d214a5c3740
0x180151c4f  call    cs:__imp_RoGetActivationFactory
0x180151c55  mov     esi, eax
0x180151c57  test    eax, eax
0x180151c59  jns     loc_180151CE7
0x180151c5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180151c66  test    rcx, rcx
0x180151c69  jnz     short loc_180151CA9
0x180151c6b  mov     rax, cs:stru_1801FC290.__vftable
0x180151c72  lea     rcx, stru_1801FC290
0x180151c79  mov     edx, 7F0h
0x180151c7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151c85  mov     rax, [rax+8]
0x180151c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151c8e  test    eax, eax
0x180151c90  jnz     short loc_180151CA2
0x180151c92  lea     rcx, stru_1801F8A30
0x180151c99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151ca0  jmp     short loc_180151CA9
0x180151ca2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180151ca9  cmp     [rcx+8], r12b
0x180151cad  jz      short loc_180151CD0
0x180151caf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180151cb4  cmp     [rax+7CCh], esi
0x180151cba  jz      short loc_180151CD0
0x180151cbc  mov     r9d, esi; int
0x180151cbf  mov     r8d, 1F0h; int
0x180151cc5  mov     rdx, r13; char *
0x180151cc8  mov     rcx, rax; this
0x180151ccb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180151cd0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180151cd7  jb      loc_1801522E9
0x180151cdd  mov     edx, 3Bh ; ';'
0x180151ce2  jmp     loc_180151B25
0x180151ce7  mov     rdi, [rbp+57h+var_90]
0x180151ceb  lea     rcx, [rbp+57h+var_B8]
0x180151cef  mov     rax, [rdi]
0x180151cf2  mov     rbx, [rax+30h]
0x180151cf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180151cfb  mov     rdx, [rbp+57h+var_80]
0x180151cff  lea     r8, [rbp+57h+var_B8]
0x180151d03  mov     rcx, rdi
0x180151d06  mov     rax, rbx
0x180151d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151d0e  mov     esi, eax
0x180151d10  test    eax, eax
0x180151d12  jns     loc_180151F4C
0x180151d18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180151d1f  test    rcx, rcx
0x180151d22  jnz     short loc_180151D62
0x180151d24  mov     rax, cs:stru_1801FC290.__vftable
0x180151d2b  lea     rcx, stru_1801FC290
0x180151d32  mov     edx, 7F0h
0x180151d37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151d3e  mov     rax, [rax+8]
0x180151d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151d47  test    eax, eax
0x180151d49  jnz     short loc_180151D5B
0x180151d4b  lea     rcx, stru_1801F8A30
0x180151d52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151d59  jmp     short loc_180151D62
0x180151d5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180151d62  cmp     [rcx+8], r12b
0x180151d66  jz      short loc_180151D89
0x180151d68  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180151d6d  cmp     [rax+7CCh], esi
0x180151d73  jz      short loc_180151D89
0x180151d75  mov     r9d, esi; int
0x180151d78  mov     r8d, 1F1h; int
0x180151d7e  mov     rdx, r13; char *
0x180151d81  mov     rcx, rax; this
0x180151d84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180151d89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180151d90  jb      loc_1801522E9
0x180151d96  mov     edx, 3Ch ; '<'
0x180151d9b  jmp     loc_180151B25
0x180151da0  mov     rbx, [rbp+57h+var_B0]
0x180151da4  lea     rcx, [rbp+57h+var_88]
0x180151da8  mov     rax, [rbx]
0x180151dab  mov     rdi, [rax]
0x180151dae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180151db3  lea     r8, [rbp+57h+var_88]
0x180151db7  mov     rcx, rbx
0x180151dba  lea     rdx, _GUID_8262c7ef_b360_40be_949b_2ff42ff35693
0x180151dc1  mov     rax, rdi
0x180151dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151dc9  test    eax, eax
0x180151dcb  js      loc_180151F59
0x180151dd1  lea     rdx, ?RuntimeClass_Windows_Media_Effects_BasicVideoEffectMediaExtensionWrapper@@3QBGB; "Windows.Media.Effects.BasicVideoEffectM"...
0x180151dd8  lea     rcx, [rbp+57h+var_58]; string
0x180151ddc  call    ??$?0$0DM@@StringReference@Internal@Windows@@QEAA@AEAY0DM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[60])
0x180151de1  lea     rcx, [rbp+57h+var_98]
0x180151de5  mov     rbx, [rax]
0x180151de8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180151ded  lea     r8, [rbp+57h+var_98]
0x180151df1  mov     rcx, rbx
0x180151df4  lea     rdx, _GUID_fb8471b9_91dc_465c_b1e7_89ab34ddd8e3
0x180151dfb  call    cs:__imp_RoGetActivationFactory
0x180151e01  mov     esi, eax
0x180151e03  test    eax, eax
0x180151e05  jns     loc_180151E93
0x180151e0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180151e12  test    rcx, rcx
0x180151e15  jnz     short loc_180151E55
0x180151e17  mov     rax, cs:stru_1801FC290.__vftable
0x180151e1e  lea     rcx, stru_1801FC290
0x180151e25  mov     edx, 7F0h
0x180151e2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151e31  mov     rax, [rax+8]
0x180151e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151e3a  test    eax, eax
0x180151e3c  jnz     short loc_180151E4E
0x180151e3e  lea     rcx, stru_1801F8A30
0x180151e45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151e4c  jmp     short loc_180151E55
0x180151e4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180151e55  cmp     [rcx+8], r12b
0x180151e59  jz      short loc_180151E7C
0x180151e5b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180151e60  cmp     [rax+7CCh], esi
0x180151e66  jz      short loc_180151E7C
0x180151e68  mov     r9d, esi; int
0x180151e6b  mov     r8d, 1F9h; int
0x180151e71  mov     rdx, r13; char *
0x180151e74  mov     rcx, rax; this
0x180151e77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180151e7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180151e83  jb      loc_1801522E9
0x180151e89  mov     edx, 3Dh ; '='
0x180151e8e  jmp     loc_180151B25
0x180151e93  mov     rdi, [rbp+57h+var_98]
0x180151e97  lea     rcx, [rbp+57h+var_B8]
0x180151e9b  mov     rax, [rdi]
0x180151e9e  mov     rbx, [rax+30h]
0x180151ea2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180151ea7  mov     rdx, [rbp+57h+var_88]
0x180151eab  lea     r8, [rbp+57h+var_B8]
0x180151eaf  mov     rcx, rdi
0x180151eb2  mov     rax, rbx
0x180151eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151eba  mov     esi, eax
0x180151ebc  test    eax, eax
0x180151ebe  jns     loc_180151F4C
0x180151ec4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180151ecb  test    rcx, rcx
0x180151ece  jnz     short loc_180151F0E
0x180151ed0  mov     rax, cs:stru_1801FC290.__vftable
0x180151ed7  lea     rcx, stru_1801FC290
0x180151ede  mov     edx, 7F0h
0x180151ee3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151eea  mov     rax, [rax+8]
0x180151eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151ef3  test    eax, eax
0x180151ef5  jnz     short loc_180151F07
0x180151ef7  lea     rcx, stru_1801F8A30
0x180151efe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180151f05  jmp     short loc_180151F0E
0x180151f07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180151f0e  cmp     [rcx+8], r12b
0x180151f12  jz      short loc_180151F35
0x180151f14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180151f19  cmp     [rax+7CCh], esi
0x180151f1f  jz      short loc_180151F35
0x180151f21  mov     r9d, esi; int
  ... truncated ...
```
