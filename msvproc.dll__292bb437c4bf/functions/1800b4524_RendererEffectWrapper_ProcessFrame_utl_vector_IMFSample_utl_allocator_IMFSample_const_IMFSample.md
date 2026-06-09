# RendererEffectWrapper::ProcessFrame(utl::vector<IMFSample *,utl::allocator<IMFSample *>> const &,IMFSample *)

- ea: `0x1800b4524`
- end: `0x1800b5757`
- name: `?ProcessFrame@RendererEffectWrapper@@QEAAJAEBV?$vector@PEAUIMFSample@@V?$allocator@PEAUIMFSample@@@utl@@@utl@@PEAUIMFSample@@@Z`
- size: `4659`
- prototype: `__int64 __fastcall(RendererEffectWrapper *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cb40`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001a13c`
- `0x18001b3c4`
- `0x18001ba40`
- `0x18003639c`
- `0x180037230`
- `0x180065c10`
- `0x180066948`
- `0x180066a98`
- `0x1800b4524`
- `0x1800c1594`
- `0x1800c22d4`
- `0x1800c3fe4`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x1800b469f`
- `MFPlat!MFCreateSample` at `0x1800b4817`
- `MFPlat!MFCreateSample` at `0x1800b517c`
- `MFPlat!MFCreateSample` at `0x1800b5504`
- `MFPlat!MFCreateSample` at `0x1800b469f`
- `MFPlat!MFCreateSample` at `0x1800b4817`
- `MFPlat!MFCreateSample` at `0x1800b517c`
- `MFPlat!MFCreateSample` at `0x1800b5504`

## pseudocode

```c
__int64 __fastcall RendererEffectWrapper::ProcessFrame(RendererEffectWrapper *this, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rcx
  unsigned int v7; // r12d
  char IsEnabled; // al
  __int64 v9; // r14
  HRESULT VideoService; // ebx
  __int64 (__fastcall *v11)(__int64, _QWORD, struct IUnknown **); // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, struct IUnknown **); // rbx
  char v13; // al
  CallStackTracing *v14; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  __int64 (__fastcall *v48)(__int64, _QWORD, struct IUnknown **); // rbx
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  CallStackTracing *v59; // rcx
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 (__fastcall *v62)(__int64, _QWORD, struct IUnknown **); // rbx
  CallStackTracing *v63; // rcx
  struct CallStackContext *v64; // rax
  CallStackTracing *v65; // rcx
  struct CallStackContext *v66; // rax
  CallStackTracing *v67; // rcx
  struct CallStackContext *v68; // rax
  CallStackTracing *v69; // rcx
  struct CallStackContext *v70; // rax
  CallStackTracing *v71; // rcx
  struct CallStackContext *v72; // rax
  __int64 v73; // rcx
  IMFSample *ppIMFSample; // [rsp+30h] [rbp-50h] BYREF
  struct IUnknown *v76; // [rsp+38h] [rbp-48h] BYREF
  struct IUnknown *v77; // [rsp+40h] [rbp-40h] BYREF
  struct ID3D12Device *v78; // [rsp+48h] [rbp-38h] BYREF
  __int64 v79; // [rsp+50h] [rbp-30h] BYREF
  _OWORD v80[2]; // [rsp+58h] [rbp-28h] BYREF
  char v81; // [rsp+C8h] [rbp+48h] BYREF
  int v82; // [rsp+D0h] [rbp+50h] BYREF
  IMFSample *v83; // [rsp+D8h] [rbp+58h] BYREF

  v79 = a3;
  Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(&v79);
  memset(v80, 0, sizeof(v80));
  v82 = 0;
  if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 2) != 0 )
    McTemplateU0p_EventWriteTransfer(v6, "}", this);
  v7 = 0;
  if ( !((__int64)(a2[1] - *a2) >> 3) )
  {
LABEL_36:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl'::`2'::impl) )
      goto LABEL_251;
    if ( !a3 )
      goto LABEL_251;
    v13 = *((_BYTE *)this + 105);
    if ( !v13 && !*((_BYTE *)this + 104) )
      goto LABEL_251;
    if ( !*((_DWORD *)this + 27) )
    {
      if ( *((_BYTE *)this + 104) )
      {
LABEL_251:
        v73 = *((_QWORD *)this + 19);
        *((_QWORD *)&v80[0] + 1) = v79;
        VideoService = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _OWORD *, int *))(*(_QWORD *)v73 + 200LL))(
                         v73,
                         0,
                         1,
                         v80,
                         &v82);
        goto LABEL_252;
      }
      v76 = 0;
      v83 = 0;
      v77 = 0;
      v78 = 0;
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v81, "RendererEffectWrapper::ProcessFrame", 651);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      VideoService = MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(
                       (RendererEffectWrapper *)((char *)this + 112),
                       &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
                       (void **)&v76);
      if ( VideoService < 0 )
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v14 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != VideoService )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "RendererEffectWrapper::ProcessFrame",
              651,
              VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v16 = 75;
        goto LABEL_50;
      }
      v48 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)a3 + 320LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      VideoService = v48(a3, 0, &v77);
      if ( VideoService < 0 )
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
          if ( *((_DWORD *)v50 + 499) != VideoService )
            CallStackContext::TraceFailure(v50, "RendererEffectWrapper::ProcessFrame", 652, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v16 = 76;
        goto LABEL_50;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      VideoService = MFD3D::CMFDXGIBuffer11to12::CreateInstance(
                       v77,
                       (struct ID3D12Device *)v76,
                       (struct IUnknown **)&v78);
      if ( VideoService < 0 )
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
          if ( *((_DWORD *)v52 + 499) != VideoService )
            CallStackContext::TraceFailure(v52, "RendererEffectWrapper::ProcessFrame", 654, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v16 = 77;
        goto LABEL_50;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      VideoService = MFCreateSample(&v83);
      if ( VideoService < 0 )
      {
        v53 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v53 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext(v53);
          if ( *((_DWORD *)v54 + 499) != VideoService )
            CallStackContext::TraceFailure(v54, "RendererEffectWrapper::ProcessFrame", 655, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v16 = 78;
        goto LABEL_50;
      }
      VideoService = ((__int64 (__fastcall *)(IMFSample *, struct ID3D12Device *))v83->lpVtbl->AddBuffer)(v83, v78);
      if ( VideoService < 0 )
      {
        v55 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v55 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v55 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext(v55);
          if ( *((_DWORD *)v56 + 499) != VideoService )
            CallStackContext::TraceFailure(v56, "RendererEffectWrapper::ProcessFrame", 656, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v16 = 79;
        goto LABEL_50;
      }
      VideoService = (*(__int64 (__fastcall **)(__int64, IMFSample *))(*(_QWORD *)a3 + 256LL))(a3, v83);
      if ( VideoService < 0 )
      {
        v57 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v57 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v57 + 8) )
        {
          v58 = CallStackTracing::GetThreadRelativeContext(v57);
          if ( *((_DWORD *)v58 + 499) != VideoService )
            CallStackContext::TraceFailure(v58, "RendererEffectWrapper::ProcessFrame", 657, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v16 = 80;
LABEL_50:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
          this,
          VideoService);
LABEL_51:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
        goto LABEL_252;
      }
LABEL_250:
      Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v79, &v83);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      goto LABEL_251;
    }
    if ( *((_DWORD *)this + 27) != 1 || v13 )
      goto LABEL_251;
    v76 = 0;
    v83 = 0;
    v77 = 0;
    v78 = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v81, "RendererEffectWrapper::ProcessFrame", 665);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    VideoService = MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(
                     (RendererEffectWrapper *)((char *)this + 112),
                     &GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140,
                     (void **)&v76);
    if ( VideoService >= 0 )
    {
      v62 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)a3 + 320LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      VideoService = v62(a3, 0, &v77);
      if ( VideoService >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        VideoService = MFD3D::CMFDXGIBuffer12to11::CreateInstance(
                         v77,
                         (struct ID3D11Device *)v76,
                         (struct IUnknown **)&v78);
        if ( VideoService >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
          VideoService = MFCreateSample(&v83);
          if ( VideoService >= 0 )
          {
            VideoService = ((__int64 (__fastcall *)(IMFSample *, struct ID3D12Device *))v83->lpVtbl->AddBuffer)(
                             v83,
                             v78);
            if ( VideoService >= 0 )
            {
              VideoService = (*(__int64 (__fastcall **)(__int64, IMFSample *))(*(_QWORD *)a3 + 256LL))(a3, v83);
              if ( VideoService >= 0 )
                goto LABEL_250;
              v71 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v71 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v71 + 8) )
              {
                v72 = CallStackTracing::GetThreadRelativeContext(v71);
                if ( *((_DWORD *)v72 + 499) != VideoService )
                  CallStackContext::TraceFailure(v72, "RendererEffectWrapper::ProcessFrame", 671, VideoService);
              }
              if ( !g_wppLevels )
                goto LABEL_51;
              v61 = 86;
            }
            else
            {
              v69 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v69 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v69 + 8) )
              {
                v70 = CallStackTracing::GetThreadRelativeContext(v69);
                if ( *((_DWORD *)v70 + 499) != VideoService )
                  CallStackContext::TraceFailure(v70, "RendererEffectWrapper::ProcessFrame", 670, VideoService);
              }
              if ( !g_wppLevels )
                goto LABEL_51;
              v61 = 85;
            }
          }
          else
          {
            v67 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v67 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v67 + 8) )
            {
              v68 = CallStackTracing::GetThreadRelativeContext(v67);
              if ( *((_DWORD *)v68 + 499) != VideoService )
                CallStackContext::TraceFailure(v68, "RendererEffectWrapper::ProcessFrame", 669, VideoService);
            }
            if ( !g_wppLevels )
              goto LABEL_51;
            v61 = 84;
          }
        }
        else
        {
          v65 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v65 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v65 + 8) )
          {
            v66 = CallStackTracing::GetThreadRelativeContext(v65);
            if ( *((_DWORD *)v66 + 499) != VideoService )
              CallStackContext::TraceFailure(v66, "RendererEffectWrapper::ProcessFrame", 668, VideoService);
          }
          if ( !g_wppLevels )
            goto LABEL_51;
          v61 = 83;
        }
      }
      else
      {
        v63 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v63 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v64 = CallStackTracing::GetThreadRelativeContext(v63);
          if ( *((_DWORD *)v64 + 499) != VideoService )
            CallStackContext::TraceFailure(v64, "RendererEffectWrapper::ProcessFrame", 666, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v61 = 82;
      }
    }
    else
    {
      v59 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v59 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext(v59);
        if ( *((_DWORD *)v60 + 499) != VideoService )
          CallStackContext::TraceFailure(v60, "RendererEffectWrapper::ProcessFrame", 665, VideoService);
      }
      if ( !g_wppLevels )
        goto LABEL_51;
      v61 = 81;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v61,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      this,
      VideoService);
    goto LABEL_51;
  }
  while ( 1 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl'::`2'::impl);
    v9 = *(_QWORD *)(*a2 + 8LL * v7);
    if ( !IsEnabled )
      break;
    if ( !v9 || !*((_BYTE *)this + 105) && !*((_BYTE *)this + 104) )
      goto LABEL_35;
    v83 = *(IMFSample **)(*a2 + 8LL * v7);
    Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(&v83);
    if ( *((_DWORD *)this + 27) )
    {
      if ( *((_DWORD *)this + 27) == 1 && !*((_BYTE *)this + 105) )
      {
        v76 = 0;
        ppIMFSample = 0;
        v77 = 0;
        v78 = 0;
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v81,
          "RendererEffectWrapper::ProcessFrame",
          619);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
        VideoService = MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(
                         (RendererEffectWrapper *)((char *)this + 112),
                         &GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140,
                         (void **)&v76);
        if ( VideoService < 0 )
        {
          v42 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v42 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v43 = CallStackTracing::GetThreadRelativeContext(v42);
            if ( *((_DWORD *)v43 + 499) != VideoService )
              CallStackContext::TraceFailure(v43, "RendererEffectWrapper::ProcessFrame", 619, VideoService);
          }
          if ( !g_wppLevels )
            goto LABEL_140;
          v33 = 66;
LABEL_139:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v33,
            &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
            this,
            VideoService);
          goto LABEL_140;
        }
        v12 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v9 + 320LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
        VideoService = v12(v9, 0, &v77);
        if ( VideoService < 0 )
        {
          v40 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v40 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v40 + 8) )
          {
            v41 = CallStackTracing::GetThreadRelativeContext(v40);
            if ( *((_DWORD *)v41 + 499) != VideoService )
              CallStackContext::TraceFailure(v41, "RendererEffectWrapper::ProcessFrame", 620, VideoService);
          }
          if ( !g_wppLevels )
            goto LABEL_140;
          v33 = 67;
          goto LABEL_139;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        VideoService = MFD3D::CMFDXGIBuffer12to11::CreateInstance(
                         v77,
                         (struct ID3D11Device *)v76,
                         (struct IUnknown **)&v78);
        if ( VideoService < 0 )
        {
          v38 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v38 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v39 = CallStackTracing::GetThreadRelativeContext(v38);
            if ( *((_DWORD *)v39 + 499) != VideoService )
              CallStackContext::TraceFailure(v39, "RendererEffectWrapper::ProcessFrame", 622, VideoService);
          }
          if ( !g_wppLevels )
            goto LABEL_140;
          v33 = 68;
          goto LABEL_139;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIMFSample);
        VideoService = MFCreateSample(&ppIMFSample);
        if ( VideoService < 0 )
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
            if ( *((_DWORD *)v37 + 499) != VideoService )
              CallStackContext::TraceFailure(v37, "RendererEffectWrapper::ProcessFrame", 623, VideoService);
          }
          if ( !g_wppLevels )
            goto LABEL_140;
          v33 = 69;
          goto LABEL_139;
        }
        VideoService = ((__int64 (__fastcall *)(IMFSample *, struct ID3D12Device *))ppIMFSample->lpVtbl->AddBuffer)(
                         ppIMFSample,
                         v78);
        if ( VideoService < 0 )
        {
          v34 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v34 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v34 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext(v34);
            if ( *((_DWORD *)v35 + 499) != VideoService )
              CallStackContext::TraceFailure(v35, "RendererEffectWrapper::ProcessFrame", 624, VideoService);
          }
          if ( !g_wppLevels )
            goto LABEL_140;
          v33 = 70;
          goto LABEL_139;
        }
        VideoService = (*(__int64 (__fastcall **)(__int64, IMFSample *))(*(_QWORD *)v9 + 256LL))(v9, ppIMFSample);
        if ( VideoService < 0 )
        {
          v31 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v31 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v32 = CallStackTracing::GetThreadRelativeContext(v31);
            if ( *((_DWORD *)v32 + 499) != VideoService )
              CallStackContext::TraceFailure(v32, "RendererEffectWrapper::ProcessFrame", 625, VideoService);
          }
          if ( g_wppLevels )
          {
            v33 = 71;
            goto LABEL_139;
          }
LABEL_140:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIMFSample);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
LABEL_96:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
          goto LABEL_252;
        }
        Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v83, &ppIMFSample);
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 72, &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIMFSample);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      }
    }
    else if ( !*((_BYTE *)this + 104) )
    {
      v78 = 0;
      ppIMFSample = 0;
      v77 = 0;
      v76 = 0;
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v81, "RendererEffectWrapper::ProcessFrame", 603);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      VideoService = MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(
                       (RendererEffectWrapper *)((char *)this + 112),
                       &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
                       (void **)&v78);
      if ( VideoService < 0 )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v29 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext(v29);
          if ( *((_DWORD *)v30 + 499) != VideoService )
            CallStackContext::TraceFailure(v30, "RendererEffectWrapper::ProcessFrame", 603, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v20 = 59;
LABEL_94:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v20,
          &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
          this,
          VideoService);
        goto LABEL_95;
      }
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v9 + 320LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      VideoService = v11(v9, 0, &v77);
      if ( VideoService < 0 )
      {
        v27 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v27 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v28 = CallStackTracing::GetThreadRelativeContext(v27);
          if ( *((_DWORD *)v28 + 499) != VideoService )
            CallStackContext::TraceFailure(v28, "RendererEffectWrapper::ProcessFrame", 604, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v20 = 60;
        goto LABEL_94;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      VideoService = MFD3D::CMFDXGIBuffer11to12::CreateInstance(v77, v78, &v76);
      if ( VideoService < 0 )
      {
        v25 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v25 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext(v25);
          if ( *((_DWORD *)v26 + 499) != VideoService )
            CallStackContext::TraceFailure(v26, "RendererEffectWrapper::ProcessFrame", 606, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v20 = 61;
        goto LABEL_94;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIMFSample);
      VideoService = MFCreateSample(&ppIMFSample);
      if ( VideoService < 0 )
      {
        v23 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v23 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext(v23);
          if ( *((_DWORD *)v24 + 499) != VideoService )
            CallStackContext::TraceFailure(v24, "RendererEffectWrapper::ProcessFrame", 607, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v20 = 62;
        goto LABEL_94;
      }
      VideoService = ((__int64 (__fastcall *)(IMFSample *, struct IUnknown *))ppIMFSample->lpVtbl->AddBuffer)(
                       ppIMFSample,
                       v76);
      if ( VideoService < 0 )
      {
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v21 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( *((_DWORD *)v22 + 499) != VideoService )
            CallStackContext::TraceFailure(v22, "RendererEffectWrapper::ProcessFrame", 608, VideoService);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v20 = 63;
        goto LABEL_94;
      }
      VideoService = (*(__int64 (__fastcall **)(__int64, IMFSample *))(*(_QWORD *)v9 + 256LL))(v9, ppIMFSample);
      if ( VideoService < 0 )
      {
        v18 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v18 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext(v18);
          if ( *((_DWORD *)v19 + 499) != VideoService )
            CallStackContext::TraceFailure(v19, "RendererEffectWrapper::ProcessFrame", 609, VideoService);
        }
        if ( g_wppLevels )
        {
          v20 = 64;
          goto LABEL_94;
        }
LABEL_95:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIMFSample);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        goto LABEL_96;
      }
      Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v83, &ppIMFSample);
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 65, &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIMFSample);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    }
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v81, "RendererEffectWrapper::ProcessFrame", 629);
    VideoService = (*(__int64 (__fastcall **)(_QWORD, _QWORD, IMFSample *, _QWORD))(**((_QWORD **)this + 19) + 192LL))(
                     *((_QWORD *)this + 19),
                     v7,
                     v83,
                     0);
    if ( VideoService < 0 )
    {
      v44 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v44 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext(v44);
        if ( *((_DWORD *)v45 + 499) != VideoService )
          CallStackContext::TraceFailure(v45, "RendererEffectWrapper::ProcessFrame", 629, VideoService);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          73,
          &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
          this,
          VideoService);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
      goto LABEL_96;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
LABEL_35:
    if ( ++v7 >= (unsigned __int64)((__int64)(a2[1] - *a2) >> 3) )
      goto LABEL_36;
  }
  if ( !v9 )
    goto LABEL_35;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v81, "RendererEffectWrapper::ProcessFrame", 636);
  VideoService = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 19) + 192LL))(
                   *((_QWORD *)this + 19),
                   v7,
                   *(_QWORD *)(*a2 + 8LL * v7),
                   0);
  if ( VideoService >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
    goto LABEL_35;
  }
  v46 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v46 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v46 + 8) )
  {
    v47 = CallStackTracing::GetThreadRelativeContext(v46);
    if ( *((_DWORD *)v47 + 499) != VideoService )
      CallStackContext::TraceFailure(v47, "RendererEffectWrapper::ProcessFrame", 636, VideoService);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      this,
      VideoService);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
LABEL_252:
  if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 2) != 0 )
    McTemplateU0p_EventWriteTransfer(v17, MSVProc_EffectWrapper_ProcessFrame_Stop, this);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v81, "RendererEffectWrapper::ProcessFrame", 683);
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      87,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      (unsigned int)VideoService);
  if ( VideoService < 0 && *((_BYTE *)this + 144) )
  {
    RendererEffectWrapper::Clear(this);
    VideoService = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  return (unsigned int)VideoService;
}

```

## disassembly

```asm
0x1800b4524  mov     [rsp-38h+arg_0], rbx
0x1800b4529  push    rbp
0x1800b452a  push    rsi
0x1800b452b  push    rdi
0x1800b452c  push    r12
0x1800b452e  push    r13
0x1800b4530  push    r14
0x1800b4532  push    r15
0x1800b4534  mov     rbp, rsp
0x1800b4537  sub     rsp, 80h
0x1800b453e  mov     rdi, rcx
0x1800b4541  mov     [rbp+var_30], r8
0x1800b4545  lea     rcx, [rbp+var_30]
0x1800b4549  mov     rsi, r8
0x1800b454c  mov     r15, rdx
0x1800b454f  call    ?InternalAddRef@?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(void)
0x1800b4554  xor     r13d, r13d
0x1800b4557  xorps   xmm0, xmm0
0x1800b455a  test    byte ptr cs:Microsoft_Windows_MediaFoundation_MSVProcEnableBits, 2
0x1800b4561  movups  [rbp+var_28], xmm0
0x1800b4565  mov     [rbp+arg_10], r13d
0x1800b4569  movups  [rbp+var_18], xmm0
0x1800b456d  jz      short loc_1800B457E
0x1800b456f  mov     r8, rdi
0x1800b4572  lea     rdx, MSVProc_EffectWrapper_ProcessFrame_Start; "}"
0x1800b4579  call    McTemplateU0p_EventWriteTransfer
0x1800b457e  mov     rax, [r15+8]
0x1800b4582  mov     r12d, r13d
0x1800b4585  sub     rax, [r15]
0x1800b4588  mov     r14d, 1
0x1800b458e  sar     rax, 3
0x1800b4592  test    rax, rax
0x1800b4595  jz      loc_1800B4995
0x1800b459b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects> `wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl(void)'::`2'::impl
0x1800b45a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(void)
0x1800b45a7  mov     rcx, [r15]
0x1800b45aa  mov     ebx, r12d
0x1800b45ad  mov     r14, [rcx+rbx*8]
0x1800b45b1  test    al, al
0x1800b45b3  jz      loc_1800B4921
0x1800b45b9  test    r14, r14
0x1800b45bc  jz      loc_1800B4975
0x1800b45c2  cmp     [rdi+69h], r13b
0x1800b45c6  jnz     short loc_1800B45D2
0x1800b45c8  cmp     [rdi+68h], r13b
0x1800b45cc  jz      loc_1800B4975
0x1800b45d2  lea     rcx, [rbp+arg_18]
0x1800b45d6  mov     [rbp+arg_18], r14
0x1800b45da  call    ?InternalAddRef@?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(void)
0x1800b45df  cmp     [rdi+6Ch], r13d
0x1800b45e3  jnz     loc_1800B4757
0x1800b45e9  cmp     [rdi+68h], r13b
0x1800b45ed  jnz     loc_1800B48CA
0x1800b45f3  mov     r8d, 25Bh; int
0x1800b45f9  mov     [rbp+var_38], r13
0x1800b45fd  lea     rdx, aRenderereffect_1; "RendererEffectWrapper::ProcessFrame"
0x1800b4604  mov     [rbp+ppIMFSample], r13
0x1800b4608  lea     rcx, [rbp+arg_8]; this
0x1800b460c  mov     [rbp+var_40], r13
0x1800b4610  mov     [rbp+var_48], r13
0x1800b4614  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b4619  lea     rcx, [rbp+var_38]
0x1800b461d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4622  lea     rcx, [rdi+70h]; this
0x1800b4626  lea     r8, [rbp+var_38]; void **
0x1800b462a  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7; struct _GUID *
0x1800b4631  call    ?GetVideoService@CMFDXGIDeviceManagerHandle@MFD3D@@QEAAJAEBU_GUID@@PEAPEAX@Z; MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(_GUID const &,void * *)
0x1800b4636  mov     ebx, eax
0x1800b4638  test    eax, eax
0x1800b463a  js      loc_1800B4C7F
0x1800b4640  mov     rax, [r14]
0x1800b4643  lea     rcx, [rbp+var_40]
0x1800b4647  mov     rbx, [rax+140h]
0x1800b464e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4653  lea     r8, [rbp+var_40]
0x1800b4657  xor     edx, edx
0x1800b4659  mov     rcx, r14
0x1800b465c  mov     rax, rbx
0x1800b465f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4664  mov     ebx, eax
0x1800b4666  test    eax, eax
0x1800b4668  js      loc_1800B4C2C
0x1800b466e  lea     rcx, [rbp+var_48]
0x1800b4672  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4677  mov     rdx, [rbp+var_38]; struct ID3D12Device *
0x1800b467b  lea     r8, [rbp+var_48]; struct IUnknown **
0x1800b467f  mov     rcx, [rbp+var_40]; struct IUnknown *
0x1800b4683  call    ?CreateInstance@CMFDXGIBuffer11to12@MFD3D@@SAJPEAUIUnknown@@PEAUID3D12Device@@PEAPEAU3@@Z; MFD3D::CMFDXGIBuffer11to12::CreateInstance(IUnknown *,ID3D12Device *,IUnknown * *)
0x1800b4688  mov     ebx, eax
0x1800b468a  test    eax, eax
0x1800b468c  js      loc_1800B4BD2
0x1800b4692  lea     rcx, [rbp+ppIMFSample]
0x1800b4696  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b469b  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1800b469f  call    cs:__imp_MFCreateSample
0x1800b46a5  mov     ebx, eax
0x1800b46a7  test    eax, eax
0x1800b46a9  js      loc_1800B4B78
0x1800b46af  mov     rcx, [rbp+ppIMFSample]
0x1800b46b3  mov     rdx, [rbp+var_48]
0x1800b46b7  mov     rax, [rcx]
0x1800b46ba  mov     rax, [rax+150h]
0x1800b46c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b46c6  mov     ebx, eax
0x1800b46c8  test    eax, eax
0x1800b46ca  js      loc_1800B4B1E
0x1800b46d0  mov     rax, [r14]
0x1800b46d3  mov     rcx, r14
0x1800b46d6  mov     rdx, [rbp+ppIMFSample]
0x1800b46da  mov     rax, [rax+100h]
0x1800b46e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b46e6  mov     ebx, eax
0x1800b46e8  test    eax, eax
0x1800b46ea  js      loc_1800B4AC4
0x1800b46f0  lea     rdx, [rbp+ppIMFSample]
0x1800b46f4  lea     rcx, [rbp+arg_18]
0x1800b46f8  call    ??4?$ComPtr@UID3D11VideoProcessor@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(Microsoft::WRL::ComPtr<ID3D11VideoProcessor> const &)
0x1800b46fd  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800b4704  jb      short loc_1800B4725
0x1800b4706  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b470d  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800b4714  mov     edx, 41h ; 'A'
0x1800b4719  mov     rcx, [rcx+150h]
0x1800b4720  call    WPP_SF_
0x1800b4725  lea     rcx, [rbp+arg_8]; this
0x1800b4729  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b472e  lea     rcx, [rbp+var_48]
0x1800b4732  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4737  lea     rcx, [rbp+var_40]
0x1800b473b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4740  lea     rcx, [rbp+ppIMFSample]
0x1800b4744  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4749  lea     rcx, [rbp+var_38]
0x1800b474d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4752  jmp     loc_1800B48CA
0x1800b4757  cmp     dword ptr [rdi+6Ch], 1
0x1800b475b  jnz     loc_1800B48CA
0x1800b4761  cmp     [rdi+69h], r13b
0x1800b4765  jnz     loc_1800B48CA
0x1800b476b  mov     r8d, 26Bh; int
0x1800b4771  mov     [rbp+var_48], r13
0x1800b4775  lea     rdx, aRenderereffect_1; "RendererEffectWrapper::ProcessFrame"
0x1800b477c  mov     [rbp+ppIMFSample], r13
0x1800b4780  lea     rcx, [rbp+arg_8]; this
0x1800b4784  mov     [rbp+var_40], r13
0x1800b4788  mov     [rbp+var_38], r13
0x1800b478c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b4791  lea     rcx, [rbp+var_48]
0x1800b4795  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b479a  lea     rcx, [rdi+70h]; this
0x1800b479e  lea     r8, [rbp+var_48]; void **
0x1800b47a2  lea     rdx, _GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140; struct _GUID *
0x1800b47a9  call    ?GetVideoService@CMFDXGIDeviceManagerHandle@MFD3D@@QEAAJAEBU_GUID@@PEAPEAX@Z; MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(_GUID const &,void * *)
0x1800b47ae  mov     ebx, eax
0x1800b47b0  test    eax, eax
0x1800b47b2  js      loc_1800B4EE4
0x1800b47b8  mov     rax, [r14]
0x1800b47bb  lea     rcx, [rbp+var_40]
0x1800b47bf  mov     rbx, [rax+140h]
0x1800b47c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b47cb  lea     r8, [rbp+var_40]
0x1800b47cf  xor     edx, edx
0x1800b47d1  mov     rcx, r14
0x1800b47d4  mov     rax, rbx
0x1800b47d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47dc  mov     ebx, eax
0x1800b47de  test    eax, eax
0x1800b47e0  js      loc_1800B4E91
0x1800b47e6  lea     rcx, [rbp+var_38]
0x1800b47ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b47ef  mov     rdx, [rbp+var_48]; struct ID3D11Device *
0x1800b47f3  lea     r8, [rbp+var_38]; struct IUnknown **
0x1800b47f7  mov     rcx, [rbp+var_40]; struct IUnknown *
0x1800b47fb  call    ?CreateInstance@CMFDXGIBuffer12to11@MFD3D@@SAJPEAUIUnknown@@PEAUID3D11Device@@PEAPEAU3@@Z; MFD3D::CMFDXGIBuffer12to11::CreateInstance(IUnknown *,ID3D11Device *,IUnknown * *)
0x1800b4800  mov     ebx, eax
0x1800b4802  test    eax, eax
0x1800b4804  js      loc_1800B4E37
0x1800b480a  lea     rcx, [rbp+ppIMFSample]
0x1800b480e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4813  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1800b4817  call    cs:__imp_MFCreateSample
0x1800b481d  mov     ebx, eax
0x1800b481f  test    eax, eax
0x1800b4821  js      loc_1800B4DDD
0x1800b4827  mov     rcx, [rbp+ppIMFSample]
0x1800b482b  mov     rdx, [rbp+var_38]
0x1800b482f  mov     rax, [rcx]
0x1800b4832  mov     rax, [rax+150h]
0x1800b4839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b483e  mov     ebx, eax
0x1800b4840  test    eax, eax
0x1800b4842  js      loc_1800B4D83
0x1800b4848  mov     rax, [r14]
0x1800b484b  mov     rcx, r14
0x1800b484e  mov     rdx, [rbp+ppIMFSample]
0x1800b4852  mov     rax, [rax+100h]
0x1800b4859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b485e  mov     ebx, eax
0x1800b4860  test    eax, eax
0x1800b4862  js      loc_1800B4D29
0x1800b4868  lea     rdx, [rbp+ppIMFSample]
0x1800b486c  lea     rcx, [rbp+arg_18]
0x1800b4870  call    ??4?$ComPtr@UID3D11VideoProcessor@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(Microsoft::WRL::ComPtr<ID3D11VideoProcessor> const &)
0x1800b4875  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800b487c  jb      short loc_1800B489D
0x1800b487e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4885  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800b488c  mov     edx, 48h ; 'H'
0x1800b4891  mov     rcx, [rcx+150h]
0x1800b4898  call    WPP_SF_
0x1800b489d  lea     rcx, [rbp+arg_8]; this
0x1800b48a1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b48a6  lea     rcx, [rbp+var_38]
0x1800b48aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b48af  lea     rcx, [rbp+var_40]
0x1800b48b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b48b8  lea     rcx, [rbp+ppIMFSample]
0x1800b48bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b48c1  lea     rcx, [rbp+var_48]
0x1800b48c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b48ca  mov     r14d, 275h
0x1800b48d0  lea     rdx, aRenderereffect_1; "RendererEffectWrapper::ProcessFrame"
0x1800b48d7  mov     r8d, r14d; int
0x1800b48da  lea     rcx, [rbp+arg_8]; this
0x1800b48de  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b48e3  mov     rcx, [rdi+98h]
0x1800b48ea  xor     r9d, r9d
0x1800b48ed  mov     r8, [rbp+arg_18]
0x1800b48f1  mov     edx, r12d
0x1800b48f4  mov     rax, [rcx]
0x1800b48f7  mov     rax, [rax+0C0h]
0x1800b48fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4903  mov     ebx, eax
0x1800b4905  test    eax, eax
0x1800b4907  js      loc_1800B4F85
0x1800b490d  lea     rcx, [rbp+arg_8]; this
0x1800b4911  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b4916  lea     rcx, [rbp+arg_18]
0x1800b491a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b491f  jmp     short loc_1800B4975
0x1800b4921  test    r14, r14
0x1800b4924  jz      short loc_1800B4975
0x1800b4926  mov     r14d, 27Ch
0x1800b492c  lea     rdx, aRenderereffect_1; "RendererEffectWrapper::ProcessFrame"
0x1800b4933  mov     r8d, r14d; int
0x1800b4936  lea     rcx, [rbp+arg_8]; this
0x1800b493a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b493f  mov     rcx, [rdi+98h]
0x1800b4946  xor     r9d, r9d
0x1800b4949  mov     r8, [r15]
0x1800b494c  mov     edx, r12d
0x1800b494f  mov     rax, [rcx]
0x1800b4952  mov     r8, [r8+rbx*8]
0x1800b4956  mov     rax, [rax+0C0h]
0x1800b495d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4962  mov     ebx, eax
0x1800b4964  test    eax, eax
0x1800b4966  js      loc_1800B4FFF
0x1800b496c  lea     rcx, [rbp+arg_8]; this
0x1800b4970  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b4975  mov     rcx, [r15+8]
0x1800b4979  mov     r14d, 1
0x1800b497f  sub     rcx, [r15]
0x1800b4982  add     r12d, r14d
0x1800b4985  sar     rcx, 3
0x1800b4989  mov     eax, r12d
0x1800b498c  cmp     rax, rcx
0x1800b498f  jb      loc_1800B459B
0x1800b4995  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects> `wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl(void)'::`2'::impl
0x1800b499c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(void)
0x1800b49a1  test    al, al
0x1800b49a3  jz      loc_1800B5685
0x1800b49a9  test    rsi, rsi
0x1800b49ac  jz      loc_1800B5685
0x1800b49b2  mov     al, [rdi+69h]
0x1800b49b5  test    al, al
0x1800b49b7  jnz     short loc_1800B49C3
0x1800b49b9  cmp     [rdi+68h], r13b
0x1800b49bd  jz      loc_1800B5685
0x1800b49c3  cmp     [rdi+6Ch], r13d
0x1800b49c7  jnz     loc_1800B5302
0x1800b49cd  cmp     [rdi+68h], r13b
0x1800b49d1  jnz     loc_1800B5685
0x1800b49d7  mov     r12d, 28Bh
0x1800b49dd  mov     [rbp+var_48], r13
0x1800b49e1  lea     r15, aRenderereffect_1; "RendererEffectWrapper::ProcessFrame"
0x1800b49e8  mov     [rbp+arg_18], r13
0x1800b49ec  mov     r8d, r12d; int
0x1800b49ef  mov     [rbp+var_40], r13
0x1800b49f3  mov     rdx, r15; char *
0x1800b49f6  mov     [rbp+var_38], r13
0x1800b49fa  lea     rcx, [rbp+arg_8]; this
0x1800b49fe  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b4a03  lea     rcx, [rbp+var_48]
0x1800b4a07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4a0c  lea     rcx, [rdi+70h]; this
0x1800b4a10  lea     r8, [rbp+var_48]; void **
0x1800b4a14  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7; struct _GUID *
0x1800b4a1b  call    ?GetVideoService@CMFDXGIDeviceManagerHandle@MFD3D@@QEAAJAEBU_GUID@@PEAPEAX@Z; MFD3D::CMFDXGIDeviceManagerHandle::GetVideoService(_GUID const &,void * *)
0x1800b4a20  mov     ebx, eax
  ... truncated ...
```
