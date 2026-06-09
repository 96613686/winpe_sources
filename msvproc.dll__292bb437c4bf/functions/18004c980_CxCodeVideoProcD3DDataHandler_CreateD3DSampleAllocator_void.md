# CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator(void)

- ea: `0x18004c980`
- end: `0x18004d4ac`
- name: `?CreateD3DSampleAllocator@CxCodeVideoProcD3DDataHandler@@IEAAJXZ`
- size: `2860`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DDataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009b2c`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000ac20`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180014be0`
- `0x18003639c`
- `0x18004c980`
- `0x180063110`
- `0x18006b8d0`
- `0x180072bd0`
- `0x180072c70`
- `0x18007355c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18004cb07`
- `MFPlat!MFCreateAttributes` at `0x18004cb07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c9fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cb23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cbd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cc88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cd3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cf15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cfd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d0b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d15f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d3e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c9fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cb23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cbd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cc88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cd3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cf15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cfd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d0b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d15f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d3e6`

## string_xrefs

- `0x18004c997`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004ca54`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004cb7a`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004cc29`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004ccdf`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004cd95`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004ce95`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004cf6c`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004d030`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004d109`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004d1b6`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004d32f`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`
- `0x18004d43d`: `CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator(CxCodeVideoProcD3DDataHandler *this)
{
  CMFTMultiStreamTypeHandler *v2; // rcx
  unsigned int v3; // edx
  struct IMFMediaType *v4; // r15
  __int64 v5; // rsi
  HRESULT v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  int v11; // eax
  _DWORD *v12; // rcx
  int v13; // ebx
  int v14; // ebx
  unsigned int v15; // r14d
  unsigned int v16; // r12d
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  unsigned int v29; // esi
  CxCodeVideoProcMFTDataHandler *v30; // rbx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rbx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v61; // [rsp+A0h] [rbp+48h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v63; // [rsp+B0h] [rbp+58h] BYREF
  struct IMFAttributes *v64; // [rsp+B8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v61,
    "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator",
    3785);
  v2 = (CMFTMultiStreamTypeHandler *)*((_QWORD *)this + 3);
  ppMFAttributes = 0;
  v64 = 0;
  v4 = CMFTMultiStreamTypeHandler::POutputType(v2, v3);
  v5 = *(_QWORD *)(*((_QWORD *)this + 4) + 232LL);
  v6 = (*(__int64 (__fastcall **)(CxCodeVideoProcD3DDataHandler *, struct IMFMediaType *, __int64))(*(_QWORD *)this
                                                                                                  + 216LL))(
         this,
         v4,
         v5);
  if ( v6 < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator",
          3796,
          v6);
    }
    if ( g_wppLevels )
    {
      v10 = 218;
LABEL_158:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v6);
      goto LABEL_159;
    }
    goto LABEL_159;
  }
  v11 = MFGetAttributeUINT32(v5, MF_SA_D3D11_BINDFLAGS, 0);
  v12 = (_DWORD *)*((_QWORD *)this + 2);
  if ( v12[248] || v12[536] || (v13 = 128, (int)v12[275] <= 29) )
    v13 = 32;
  v14 = v11 | v13;
  v15 = MFGetAttributeUINT32(v5, &MF_SA_REQUIRED_SAMPLE_COUNT, 10);
  if ( v15 <= 0xA )
    v15 = 10;
  v16 = v14 | 8;
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 892LL) )
    v16 = v14;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
  v6 = MFCreateAttributes(&ppMFAttributes, 4u);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v5 + 256LL))(v5, ppMFAttributes);
    if ( v6 < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v6 )
          CallStackContext::TraceFailure(v22, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3821, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 220;
        goto LABEL_158;
      }
      goto LABEL_159;
    }
    v6 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_D3D11_USAGE,
           0);
    if ( v6 < 0 )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v6 )
          CallStackContext::TraceFailure(v25, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3822, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 221;
        goto LABEL_158;
      }
      goto LABEL_159;
    }
    v6 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_D3D11_BINDFLAGS,
           v16);
    if ( v6 < 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v6 )
          CallStackContext::TraceFailure(v28, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3823, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 222;
        goto LABEL_158;
      }
      goto LABEL_159;
    }
    v29 = MFGetAttributeUINT32(v4, MF_MT_SECURE, 0);
    if ( !v29 )
    {
      v30 = (CxCodeVideoProcMFTDataHandler *)*((_QWORD *)this + 4);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      if ( (int)CxCodeVideoProcMFTDataHandler::GetAttributes(v30, &v64) >= 0 )
        v29 = MFGetAttributeUINT32(v64, MFT_USING_HARDWARE_DRM, 0);
    }
    v6 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_D3D11_HW_PROTECTED,
           v29);
    if ( v6 < 0 )
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
        if ( *((_DWORD *)v33 + 499) != v6 )
          CallStackContext::TraceFailure(v33, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3831, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 223;
        goto LABEL_158;
      }
      goto LABEL_159;
    }
    v34 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v34 + 356) )
    {
      if ( *(_DWORD *)(v34 + 744) == 1 )
      {
        v6 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               MF_SA_BUFFERS_PER_SAMPLE,
               2);
        if ( v6 < 0 )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != v6 )
              CallStackContext::TraceFailure(v37, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3836, v6);
          }
          if ( g_wppLevels )
          {
            v10 = 224;
            goto LABEL_158;
          }
          goto LABEL_159;
        }
      }
    }
    if ( !*((_QWORD *)this + 5) )
    {
      v61 = 0;
      v63 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      v6 = dlMFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, &v61);
      if ( v6 < 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != v6 )
            CallStackContext::TraceFailure(v40, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3848, v6);
        }
        if ( !g_wppLevels )
          goto LABEL_104;
        v41 = 225;
LABEL_103:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v41, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v6);
LABEL_104:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
        goto LABEL_159;
      }
      v6 = Microsoft::WRL::ComPtr<IMFDXGIDeviceManager>::As<IUnknown>(*((_QWORD *)this + 4) + 3112LL, &v63);
      if ( v6 < 0 )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != v6 )
            CallStackContext::TraceFailure(v44, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3850, v6);
        }
        if ( !g_wppLevels )
          goto LABEL_104;
        v41 = 226;
        goto LABEL_103;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 24LL))(v61, v63);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)v47 + 499) != v6 )
            CallStackContext::TraceFailure(v47, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3851, v6);
        }
        if ( !g_wppLevels )
          goto LABEL_104;
        v41 = 227;
        goto LABEL_103;
      }
      v48 = *((_QWORD *)this + 5);
      v49 = v61;
      v61 = 0;
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      *((_QWORD *)this + 5) = v49;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    }
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    {
      MFGetAttributeUINT32(ppMFAttributes, MF_SA_D3D11_SHARED, 0);
      MFGetAttributeUINT32(ppMFAttributes, MF_SA_D3D11_BINDFLAGS, 0);
      WPP_SF_qdDdddd(*((_QWORD *)WPP_GLOBAL_Control + 42), v50, v51, this);
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, IMFAttributes *, struct IMFMediaType *))(**((_QWORD **)this + 5) + 56LL))(
           *((_QWORD *)this + 5),
           1,
           v15,
           ppMFAttributes,
           v4);
    if ( v6 < 0 && v16 != 32 )
    {
      v6 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
             ppMFAttributes,
             MF_SA_D3D11_BINDFLAGS,
             32);
      if ( v6 >= 0 )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        {
          MFGetAttributeUINT32(ppMFAttributes, MF_SA_D3D11_SHARED, 0);
          MFGetAttributeUINT32(ppMFAttributes, MF_SA_D3D11_BINDFLAGS, 0);
          WPP_SF_qdDddd(*((_QWORD *)WPP_GLOBAL_Control + 42), v55, v56, this);
        }
        v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, IMFAttributes *, struct IMFMediaType *))(**((_QWORD **)this + 5) + 56LL))(
               *((_QWORD *)this + 5),
               1,
               v15,
               ppMFAttributes,
               v4);
        if ( v6 < 0 )
        {
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v58;
            if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
            {
              v57 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v57 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v57 + 8) )
          {
            v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
            if ( *((_DWORD *)v59 + 499) != v6 )
              CallStackContext::TraceFailure(v59, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3876, v6);
          }
          if ( g_wppLevels )
          {
            v10 = 231;
            goto LABEL_158;
          }
        }
      }
      else
      {
        v52 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
          {
            v52 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v52 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v52 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
          if ( *((_DWORD *)v54 + 499) != v6 )
            CallStackContext::TraceFailure(v54, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3867, v6);
        }
        if ( g_wppLevels )
        {
          v10 = 229;
          goto LABEL_158;
        }
      }
    }
    goto LABEL_159;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != v6 )
      CallStackContext::TraceFailure(v19, "CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator", 3820, v6);
  }
  if ( g_wppLevels )
  {
    v10 = 219;
    goto LABEL_158;
  }
LABEL_159:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v61);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004c980  push    rbp
0x18004c982  push    rbx
0x18004c983  push    rsi
0x18004c984  push    rdi
0x18004c985  push    r12
0x18004c987  push    r13
0x18004c989  push    r14
0x18004c98b  push    r15
0x18004c98d  mov     rbp, rsp
0x18004c990  sub     rsp, 58h
0x18004c994  mov     rdi, rcx
0x18004c997  lea     rdx, aCxcodevideopro_75; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x18004c99e  lea     rcx, [rbp+arg_0]; this
0x18004c9a2  mov     r8d, 0EC9h; int
0x18004c9a8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004c9ad  mov     rcx, [rdi+18h]; this
0x18004c9b1  xor     r13d, r13d
0x18004c9b4  mov     [rbp+ppMFAttributes], r13
0x18004c9b8  mov     [rbp+arg_18], r13
0x18004c9bc  call    ?POutputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::POutputType(ulong)
0x18004c9c1  mov     rcx, [rdi+20h]
0x18004c9c5  mov     r15, rax
0x18004c9c8  mov     rdx, r15
0x18004c9cb  mov     rsi, [rcx+0E8h]
0x18004c9d2  mov     rcx, [rdi]
0x18004c9d5  mov     r8, rsi
0x18004c9d8  mov     rax, [rcx+0D8h]
0x18004c9df  mov     rcx, rdi
0x18004c9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9e7  mov     ebx, eax
0x18004c9e9  test    eax, eax
0x18004c9eb  jns     loc_18004CA80
0x18004c9f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c9f8  test    rcx, rcx
0x18004c9fb  jnz     short loc_18004CA3E
0x18004c9fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ca03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ca0a  mov     rcx, rax
0x18004ca0d  test    rax, rax
0x18004ca10  jz      short loc_18004CA30
0x18004ca12  mov     rax, [rax]
0x18004ca15  mov     edx, 7F0h
0x18004ca1a  mov     rax, [rax+8]
0x18004ca1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca23  test    eax, eax
0x18004ca25  jz      short loc_18004CA30
0x18004ca27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ca2e  jmp     short loc_18004CA3E
0x18004ca30  lea     rcx, qword_180153440; this
0x18004ca37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ca3e  cmp     [rcx+8], r13b
0x18004ca42  jz      short loc_18004CA69
0x18004ca44  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ca49  cmp     [rax+7CCh], ebx
0x18004ca4f  jz      short loc_18004CA69
0x18004ca51  mov     r9d, ebx; int
0x18004ca54  lea     rdx, aCxcodevideopro_75; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x18004ca5b  mov     r8d, 0ED4h; int
0x18004ca61  mov     rcx, rax; this
0x18004ca64  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ca69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ca70  jb      loc_18004D47E
0x18004ca76  mov     edx, 0DAh
0x18004ca7b  jmp     loc_18004D460
0x18004ca80  xor     r8d, r8d
0x18004ca83  lea     rdx, MF_SA_D3D11_BINDFLAGS
0x18004ca8a  mov     rcx, rsi
0x18004ca8d  call    MFGetAttributeUINT32
0x18004ca92  mov     rcx, [rdi+10h]
0x18004ca96  cmp     [rcx+3E0h], r13d
0x18004ca9d  jnz     short loc_18004CAB6
0x18004ca9f  cmp     [rcx+860h], r13d
0x18004caa6  jnz     short loc_18004CAB6
0x18004caa8  cmp     dword ptr [rcx+44Ch], 1Dh
0x18004caaf  mov     ebx, 80h
0x18004cab4  jg      short loc_18004CABB
0x18004cab6  mov     ebx, 20h ; ' '
0x18004cabb  mov     r12d, 0Ah
0x18004cac1  lea     rdx, MF_SA_REQUIRED_SAMPLE_COUNT
0x18004cac8  mov     r8d, r12d
0x18004cacb  mov     rcx, rsi
0x18004cace  or      ebx, eax
0x18004cad0  call    MFGetAttributeUINT32
0x18004cad5  cmp     eax, r12d
0x18004cad8  lea     rcx, [rbp+ppMFAttributes]
0x18004cadc  mov     r14d, eax
0x18004cadf  mov     rax, [rdi+10h]
0x18004cae3  cmovbe  r14d, r12d
0x18004cae7  mov     r12d, ebx
0x18004caea  or      r12d, 8
0x18004caee  cmp     [rax+37Ch], r13d
0x18004caf5  cmovz   r12d, ebx
0x18004caf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004cafe  mov     edx, 4; cInitialSize
0x18004cb03  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18004cb07  call    cs:__imp_MFCreateAttributes
0x18004cb0d  mov     ebx, eax
0x18004cb0f  test    eax, eax
0x18004cb11  jns     loc_18004CBA6
0x18004cb17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb1e  test    rcx, rcx
0x18004cb21  jnz     short loc_18004CB64
0x18004cb23  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cb29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb30  mov     rcx, rax
0x18004cb33  test    rax, rax
0x18004cb36  jz      short loc_18004CB56
0x18004cb38  mov     rax, [rax]
0x18004cb3b  mov     edx, 7F0h
0x18004cb40  mov     rax, [rax+8]
0x18004cb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb49  test    eax, eax
0x18004cb4b  jz      short loc_18004CB56
0x18004cb4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb54  jmp     short loc_18004CB64
0x18004cb56  lea     rcx, qword_180153440; this
0x18004cb5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cb64  cmp     [rcx+8], r13b
0x18004cb68  jz      short loc_18004CB8F
0x18004cb6a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cb6f  cmp     [rax+7CCh], ebx
0x18004cb75  jz      short loc_18004CB8F
0x18004cb77  mov     r9d, ebx; int
0x18004cb7a  lea     rdx, aCxcodevideopro_75; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x18004cb81  mov     r8d, 0EECh; int
0x18004cb87  mov     rcx, rax; this
0x18004cb8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cb8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cb96  jb      loc_18004D47E
0x18004cb9c  mov     edx, 0DBh
0x18004cba1  jmp     loc_18004D460
0x18004cba6  mov     rax, [rsi]
0x18004cba9  mov     rcx, rsi
0x18004cbac  mov     rdx, [rbp+ppMFAttributes]
0x18004cbb0  mov     rax, [rax+100h]
0x18004cbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbbc  mov     ebx, eax
0x18004cbbe  test    eax, eax
0x18004cbc0  jns     loc_18004CC55
0x18004cbc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cbcd  test    rcx, rcx
0x18004cbd0  jnz     short loc_18004CC13
0x18004cbd2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cbd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cbdf  mov     rcx, rax
0x18004cbe2  test    rax, rax
0x18004cbe5  jz      short loc_18004CC05
0x18004cbe7  mov     rax, [rax]
0x18004cbea  mov     edx, 7F0h
0x18004cbef  mov     rax, [rax+8]
0x18004cbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbf8  test    eax, eax
0x18004cbfa  jz      short loc_18004CC05
0x18004cbfc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc03  jmp     short loc_18004CC13
0x18004cc05  lea     rcx, qword_180153440; this
0x18004cc0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc13  cmp     [rcx+8], r13b
0x18004cc17  jz      short loc_18004CC3E
0x18004cc19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cc1e  cmp     [rax+7CCh], ebx
0x18004cc24  jz      short loc_18004CC3E
0x18004cc26  mov     r9d, ebx; int
0x18004cc29  lea     rdx, aCxcodevideopro_75; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x18004cc30  mov     r8d, 0EEDh; int
0x18004cc36  mov     rcx, rax; this
0x18004cc39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cc3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cc45  jb      loc_18004D47E
0x18004cc4b  mov     edx, 0DCh
0x18004cc50  jmp     loc_18004D460
0x18004cc55  mov     rcx, [rbp+ppMFAttributes]
0x18004cc59  lea     rdx, MF_SA_D3D11_USAGE
0x18004cc60  xor     r8d, r8d
0x18004cc63  mov     rax, [rcx]
0x18004cc66  mov     rax, [rax+0A8h]
0x18004cc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc72  mov     ebx, eax
0x18004cc74  test    eax, eax
0x18004cc76  jns     loc_18004CD0B
0x18004cc7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc83  test    rcx, rcx
0x18004cc86  jnz     short loc_18004CCC9
0x18004cc88  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cc8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cc95  mov     rcx, rax
0x18004cc98  test    rax, rax
0x18004cc9b  jz      short loc_18004CCBB
0x18004cc9d  mov     rax, [rax]
0x18004cca0  mov     edx, 7F0h
0x18004cca5  mov     rax, [rax+8]
0x18004cca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccae  test    eax, eax
0x18004ccb0  jz      short loc_18004CCBB
0x18004ccb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ccb9  jmp     short loc_18004CCC9
0x18004ccbb  lea     rcx, qword_180153440; this
0x18004ccc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ccc9  cmp     [rcx+8], r13b
0x18004cccd  jz      short loc_18004CCF4
0x18004cccf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ccd4  cmp     [rax+7CCh], ebx
0x18004ccda  jz      short loc_18004CCF4
0x18004ccdc  mov     r9d, ebx; int
0x18004ccdf  lea     rdx, aCxcodevideopro_75; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x18004cce6  mov     r8d, 0EEEh; int
0x18004ccec  mov     rcx, rax; this
0x18004ccef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ccf4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ccfb  jb      loc_18004D47E
0x18004cd01  mov     edx, 0DDh
0x18004cd06  jmp     loc_18004D460
0x18004cd0b  mov     rcx, [rbp+ppMFAttributes]
0x18004cd0f  lea     rdx, MF_SA_D3D11_BINDFLAGS
0x18004cd16  mov     r8d, r12d
0x18004cd19  mov     rax, [rcx]
0x18004cd1c  mov     rax, [rax+0A8h]
0x18004cd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd28  mov     ebx, eax
0x18004cd2a  test    eax, eax
0x18004cd2c  jns     loc_18004CDC1
0x18004cd32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd39  test    rcx, rcx
0x18004cd3c  jnz     short loc_18004CD7F
0x18004cd3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cd44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd4b  mov     rcx, rax
0x18004cd4e  test    rax, rax
0x18004cd51  jz      short loc_18004CD71
0x18004cd53  mov     rax, [rax]
0x18004cd56  mov     edx, 7F0h
0x18004cd5b  mov     rax, [rax+8]
0x18004cd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd64  test    eax, eax
0x18004cd66  jz      short loc_18004CD71
0x18004cd68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd6f  jmp     short loc_18004CD7F
0x18004cd71  lea     rcx, qword_180153440; this
0x18004cd78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd7f  cmp     [rcx+8], r13b
0x18004cd83  jz      short loc_18004CDAA
0x18004cd85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cd8a  cmp     [rax+7CCh], ebx
0x18004cd90  jz      short loc_18004CDAA
0x18004cd92  mov     r9d, ebx; int
0x18004cd95  lea     rdx, aCxcodevideopro_75; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x18004cd9c  mov     r8d, 0EEFh; int
0x18004cda2  mov     rcx, rax; this
0x18004cda5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cdaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cdb1  jb      loc_18004D47E
0x18004cdb7  mov     edx, 0DEh
0x18004cdbc  jmp     loc_18004D460
0x18004cdc1  xor     r8d, r8d
0x18004cdc4  lea     rdx, MF_MT_SECURE
0x18004cdcb  mov     rcx, r15
0x18004cdce  call    MFGetAttributeUINT32
0x18004cdd3  mov     esi, eax
0x18004cdd5  test    eax, eax
0x18004cdd7  jnz     short loc_18004CE0B
0x18004cdd9  mov     rbx, [rdi+20h]
0x18004cddd  lea     rcx, [rbp+arg_18]
0x18004cde1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004cde6  lea     rdx, [rbp+arg_18]; struct IMFAttributes **
0x18004cdea  mov     rcx, rbx; this
0x18004cded  call    ?GetAttributes@CxCodeVideoProcMFTDataHandler@@UEAAJPEAPEAUIMFAttributes@@@Z; CxCodeVideoProcMFTDataHandler::GetAttributes(IMFAttributes * *)
0x18004cdf2  test    eax, eax
0x18004cdf4  js      short loc_18004CE0B
0x18004cdf6  mov     rcx, [rbp+arg_18]
0x18004cdfa  lea     rdx, MFT_USING_HARDWARE_DRM
0x18004ce01  xor     r8d, r8d
0x18004ce04  call    MFGetAttributeUINT32
0x18004ce09  mov     esi, eax
0x18004ce0b  mov     rcx, [rbp+ppMFAttributes]
0x18004ce0f  lea     rdx, MF_SA_D3D11_HW_PROTECTED
0x18004ce16  mov     r8d, esi
0x18004ce19  mov     rax, [rcx]
0x18004ce1c  mov     rax, [rax+0A8h]
0x18004ce23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce28  mov     ebx, eax
0x18004ce2a  test    eax, eax
0x18004ce2c  jns     loc_18004CEC1
0x18004ce32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce39  test    rcx, rcx
0x18004ce3c  jnz     short loc_18004CE7F
0x18004ce3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ce44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce4b  mov     rcx, rax
0x18004ce4e  test    rax, rax
0x18004ce51  jz      short loc_18004CE71
0x18004ce53  mov     rax, [rax]
0x18004ce56  mov     edx, 7F0h
0x18004ce5b  mov     rax, [rax+8]
0x18004ce5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce64  test    eax, eax
0x18004ce66  jz      short loc_18004CE71
0x18004ce68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce6f  jmp     short loc_18004CE7F
0x18004ce71  lea     rcx, qword_180153440; this
0x18004ce78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
