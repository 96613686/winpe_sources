# CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect(void)

- ea: `0x18005d29c`
- end: `0x18005dd98`
- name: `?ConfigureRendererEffect@CxCodeVideoProcMFTDataHandler@@QEAAJXZ`
- size: `2812`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800244c4`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001a13c`
- `0x18003639c`
- `0x1800364d0`
- `0x180036590`
- `0x180036fe0`
- `0x180054140`
- `0x18005a5e0`
- `0x18005a6c0`
- `0x18005d29c`
- `0x180063110`
- `0x180065ba0`
- `0x180065bd0`
- `0x180065c10`
- `0x180066120`
- `0x180066250`
- `0x1800b3a9c`
- `0x1800b40a4`
- `0x1800b5760`
- `0x1800b5fc0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18005d3b8`
- `MFPlat!MFCreateMediaType` at `0x18005d52c`
- `MFPlat!MFCreateMediaType` at `0x18005d784`
- `MFPlat!MFCreateMediaType` at `0x18005d3b8`
- `MFPlat!MFCreateMediaType` at `0x18005d52c`
- `MFPlat!MFCreateMediaType` at `0x18005d784`

## string_xrefs

- `0x18005d2cb`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d3f2`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d493`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d5ea`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d63d`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d7c2`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d875`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d965`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005d9ff`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005daca`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005db3a`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005dc2e`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005dca8`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`
- `0x18005dd1f`: `CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect(CxCodeVideoProcMFTDataHandler *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int128 v4; // xmm0
  unsigned int v5; // edx
  int Attributes; // edi
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  struct IMFMediaType *v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rcx
  __m128i si128; // xmm6
  unsigned int v15; // eax
  unsigned int v16; // r14d
  _QWORD *v17; // rbx
  struct IMFMediaType *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  RendererEffectWrapper *v24; // r14
  unsigned int v25; // edx
  CMFTMultiStreamTypeHandler *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // edx
  int v29; // ebx
  struct IMFMediaType *v30; // rax
  unsigned int v31; // edx
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  struct IMFMediaType *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  struct IMFMediaType *v38; // rax
  int v39; // eax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  struct IMFMediaType *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  unsigned __int64 v46; // r8
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  CallStackTracing *v56; // rcx
  struct CallStackContext *v57; // rax
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-79h] BYREF
  IMFMediaType *v60; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v61[4]; // [rsp+48h] [rbp-69h] BYREF
  unsigned int v62; // [rsp+4Ch] [rbp-65h] BYREF
  __m128i v63; // [rsp+50h] [rbp-61h] BYREF
  __int64 v64; // [rsp+60h] [rbp-51h]
  __m128i v65; // [rsp+68h] [rbp-49h] BYREF
  __int64 v66; // [rsp+78h] [rbp-39h]
  __m128i v67; // [rsp+80h] [rbp-31h] BYREF
  __int64 v68; // [rsp+90h] [rbp-21h]
  _QWORD v69[2]; // [rsp+98h] [rbp-19h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v61,
    "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
    1953);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v4 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 388) + 280LL))(
                      *((_QWORD *)this + 388),
                      v69);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
    *((_OWORD *)ThreadRelativeContext + 125) = v4;
  }
  *((_DWORD *)this + 588) = 0;
  if ( *((_QWORD *)this + 217) )
  {
    if ( *((_QWORD *)this + 21)
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl'::`2'::impl) )
    {
      *((_DWORD *)this + 423) = (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21)) >= 49152;
    }
    LODWORD(v60) = 0;
    ppMFType = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    Attributes = MFCreateMediaType(&ppMFType);
    if ( Attributes < 0 )
    {
      v7 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v7 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext(v7);
        if ( *((_DWORD *)v8 + 499) != Attributes )
          CallStackContext::TraceFailure(v8, "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect", 1973, Attributes);
      }
      if ( !g_wppLevels )
        goto LABEL_156;
      v9 = 117;
      goto LABEL_16;
    }
    v10 = CMFTMultiStreamTypeHandler::POutputType(*((CMFTMultiStreamTypeHandler **)this + 1), v5);
    Attributes = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))v10->lpVtbl->CopyAllItems)(
                   v10,
                   ppMFType);
    if ( Attributes < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v11 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)v12 + 499) != Attributes )
          CallStackContext::TraceFailure(
            v12,
            "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
            1974,
            Attributes);
      }
      if ( !g_wppLevels )
        goto LABEL_156;
      v9 = 118;
LABEL_16:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        Attributes);
      goto LABEL_156;
    }
    v13 = *((_QWORD *)this + 1);
    v62 = 1;
    (*(void (__fastcall **)(__int64, unsigned int *, _QWORD))(*(_QWORD *)v13 + 8LL))(v13, &v62, 0);
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v63 = si128;
    v64 = -1;
    v69[0] = 0;
    utl::vector<Microsoft::WRL::ComPtr<IMFMediaType>,utl::allocator<Microsoft::WRL::ComPtr<IMFMediaType>>>::_Resize<Microsoft::WRL::ComPtr<IMFMediaType>,0>(
      &v63,
      v62,
      v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v69);
    v15 = v62;
    v16 = 0;
    v17 = (_QWORD *)v63.m128i_i64[0];
    if ( v62 )
    {
      while ( 1 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17[v16]);
        Attributes = MFCreateMediaType((IMFMediaType **)&v17[v16]);
        if ( Attributes < 0 )
          break;
        v18 = CMFTMultiStreamTypeHandler::PInputType(*((CMFTMultiStreamTypeHandler **)this + 1), v16);
        Attributes = ((__int64 (__fastcall *)(struct IMFMediaType *, _QWORD))v18->lpVtbl->CopyAllItems)(v18, v17[v16]);
        if ( Attributes < 0 )
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v19 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext(v19);
            if ( *((_DWORD *)v20 + 499) != Attributes )
              CallStackContext::TraceFailure(
                v20,
                "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
                1984,
                Attributes);
          }
          if ( g_wppLevels )
          {
            v21 = 120;
LABEL_48:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v21,
              &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
              this,
              Attributes);
            goto LABEL_49;
          }
          goto LABEL_49;
        }
        v15 = v62;
        if ( ++v16 >= v62 )
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          goto LABEL_31;
        }
      }
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v22 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( *((_DWORD *)v23 + 499) != Attributes )
          CallStackContext::TraceFailure(
            v23,
            "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
            1983,
            Attributes);
      }
      if ( g_wppLevels )
      {
        v21 = 119;
        goto LABEL_48;
      }
      goto LABEL_49;
    }
LABEL_31:
    v65 = si128;
    v66 = -1;
    utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>>::reserve(&v65, v15);
    while ( v17 != (_QWORD *)v63.m128i_i64[1] )
    {
      v69[0] = *v17;
      utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>>::push_back(&v65, v69);
      ++v17;
    }
    v24 = (CxCodeVideoProcMFTDataHandler *)((char *)this + 1584);
    if ( (int)RendererEffectWrapper::SetTypes((char *)this + 1584, &v65, ppMFType, &v60, 0) < 0
      || !*((_QWORD *)this + 217) )
    {
      RendererEffectWrapper::Clear((CxCodeVideoProcMFTDataHandler *)((char *)this + 1584));
      *((_DWORD *)this + 588) = 0;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 131, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
LABEL_128:
      utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(&v65);
      utl::vector<Microsoft::WRL::ComPtr<IMFMediaType>,utl::allocator<Microsoft::WRL::ComPtr<IMFMediaType>>>::_Uninit(&v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      goto LABEL_130;
    }
    v26 = (CMFTMultiStreamTypeHandler *)*((_QWORD *)this + 1);
    v67 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v68 = -1;
    v69[0] = CMFTMultiStreamTypeHandler::POutputType(v26, v25);
    utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>>::_Resize<IMFMediaType *,0>(&v67, v27, v69);
    v29 = (int)v60;
    if ( !(_DWORD)v60 )
    {
      v30 = CMFTMultiStreamTypeHandler::POutputType(*((CMFTMultiStreamTypeHandler **)this + 1), v28);
      if ( (int)RendererEffectWrapper::SetTypes((char *)this + 1584, &v67, v30, &v60, 0) >= 0 && *((_QWORD *)this + 217) )
      {
        v29 = (int)v60;
        if ( (_DWORD)v60 )
        {
          *((_DWORD *)this + 588) = 1;
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              121,
              &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
              this,
              v29);
          goto LABEL_108;
        }
      }
      else
      {
        v29 = (int)v60;
      }
    }
    if ( (v29 & 2) == 0 )
    {
      if ( (v29 & 1) != 0 )
      {
        v42 = CMFTMultiStreamTypeHandler::PInputType(*((CMFTMultiStreamTypeHandler **)this + 1), 0);
        Attributes = RendererEffectWrapper::SetTypes((char *)this + 1584, &v65, v42, &v60, 0);
        if ( Attributes < 0 )
        {
          v43 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v43 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v43 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext(v43);
            if ( *((_DWORD *)v44 + 499) != Attributes )
              CallStackContext::TraceFailure(
                v44,
                "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
                2034,
                Attributes);
          }
          if ( !g_wppLevels )
            goto LABEL_70;
          v45 = 127;
LABEL_104:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v45,
            &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
            this,
            Attributes);
          goto LABEL_70;
        }
        v29 = (int)v60;
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            128,
            &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
            this,
            (_DWORD)v60);
        *((_DWORD *)this + 588) = 2;
      }
      goto LABEL_108;
    }
    v60 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Attributes = MFCreateMediaType(&v60);
    if ( Attributes >= 0 )
    {
      v35 = CMFTMultiStreamTypeHandler::POutputType(*((CMFTMultiStreamTypeHandler **)this + 1), v31);
      Attributes = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))v35->lpVtbl->CopyAllItems)(v35, v60);
      if ( Attributes >= 0 )
      {
        if ( (v29 & 4) != 0 )
        {
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              125,
              &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
              this,
              v29);
          v39 = 14;
        }
        else
        {
          v38 = CMFTMultiStreamTypeHandler::PInputType(*((CMFTMultiStreamTypeHandler **)this + 1), 0);
          CopyScalingAttributes(v38, v60);
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              124,
              &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
              this,
              v29);
          v39 = 6;
        }
        *((_DWORD *)this + 588) = v39;
        Attributes = CxCodeVideoProcMFTDataHandler::OnInputTypeChanged(this, v60);
        if ( Attributes >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
LABEL_108:
          v46 = *((_QWORD *)this + 389);
          if ( v46 )
          {
            Attributes = RendererEffectWrapper::ProcessMessage(
                           (CxCodeVideoProcMFTDataHandler *)((char *)this + 1584),
                           MFT_MESSAGE_SET_D3D_MANAGER,
                           v46);
            if ( Attributes < 0 )
            {
              v47 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v47 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v47 + 8) )
              {
                v48 = CallStackTracing::GetThreadRelativeContext(v47);
                if ( *((_DWORD *)v48 + 499) != Attributes )
                  CallStackContext::TraceFailure(
                    v48,
                    "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
                    2041,
                    Attributes);
              }
              if ( !g_wppLevels )
                goto LABEL_70;
              v45 = 129;
              goto LABEL_104;
            }
          }
          Attributes = RendererEffectWrapper::ProcessMessage(
                         (CxCodeVideoProcMFTDataHandler *)((char *)this + 1584),
                         MFT_MESSAGE_NOTIFY_BEGIN_STREAMING,
                         0);
          if ( Attributes < 0 )
          {
            v49 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v49 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v49 + 8) )
            {
              v50 = CallStackTracing::GetThreadRelativeContext(v49);
              if ( *((_DWORD *)v50 + 499) != Attributes )
                CallStackContext::TraceFailure(
                  v50,
                  "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
                  2043,
                  Attributes);
            }
            if ( !g_wppLevels )
              goto LABEL_70;
            v45 = 130;
            goto LABEL_104;
          }
          *((_DWORD *)this + 592) = v29;
          utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(&v67);
          goto LABEL_128;
        }
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v40 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext(v40);
          if ( *((_DWORD *)v41 + 499) != Attributes )
            CallStackContext::TraceFailure(
              v41,
              "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
              2030,
              Attributes);
        }
        if ( !g_wppLevels )
        {
LABEL_69:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
LABEL_70:
          utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(&v67);
          utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(&v65);
LABEL_49:
          utl::vector<Microsoft::WRL::ComPtr<IMFMediaType>,utl::allocator<Microsoft::WRL::ComPtr<IMFMediaType>>>::_Uninit(&v63);
          goto LABEL_156;
        }
        v34 = 126;
      }
      else
      {
        v36 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v36 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext(v36);
          if ( *((_DWORD *)v37 + 499) != Attributes )
            CallStackContext::TraceFailure(
              v37,
              "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
              2017,
              Attributes);
        }
        if ( !g_wppLevels )
          goto LABEL_69;
        v34 = 123;
      }
    }
    else
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v32 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(v32);
        if ( *((_DWORD *)v33 + 499) != Attributes )
          CallStackContext::TraceFailure(
            v33,
            "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
            2016,
            Attributes);
      }
      if ( !g_wppLevels )
        goto LABEL_69;
      v34 = 122;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v34,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      Attributes);
    goto LABEL_69;
  }
  Attributes = 0;
  v24 = (CxCodeVideoProcMFTDataHandler *)((char *)this + 1584);
LABEL_130:
  if ( *((_QWORD *)this + 217) )
  {
    ppMFType = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    Attributes = RendererEffectWrapper::GetAttributes(v24, (struct IMFAttributes **)&ppMFType);
    if ( Attributes >= 0 )
    {
      Attributes = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(**((_QWORD **)this + 28) + 256LL))(
                     *((_QWORD *)this + 28),
                     ppMFType);
      if ( Attributes >= 0 )
      {
        Attributes = ((__int64 (__fastcall *)(IMFMediaType *, _QWORD))ppMFType->lpVtbl->CopyAllItems)(
                       ppMFType,
                       *((_QWORD *)this + 28));
        if ( Attributes >= 0 )
          goto LABEL_156;
        v56 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v56 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v56 + 8) )
        {
          v57 = CallStackTracing::GetThreadRelativeContext(v56);
          if ( *((_DWORD *)v57 + 499) != Attributes )
            CallStackContext::TraceFailure(
              v57,
              "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
              2062,
              Attributes);
        }
        if ( !g_wppLevels )
          goto LABEL_156;
        v53 = 134;
      }
      else
      {
        v54 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v54 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext(v54);
          if ( *((_DWORD *)v55 + 499) != Attributes )
            CallStackContext::TraceFailure(
              v55,
              "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
              2061,
              Attributes);
        }
        if ( !g_wppLevels )
          goto LABEL_156;
        v53 = 133;
      }
    }
    else
    {
      v51 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v51 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext(v51);
        if ( *((_DWORD *)v52 + 499) != Attributes )
          CallStackContext::TraceFailure(
            v52,
            "CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect",
            2058,
            Attributes);
      }
      if ( !g_wppLevels )
        goto LABEL_156;
      v53 = 132;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v53,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      Attributes);
LABEL_156:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x18005d29c  mov     rax, rsp
0x18005d29f  push    rbp
0x18005d2a0  push    rbx
0x18005d2a1  push    rsi
0x18005d2a2  push    rdi
0x18005d2a3  push    r12
0x18005d2a5  push    r13
0x18005d2a7  push    r14
0x18005d2a9  push    r15
0x18005d2ab  lea     rbp, [rax-5Fh]
0x18005d2af  sub     rsp, 0C8h
0x18005d2b6  movaps  xmmword ptr [rax-58h], xmm6
0x18005d2ba  mov     rax, cs:__security_cookie
0x18005d2c1  xor     rax, rsp
0x18005d2c4  mov     [rbp+57h+var_60], rax
0x18005d2c8  mov     rsi, rcx
0x18005d2cb  lea     rdx, aCxcodevideopro_72; "CxCodeVideoProcMFTDataHandler::Configur"...
0x18005d2d2  lea     rcx, [rbp+57h+var_C0]; this
0x18005d2d6  mov     r8d, 7A1h; int
0x18005d2dc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005d2e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005d2e8  xor     r12d, r12d
0x18005d2eb  cmp     [rcx+8], r12b
0x18005d2ef  jz      short loc_18005D345
0x18005d2f1  cmp     [rsi+0C20h], r12
0x18005d2f8  jz      short loc_18005D345
0x18005d2fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d2ff  mov     rcx, [rsi+0C20h]
0x18005d306  mov     rdi, rax
0x18005d309  mov     rdx, [rcx]
0x18005d30c  mov     rax, [rdx+128h]
0x18005d313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d318  mov     rcx, [rsi+0C20h]
0x18005d31f  mov     ebx, eax
0x18005d321  mov     rdx, [rcx]
0x18005d324  mov     rax, [rdx+118h]
0x18005d32b  lea     rdx, [rbp+57h+var_70]
0x18005d32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d334  movups  xmm0, xmmword ptr [rax]
0x18005d337  mov     [rdi+7E0h], ebx
0x18005d33d  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18005d345  lea     r15, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005d34c  mov     [rsi+930h], r12d
0x18005d353  mov     r13d, 1
0x18005d359  cmp     [rsi+6C8h], r12
0x18005d360  jz      loc_18005DBCA
0x18005d366  cmp     [rsi+0A8h], r12
0x18005d36d  jz      short loc_18005D3A3
0x18005d36f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects> `wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl(void)'::`2'::impl
0x18005d376  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(void)
0x18005d37b  test    al, al
0x18005d37d  jz      short loc_18005D3A3
0x18005d37f  mov     rcx, [rsi+0A8h]
0x18005d386  mov     rax, [rcx]
0x18005d389  mov     rax, [rax+30h]
0x18005d38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d392  mov     ecx, r12d
0x18005d395  cmp     eax, 0C000h
0x18005d39a  setnl   cl
0x18005d39d  mov     [rsi+69Ch], ecx
0x18005d3a3  lea     rcx, [rbp+57h+ppMFType]
0x18005d3a7  mov     dword ptr [rbp+57h+var_C8], r12d
0x18005d3ab  mov     [rbp+57h+ppMFType], r12
0x18005d3af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d3b4  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x18005d3b8  call    cs:__imp_MFCreateMediaType
0x18005d3be  mov     edi, eax
0x18005d3c0  test    eax, eax
0x18005d3c2  jns     short loc_18005D43D
0x18005d3c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d3cb  test    rcx, rcx
0x18005d3ce  jnz     short loc_18005D3DC
0x18005d3d0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005d3d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005d3dc  cmp     [rcx+8], r12b
0x18005d3e0  jz      short loc_18005D407
0x18005d3e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d3e7  cmp     [rax+7CCh], edi
0x18005d3ed  jz      short loc_18005D407
0x18005d3ef  mov     r9d, edi; int
0x18005d3f2  lea     rdx, aCxcodevideopro_72; "CxCodeVideoProcMFTDataHandler::Configur"...
0x18005d3f9  mov     r8d, 7B5h; int
0x18005d3ff  mov     rcx, rax; this
0x18005d402  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d407  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18005d40e  jb      short loc_18005D42F
0x18005d410  mov     edx, 75h ; 'u'
0x18005d415  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d41c  mov     r9, rsi
0x18005d41f  mov     r8, r15
0x18005d422  mov     [rsp+20h], edi
0x18005d426  mov     rcx, [rcx+10h]
0x18005d42a  call    WPP_SF_qD
0x18005d42f  lea     rcx, [rbp+57h+ppMFType]
0x18005d433  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d438  jmp     loc_18005DD65
0x18005d43d  mov     rcx, [rsi+8]; this
0x18005d441  call    ?POutputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::POutputType(ulong)
0x18005d446  mov     rdx, [rbp+57h+ppMFType]
0x18005d44a  mov     r8, rax
0x18005d44d  mov     rcx, [rax]
0x18005d450  mov     rax, [rcx+100h]
0x18005d457  mov     rcx, r8
0x18005d45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d45f  mov     edi, eax
0x18005d461  test    eax, eax
0x18005d463  jns     short loc_18005D4BF
0x18005d465  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d46c  test    rcx, rcx
0x18005d46f  jnz     short loc_18005D47D
0x18005d471  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005d476  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005d47d  cmp     [rcx+8], r12b
0x18005d481  jz      short loc_18005D4A8
0x18005d483  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d488  cmp     [rax+7CCh], edi
0x18005d48e  jz      short loc_18005D4A8
0x18005d490  mov     r9d, edi; int
0x18005d493  lea     rdx, aCxcodevideopro_72; "CxCodeVideoProcMFTDataHandler::Configur"...
0x18005d49a  mov     r8d, 7B6h; int
0x18005d4a0  mov     rcx, rax; this
0x18005d4a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d4a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18005d4af  jb      loc_18005D42F
0x18005d4b5  mov     edx, 76h ; 'v'
0x18005d4ba  jmp     loc_18005D415
0x18005d4bf  mov     rcx, [rsi+8]
0x18005d4c3  lea     rdx, [rbp+57h+var_BC]
0x18005d4c7  mov     [rbp+57h+var_BC], r13d
0x18005d4cb  xor     r8d, r8d
0x18005d4ce  mov     rax, [rcx]
0x18005d4d1  mov     rax, [rax+8]
0x18005d4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4da  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18005d4e2  lea     r8, [rbp+57h+var_70]
0x18005d4e6  mov     edx, [rbp+57h+var_BC]
0x18005d4e9  lea     rcx, [rbp+57h+var_B8]
0x18005d4ed  movdqu  [rbp+57h+var_B8], xmm6
0x18005d4f2  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFFh
0x18005d4fa  mov     [rbp+57h+var_70], r12
0x18005d4fe  call    ??$_Resize@V?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@$0A@@?$vector@V?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@@utl@@@utl@@AEAA_N_KAEBV?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@@Z; utl::vector<Microsoft::WRL::ComPtr<IMFMediaType>,utl::allocator<Microsoft::WRL::ComPtr<IMFMediaType>>>::_Resize<Microsoft::WRL::ComPtr<IMFMediaType>,0>(unsigned __int64,Microsoft::WRL::ComPtr<IMFMediaType> const &)
0x18005d503  lea     rcx, [rbp+57h+var_70]
0x18005d507  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d50c  mov     eax, [rbp+57h+var_BC]
0x18005d50f  mov     r14d, r12d
0x18005d512  mov     rbx, qword ptr [rbp+57h+var_B8]
0x18005d516  test    eax, eax
0x18005d518  jz      short loc_18005D580
0x18005d51a  mov     eax, r14d
0x18005d51d  lea     r15, [rbx+rax*8]
0x18005d521  mov     rcx, r15
0x18005d524  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d529  mov     rcx, r15; ppMFType
0x18005d52c  call    cs:__imp_MFCreateMediaType
0x18005d532  mov     edi, eax
0x18005d534  test    eax, eax
0x18005d536  js      loc_18005D60F
0x18005d53c  mov     rcx, [rsi+8]; this
0x18005d540  mov     edx, r14d; unsigned int
0x18005d543  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x18005d548  mov     rdx, [r15]
0x18005d54b  mov     r10, rax
0x18005d54e  mov     rcx, [rax]
0x18005d551  mov     rax, [rcx+100h]
0x18005d558  mov     rcx, r10
0x18005d55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d560  mov     edi, eax
0x18005d562  test    eax, eax
0x18005d564  js      short loc_18005D5BC
0x18005d566  mov     eax, [rbp+57h+var_BC]
0x18005d569  add     r14d, r13d
0x18005d56c  cmp     r14d, eax
0x18005d56f  jb      short loc_18005D51A
0x18005d571  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18005d579  lea     r15, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005d580  mov     edx, eax
0x18005d582  lea     rcx, [rbp+57h+var_A0]
0x18005d586  movdqu  [rbp+57h+var_A0], xmm6
0x18005d58b  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFFh
0x18005d593  call    ?reserve@?$vector@PEAUIMFMediaType@@V?$allocator@PEAUIMFMediaType@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>>::reserve(unsigned __int64)
0x18005d598  cmp     rbx, qword ptr [rbp+57h+var_B8+8]
0x18005d59c  jz      loc_18005D68C
0x18005d5a2  mov     rax, [rbx]
0x18005d5a5  lea     rdx, [rbp+57h+var_70]
0x18005d5a9  lea     rcx, [rbp+57h+var_A0]
0x18005d5ad  mov     [rbp+57h+var_70], rax
0x18005d5b1  call    ?push_back@?$vector@PEAUIMFMediaType@@V?$allocator@PEAUIMFMediaType@@@utl@@@utl@@QEAA_N$$QEAPEAUIMFMediaType@@@Z; utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>>::push_back(IMFMediaType * &&)
0x18005d5b6  add     rbx, 8
0x18005d5ba  jmp     short loc_18005D598
0x18005d5bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d5c3  test    rcx, rcx
0x18005d5c6  jnz     short loc_18005D5D4
0x18005d5c8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005d5cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005d5d4  cmp     [rcx+8], r12b
0x18005d5d8  jz      short loc_18005D5FF
0x18005d5da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d5df  cmp     [rax+7CCh], edi
0x18005d5e5  jz      short loc_18005D5FF
0x18005d5e7  mov     r9d, edi; int
0x18005d5ea  lea     rdx, aCxcodevideopro_72; "CxCodeVideoProcMFTDataHandler::Configur"...
0x18005d5f1  mov     r8d, 7C0h; int
0x18005d5f7  mov     rcx, rax; this
0x18005d5fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d5ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18005d606  jb      short loc_18005D67E
0x18005d608  mov     edx, 78h ; 'x'
0x18005d60d  jmp     short loc_18005D660
0x18005d60f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d616  test    rcx, rcx
0x18005d619  jnz     short loc_18005D627
0x18005d61b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005d620  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005d627  cmp     [rcx+8], r12b
0x18005d62b  jz      short loc_18005D652
0x18005d62d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d632  cmp     [rax+7CCh], edi
0x18005d638  jz      short loc_18005D652
0x18005d63a  mov     r9d, edi; int
0x18005d63d  lea     rdx, aCxcodevideopro_72; "CxCodeVideoProcMFTDataHandler::Configur"...
0x18005d644  mov     r8d, 7BFh; int
0x18005d64a  mov     rcx, rax; this
0x18005d64d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d652  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18005d659  jb      short loc_18005D67E
0x18005d65b  mov     edx, 77h ; 'w'
0x18005d660  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d667  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18005d66e  mov     r9, rsi
0x18005d671  mov     [rsp+20h], edi
0x18005d675  mov     rcx, [rcx+10h]
0x18005d679  call    WPP_SF_qD
0x18005d67e  lea     rcx, [rbp+57h+var_B8]
0x18005d682  call    ?_Uninit@?$vector@V?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@@utl@@@utl@@AEAAXXZ; utl::vector<Microsoft::WRL::ComPtr<IMFMediaType>,utl::allocator<Microsoft::WRL::ComPtr<IMFMediaType>>>::_Uninit(void)
0x18005d687  jmp     loc_18005D42F
0x18005d68c  mov     r8, [rbp+57h+ppMFType]
0x18005d690  lea     r14, [rsi+630h]
0x18005d697  mov     rcx, r14
0x18005d69a  mov     [rsp+20h], r12d
0x18005d69f  lea     r9, [rbp+57h+var_C8]
0x18005d6a3  lea     rdx, [rbp+57h+var_A0]
0x18005d6a7  call    ?SetTypes@RendererEffectWrapper@@QEAAJAEBV?$vector@PEAUIMFMediaType@@V?$allocator@PEAUIMFMediaType@@@utl@@@utl@@PEAUIMFMediaType@@PEAIK@Z; RendererEffectWrapper::SetTypes(utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>> const &,IMFMediaType *,uint *,ulong)
0x18005d6ac  test    eax, eax
0x18005d6ae  js      loc_18005DB77
0x18005d6b4  cmp     [rsi+6C8h], r12
0x18005d6bb  jz      loc_18005DB77
0x18005d6c1  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18005d6c9  mov     rcx, [rsi+8]; this
0x18005d6cd  movdqu  [rbp+57h+var_88], xmm0
0x18005d6d2  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFFh
0x18005d6da  call    ?POutputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::POutputType(ulong)
0x18005d6df  lea     r8, [rbp+57h+var_70]
0x18005d6e3  mov     [rbp+57h+var_70], rax
0x18005d6e7  lea     rcx, [rbp+57h+var_88]
0x18005d6eb  call    ??$_Resize@PEAUIMFMediaType@@$0A@@?$vector@PEAUIMFMediaType@@V?$allocator@PEAUIMFMediaType@@@utl@@@utl@@AEAA_N_KAEBQEAUIMFMediaType@@@Z; utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>>::_Resize<IMFMediaType *,0>(unsigned __int64,IMFMediaType * const &)
0x18005d6f0  mov     ebx, dword ptr [rbp+57h+var_C8]
0x18005d6f3  test    ebx, ebx
0x18005d6f5  jnz     short loc_18005D76A
0x18005d6f7  mov     rcx, [rsi+8]; this
0x18005d6fb  call    ?POutputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::POutputType(ulong)
0x18005d700  mov     r8, rax
0x18005d703  mov     [rsp+20h], r12d
0x18005d708  lea     rdx, [rbp+57h+var_88]
0x18005d70c  mov     rcx, r14
0x18005d70f  lea     r9, [rbp+57h+var_C8]
0x18005d713  call    ?SetTypes@RendererEffectWrapper@@QEAAJAEBV?$vector@PEAUIMFMediaType@@V?$allocator@PEAUIMFMediaType@@@utl@@@utl@@PEAUIMFMediaType@@PEAIK@Z; RendererEffectWrapper::SetTypes(utl::vector<IMFMediaType *,utl::allocator<IMFMediaType *>> const &,IMFMediaType *,uint *,ulong)
0x18005d718  test    eax, eax
0x18005d71a  js      short loc_18005D767
0x18005d71c  cmp     [rsi+6C8h], r12
0x18005d723  jz      short loc_18005D767
0x18005d725  mov     ebx, dword ptr [rbp+57h+var_C8]
0x18005d728  test    ebx, ebx
0x18005d72a  jz      short loc_18005D76A
0x18005d72c  mov     [rsi+930h], r13d
0x18005d733  cmp     cs:byte_180153DE0, 20h ; ' '
0x18005d73a  jb      loc_18005DA7D
0x18005d740  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d747  mov     edx, 79h ; 'y'
0x18005d74c  mov     r9, rsi
0x18005d74f  mov     [rsp+20h], ebx
0x18005d753  mov     r8, r15
0x18005d756  mov     rcx, [rcx+150h]
0x18005d75d  call    WPP_SF_qD
0x18005d762  jmp     loc_18005DA7D
0x18005d767  mov     ebx, dword ptr [rbp+57h+var_C8]
0x18005d76a  test    bl, 2
0x18005d76d  jz      loc_18005D99F
0x18005d773  lea     rcx, [rbp+57h+var_C8]
0x18005d777  mov     [rbp+57h+var_C8], r12
0x18005d77b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d780  lea     rcx, [rbp+57h+var_C8]; ppMFType
0x18005d784  call    cs:__imp_MFCreateMediaType
0x18005d78a  mov     edi, eax
0x18005d78c  test    eax, eax
0x18005d78e  jns     loc_18005D81F
0x18005d794  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d79b  test    rcx, rcx
0x18005d79e  jnz     short loc_18005D7AC
0x18005d7a0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005d7a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
  ... truncated ...
```
