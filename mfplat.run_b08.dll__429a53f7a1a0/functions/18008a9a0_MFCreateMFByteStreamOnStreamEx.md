# MFCreateMFByteStreamOnStreamEx

- ea: `0x18008a9a0`
- end: `0x18008b7e0`
- name: `MFCreateMFByteStreamOnStreamEx`
- size: `3648`
- prototype: `HRESULT __stdcall(IUnknown *punkStream, IMFByteStream **ppByteStream)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180004870`
- `0x180011454`
- `0x180017860`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003c574`
- `0x180040cb0`
- `0x18008a9a0`
- `0x1800f5a14`
- `0x1801012ec`
- `0x18011fff0`
- `0x180120030`
- `0x1801250c8`
- `0x18017bfa4`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008b3b3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008b494`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008b3b3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008b494`

## string_xrefs

- `0x18008a9bf`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008af53`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b02c`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b102`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b1d6`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b2c8`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b375`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b458`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b532`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b5e8`: `MFCreateMFByteStreamOnStreamEx`
- `0x18008b697`: `MFCreateMFByteStreamOnStreamEx`

## pseudocode

```c
HRESULT __stdcall MFCreateMFByteStreamOnStreamEx(IUnknown *punkStream, IMFByteStream **ppByteStream)
{
  WCHAR *v4; // r13
  CallStackTracing *v5; // rcx
  int Instance; // esi
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, const IID *, GUID *, struct IMFByteStream **); // rbx
  struct IMFByteStream *v14; // rbx
  HRESULT (__stdcall *v15)(IMFByteStream *, const IID *const, void **); // rdi
  struct IMFAttributes *v16; // rdx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  HRESULT (__fastcall *v22)(IUnknown *, const _GUID *, void **); // rbx
  int v23; // eax
  HRESULT (__fastcall *v24)(IUnknown *, const _GUID *, void **); // rbx
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  HRESULT (__fastcall *v28)(IUnknown *, const _GUID *, void **); // rbx
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  HRESULT (__fastcall *v31)(IUnknown *, const _GUID *, void **); // rbx
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  HRESULT (__fastcall *v34)(IUnknown *, const _GUID *, void **); // rbx
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  HRESULT (__fastcall *v37)(IUnknown *, const _GUID *, void **); // rbx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, GUID *, __int64 *); // rbx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  DWORD FinalPathNameByHandleW; // eax
  DWORD v45; // ebx
  WCHAR *v46; // rax
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  IMFByteStream *v49; // rdi
  HRESULT (__stdcall *v50)(IMFByteStream *, const IID *const, void **); // rbx
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  struct IStream *v60; // rcx
  __int64 v61; // rcx
  struct Windows::Storage::Streams::IInputStream *v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v66; // [rsp+30h] [rbp-39h] BYREF
  __int64 v67; // [rsp+38h] [rbp-31h] BYREF
  struct IUnknown *v68; // [rsp+40h] [rbp-29h] BYREF
  __int64 v69; // [rsp+48h] [rbp-21h] BYREF
  __int64 v70; // [rsp+50h] [rbp-19h] BYREF
  struct IStream *v71; // [rsp+58h] [rbp-11h] BYREF
  struct Windows::Storage::Streams::IInputStream *v72; // [rsp+60h] [rbp-9h] BYREF
  __int64 v73; // [rsp+68h] [rbp-1h] BYREF
  __int64 v74; // [rsp+70h] [rbp+7h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v76; // [rsp+80h] [rbp+17h] BYREF
  _QWORD v77[7]; // [rsp+88h] [rbp+1Fh] BYREF
  CallStackScopeTrace v78; // [rsp+D8h] [rbp+6Fh] BYREF
  struct IMFByteStream *v79; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v80; // [rsp+E8h] [rbp+7Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v78, "MFCreateMFByteStreamOnStreamEx", 104);
  v73 = 0;
  v4 = 0;
  v66 = 0;
  v72 = 0;
  v74 = 0;
  v71 = 0;
  v70 = 0;
  v80 = 0;
  v69 = 0;
  hFile = 0;
  v78 = 0;
  if ( !ppByteStream )
  {
    v5 = CallStackTracing::s_wpInstance;
    Instance = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v5->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFCreateMFByteStreamOnStreamEx", 123, -2147467261);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids,
        0,
        -2147467261);
    goto LABEL_165;
  }
  *ppByteStream = 0;
  if ( !punkStream )
  {
    v8 = CallStackTracing::s_wpInstance;
    Instance = -2147024809;
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
      if ( v9->m_result != -2147024809 )
        CallStackContext::TraceFailure(v9, "MFCreateMFByteStreamOnStreamEx", 126, -2147024809);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v10 = 12;
LABEL_164:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids,
        0,
        -2147024809);
      goto LABEL_165;
    }
    goto LABEL_165;
  }
  QueryInterface = punkStream->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  if ( QueryInterface(punkStream, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, (void **)&v73) >= 0 )
  {
    v79 = 0;
    v12 = v73;
    v13 = *(int (__fastcall **)(__int64, const IID *, GUID *, struct IMFByteStream **))(*(_QWORD *)v73 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    if ( v13(v12, &MF_WRAPPED_OBJECT, &GUID_ad4c1b00_4bf7_422f_9175_756693d9130d, &v79) >= 0 )
    {
      v14 = v79;
      v67 = 0;
      Instance = 0;
      v68 = 0;
      v15 = v79->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      if ( ((int (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))v15)(
             v14,
             &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
             &v67) >= 0
        && (unsigned int)MFGetAttributeUINT32(v67, &MF_BYTESTREAM_PROXY, 0) )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
        Instance = CMFByteStreamProxy::CreateInstance(v79, v16, &v68);
        if ( Instance < 0 )
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
            if ( v18->m_result != Instance )
              CallStackContext::TraceFailure(v18, "MFCreateMFByteStreamOnStreamEx", 150, Instance);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_36;
          v19 = 13;
LABEL_35:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            &WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids,
            0,
            Instance);
LABEL_36:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
          goto LABEL_165;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
        Instance = v68->QueryInterface(v68, &GUID_ad4c1b00_4bf7_422f_9175_756693d9130d, (void **)&v79);
        if ( Instance < 0 )
        {
          v20 = CallStackTracing::s_wpInstance;
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
            if ( v21->m_result != Instance )
              CallStackContext::TraceFailure(v21, "MFCreateMFByteStreamOnStreamEx", 151, Instance);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_36;
          v19 = 14;
          goto LABEL_35;
        }
      }
      v22 = punkStream->QueryInterface;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      if ( v22(punkStream, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, (void **)&v66) >= 0 )
      {
        v76 = 0;
        v77[0] = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 80LL))(v66, &v76);
        ((void (__fastcall *)(struct IMFByteStream *, _QWORD *))v79->lpVtbl->GetCurrentPosition)(v79, v77);
        if ( v77[0] != v76 )
          ((void (__fastcall *)(struct IMFByteStream *))v79->lpVtbl->SetCurrentPosition)(v79);
      }
      *ppByteStream = v79;
      v79 = 0;
      goto LABEL_36;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  }
  v23 = MFCreateMFByteStreamFromHandleProvider(punkStream, ppByteStream);
  Instance = v23;
  if ( v23 >= 0 )
  {
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids, punkStream);
    goto LABEL_165;
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 4u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids,
      punkStream,
      v23);
  v24 = punkStream->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  if ( v24(punkStream, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, (void **)&v66) >= 0 )
  {
    Instance = CMFByteStreamOnWinRTStream::CreateInstance(0, punkStream, ppByteStream);
    if ( Instance < 0 )
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
        if ( v26->m_result != Instance )
          CallStackContext::TraceFailure(v26, "MFCreateMFByteStreamOnStreamEx", 215, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 21;
      goto LABEL_68;
    }
    goto LABEL_102;
  }
  v28 = punkStream->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  if ( v28(punkStream, &GUID_905a0fe2_bc53_11df_8c49_001e4fc686da, (void **)&v72) >= 0 )
  {
    Instance = MFCreateMFByteStreamOnInputStream(v72, ppByteStream);
    if ( Instance < 0 )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v29->m_fEnabled )
      {
        v30 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( v30->m_result != Instance )
          CallStackContext::TraceFailure(v30, "MFCreateMFByteStreamOnStreamEx", 219, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 22;
      goto LABEL_68;
    }
    goto LABEL_102;
  }
  v31 = punkStream->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  if ( v31(punkStream, &GUID_905a0fe6_bc53_11df_8c49_001e4fc686da, (void **)&v74) >= 0 )
  {
    Instance = CMFByteStreamOnWinRTStream::CreateInstance(1, punkStream, ppByteStream);
    if ( Instance < 0 )
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
        if ( v33->m_result != Instance )
          CallStackContext::TraceFailure(v33, "MFCreateMFByteStreamOnStreamEx", 225, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 23;
      goto LABEL_68;
    }
    goto LABEL_102;
  }
  v34 = punkStream->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  if ( v34(punkStream, &GUID_0000000c_0000_0000_c000_000000000046, (void **)&v71) >= 0 )
  {
    Instance = MFCreateMFByteStreamOnIStreamWithFlags(v71, MF_CREATESTREAM_FLAG_NONE);
    if ( Instance < 0 )
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
        if ( v36->m_result != Instance )
          CallStackContext::TraceFailure(v36, "MFCreateMFByteStreamOnStreamEx", 229, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 24;
      goto LABEL_68;
    }
LABEL_102:
    v37 = punkStream->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    if ( v37(punkStream, &GUID_bfb02fed_4c71_40e1_b4f3_ce99c2ff0542, (void **)&v70) < 0 )
      goto LABEL_165;
    v38 = v70;
    v39 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v70 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    Instance = v39(v38, &GUID_5e0ebc87_bece_4f2a_8d36_3673758f6c55, &v80);
    if ( Instance < 0 )
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
        if ( v41->m_result != Instance )
          CallStackContext::TraceFailure(v41, "MFCreateMFByteStreamOnStreamEx", 240, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 26;
      goto LABEL_68;
    }
    Instance = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v80 + 24LL))(v80, &hFile);
    if ( Instance < 0 )
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
        if ( v43->m_result != Instance )
          CallStackContext::TraceFailure(v43, "MFCreateMFByteStreamOnStreamEx", 241, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 27;
      goto LABEL_68;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0xAu);
    v45 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      goto LABEL_154;
    v78 = (CallStackScopeTrace)1;
    v46 = (WCHAR *)operator new(saturated_mul(FinalPathNameByHandleW + 1, 2u));
    v4 = v46;
    if ( !v46 )
    {
      v47 = CallStackTracing::s_wpInstance;
      Instance = -2147024882;
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
        if ( v48->m_result != -2147024882 )
          CallStackContext::TraceFailure(v48, "MFCreateMFByteStreamOnStreamEx", 250, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 28;
      goto LABEL_68;
    }
    *v46 = 0;
    GetFinalPathNameByHandleW(hFile, v46, v45, 0xAu);
    v49 = *ppByteStream;
    v50 = (*ppByteStream)->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Instance = ((__int64 (__fastcall *)(IMFByteStream *, GUID *, __int64 *))v50)(
                 v49,
                 &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
                 &v69);
    if ( Instance < 0 )
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
        if ( v52->m_result != Instance )
          CallStackContext::TraceFailure(v52, "MFCreateMFByteStreamOnStreamEx", 255, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_165;
      v27 = 29;
      goto LABEL_68;
    }
    Instance = (*(__int64 (__fastcall **)(__int64, const IID *, WCHAR *))(*(_QWORD *)v69 + 200LL))(
                 v69,
                 &MF_BYTESTREAM_ORIGIN_NAME,
                 v4);
    if ( Instance >= 0 )
    {
LABEL_154:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 32LL))(v80);
      v78 = 0;
      goto LABEL_165;
    }
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
      if ( v54->m_result != Instance )
        CallStackContext::TraceFailure(v54, "MFCreateMFByteStreamOnStreamEx", 256, Instance);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_165;
    v27 = 30;
LABEL_68:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids, 0, Instance);
    goto LABEL_165;
  }
  v55 = CallStackTracing::s_wpInstance;
  Instance = -2147024809;
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
    if ( v56->m_result != -2147024809 )
      CallStackContext::TraceFailure(v56, "MFCreateMFByteStreamOnStreamEx", 233, -2147024809);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v10 = 25;
    goto LABEL_164;
  }
LABEL_165:
  operator delete(v4);
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 32LL))(v80);
  v57 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  }
  v58 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  }
  v59 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
  v60 = v71;
  if ( v71 )
  {
    v71 = 0;
    v60->Release(v60);
  }
  v61 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  }
  v62 = v72;
  if ( v72 )
  {
    v72 = 0;
    v62->Release(v62);
  }
  v63 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  }
  v64 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v78);
  return Instance;
}

```

## disassembly

```asm
0x18008a9a0  mov     [rsp-8+arg_0], rbx
0x18008a9a5  push    rbp
0x18008a9a6  push    rsi
0x18008a9a7  push    rdi
0x18008a9a8  push    r12
0x18008a9aa  push    r13
0x18008a9ac  push    r14
0x18008a9ae  push    r15
0x18008a9b0  lea     rbp, [rsp-27h]
0x18008a9b5  sub     rsp, 90h
0x18008a9bc  mov     r12, rdx
0x18008a9bf  lea     r14, aMfcreatemfbyte_5; "MFCreateMFByteStreamOnStreamEx"
0x18008a9c6  mov     r15, rcx
0x18008a9c9  mov     rdx, r14; char *
0x18008a9cc  mov     r8d, 68h ; 'h'; int
0x18008a9d2  lea     rcx, [rbp+57h+arg_8]; this
0x18008a9d6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008a9db  xor     edi, edi
0x18008a9dd  mov     [rbp+57h+var_58], rdi
0x18008a9e1  mov     r13d, edi
0x18008a9e4  mov     [rbp+57h+var_90], rdi
0x18008a9e8  mov     [rbp+57h+var_60], rdi
0x18008a9ec  mov     [rbp+57h+var_50], rdi
0x18008a9f0  mov     [rbp+57h+var_68], rdi
0x18008a9f4  mov     [rbp+57h+var_70], rdi
0x18008a9f8  mov     [rbp+57h+arg_18], rdi
0x18008a9fc  mov     [rbp+57h+var_78], rdi
0x18008aa00  mov     [rbp+57h+hFile], rdi
0x18008aa04  mov     byte ptr [rbp+57h+arg_8], dil
0x18008aa08  test    r12, r12
0x18008aa0b  jnz     loc_18008AAAC
0x18008aa11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008aa18  mov     esi, 80004003h
0x18008aa1d  test    rcx, rcx
0x18008aa20  jnz     short loc_18008AA63
0x18008aa22  mov     rax, cs:stru_1801FC290.__vftable
0x18008aa29  lea     r8, stru_1801FC290
0x18008aa30  mov     edx, 7F0h
0x18008aa35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008aa3c  mov     rcx, r8
0x18008aa3f  mov     rax, [rax+8]
0x18008aa43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aa48  test    eax, eax
0x18008aa4a  jnz     short loc_18008AA5C
0x18008aa4c  lea     rcx, stru_1801F8A30
0x18008aa53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008aa5a  jmp     short loc_18008AA63
0x18008aa5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008aa63  cmp     [rcx+8], dil
0x18008aa67  jz      short loc_18008AA8A
0x18008aa69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008aa6e  cmp     [rax+7CCh], esi
0x18008aa74  jz      short loc_18008AA8A
0x18008aa76  mov     r9d, esi; int
0x18008aa79  mov     r8d, 7Bh ; '{'; int
0x18008aa7f  mov     rdx, r14; char *
0x18008aa82  mov     rcx, rax; this
0x18008aa85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008aa8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008aa91  jb      loc_18008B6D4
0x18008aa97  mov     edx, 0Bh
0x18008aa9c  mov     [rsp+0C0h+var_A0], esi
0x18008aaa0  lea     r8, WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids
0x18008aaa7  jmp     loc_18008B6C1
0x18008aaac  mov     [r12], rdi
0x18008aab0  test    r15, r15
0x18008aab3  jnz     loc_18008AB52
0x18008aab9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008aac0  mov     ebx, 80070057h
0x18008aac5  mov     esi, ebx
0x18008aac7  test    rcx, rcx
0x18008aaca  jnz     short loc_18008AB0D
0x18008aacc  mov     rax, cs:stru_1801FC290.__vftable
0x18008aad3  lea     r8, stru_1801FC290
0x18008aada  mov     edx, 7F0h
0x18008aadf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008aae6  mov     rcx, r8
0x18008aae9  mov     rax, [rax+8]
0x18008aaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aaf2  test    eax, eax
0x18008aaf4  jnz     short loc_18008AB06
0x18008aaf6  lea     rcx, stru_1801F8A30
0x18008aafd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ab04  jmp     short loc_18008AB0D
0x18008ab06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008ab0d  cmp     [rcx+8], dil
0x18008ab11  jz      short loc_18008AB34
0x18008ab13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008ab18  cmp     [rax+7CCh], ebx
0x18008ab1e  jz      short loc_18008AB34
0x18008ab20  mov     r9d, ebx; int
0x18008ab23  mov     r8d, 7Eh ; '~'; int
0x18008ab29  mov     rdx, r14; char *
0x18008ab2c  mov     rcx, rax; this
0x18008ab2f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008ab34  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008ab3b  jb      loc_18008B6D4
0x18008ab41  mov     edx, 0Ch
0x18008ab46  lea     r8, WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids
0x18008ab4d  jmp     loc_18008B6BD
0x18008ab52  mov     rax, [r15]
0x18008ab55  lea     rcx, [rbp+57h+var_58]
0x18008ab59  mov     rbx, [rax]
0x18008ab5c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ab61  lea     r8, [rbp+57h+var_58]
0x18008ab65  mov     rcx, r15
0x18008ab68  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x18008ab6f  mov     rax, rbx
0x18008ab72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ab77  test    eax, eax
0x18008ab79  js      loc_18008AE3B
0x18008ab7f  mov     [rbp+57h+arg_10], rdi
0x18008ab83  lea     rcx, [rbp+57h+arg_10]
0x18008ab87  mov     rdi, [rbp+57h+var_58]
0x18008ab8b  mov     rax, [rdi]
0x18008ab8e  mov     rbx, [rax+18h]
0x18008ab92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ab97  lea     r9, [rbp+57h+arg_10]
0x18008ab9b  mov     rcx, rdi
0x18008ab9e  lea     r8, _GUID_ad4c1b00_4bf7_422f_9175_756693d9130d
0x18008aba5  mov     rax, rbx
0x18008aba8  lea     rdx, MF_WRAPPED_OBJECT
0x18008abaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008abb4  xor     edi, edi
0x18008abb6  test    eax, eax
0x18008abb8  js      loc_18008AE32
0x18008abbe  mov     rbx, [rbp+57h+arg_10]
0x18008abc2  lea     rcx, [rbp+57h+var_88]
0x18008abc6  mov     [rbp+57h+var_88], rdi
0x18008abca  mov     esi, edi
0x18008abcc  mov     [rbp+57h+var_80], rdi
0x18008abd0  mov     rax, [rbx]
0x18008abd3  mov     rdi, [rax]
0x18008abd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008abdb  lea     r8, [rbp+57h+var_88]
0x18008abdf  mov     rcx, rbx
0x18008abe2  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18008abe9  mov     rax, rdi
0x18008abec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008abf1  xor     edi, edi
0x18008abf3  test    eax, eax
0x18008abf5  js      loc_18008ADAE
0x18008abfb  mov     rcx, [rbp+57h+var_88]
0x18008abff  lea     rdx, MF_BYTESTREAM_PROXY
0x18008ac06  xor     r8d, r8d
0x18008ac09  call    MFGetAttributeUINT32
0x18008ac0e  test    eax, eax
0x18008ac10  jz      loc_18008ADAE
0x18008ac16  lea     rcx, [rbp+57h+var_80]
0x18008ac1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008ac1f  mov     rcx, [rbp+57h+arg_10]; struct IMFByteStream *
0x18008ac23  lea     r8, [rbp+57h+var_80]; struct IUnknown **
0x18008ac27  call    ?CreateInstance@CMFByteStreamProxy@@SAJPEAUIMFByteStream@@PEAUIMFAttributes@@PEAPEAUIUnknown@@@Z; CMFByteStreamProxy::CreateInstance(IMFByteStream *,IMFAttributes *,IUnknown * *)
0x18008ac2c  mov     esi, eax
0x18008ac2e  test    eax, eax
0x18008ac30  jns     loc_18008ACF6
0x18008ac36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ac3d  test    rcx, rcx
0x18008ac40  jnz     short loc_18008AC83
0x18008ac42  mov     rax, cs:stru_1801FC290.__vftable
0x18008ac49  lea     r8, stru_1801FC290
0x18008ac50  mov     edx, 7F0h
0x18008ac55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ac5c  mov     rcx, r8
0x18008ac5f  mov     rax, [rax+8]
0x18008ac63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ac68  test    eax, eax
0x18008ac6a  jnz     short loc_18008AC7C
0x18008ac6c  lea     rcx, stru_1801F8A30
0x18008ac73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ac7a  jmp     short loc_18008AC83
0x18008ac7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008ac83  cmp     [rcx+8], dil
0x18008ac87  jz      short loc_18008ACAA
0x18008ac89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008ac8e  cmp     [rax+7CCh], esi
0x18008ac94  jz      short loc_18008ACAA
0x18008ac96  mov     r9d, esi; int
0x18008ac99  mov     r8d, 96h; int
0x18008ac9f  mov     rdx, r14; char *
0x18008aca2  mov     rcx, rax; this
0x18008aca5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008acaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008acb1  jb      short loc_18008ACD6
0x18008acb3  mov     edx, 0Dh
0x18008acb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008acbf  lea     r8, WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids
0x18008acc6  xor     r9d, r9d
0x18008acc9  mov     [rsp+0C0h+var_A0], esi
0x18008accd  mov     rcx, [rcx+10h]
0x18008acd1  call    WPP_SF_qD
0x18008acd6  lea     rcx, [rbp+57h+var_88]
0x18008acda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008acdf  lea     rcx, [rbp+57h+var_80]
0x18008ace3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008ace8  lea     rcx, [rbp+57h+arg_10]
0x18008acec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008acf1  jmp     loc_18008B6D4
0x18008acf6  lea     rcx, [rbp+57h+arg_10]
0x18008acfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008acff  mov     rcx, [rbp+57h+var_80]
0x18008ad03  lea     r8, [rbp+57h+arg_10]
0x18008ad07  lea     rdx, _GUID_ad4c1b00_4bf7_422f_9175_756693d9130d
0x18008ad0e  mov     rax, [rcx]
0x18008ad11  mov     rax, [rax]
0x18008ad14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad19  mov     esi, eax
0x18008ad1b  test    eax, eax
0x18008ad1d  jns     loc_18008ADAE
0x18008ad23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ad2a  test    rcx, rcx
0x18008ad2d  jnz     short loc_18008AD70
0x18008ad2f  mov     rax, cs:stru_1801FC290.__vftable
0x18008ad36  lea     r8, stru_1801FC290
0x18008ad3d  mov     edx, 7F0h
0x18008ad42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ad49  mov     rcx, r8
0x18008ad4c  mov     rax, [rax+8]
0x18008ad50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad55  test    eax, eax
0x18008ad57  jnz     short loc_18008AD69
0x18008ad59  lea     rcx, stru_1801F8A30
0x18008ad60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ad67  jmp     short loc_18008AD70
0x18008ad69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008ad70  cmp     [rcx+8], dil
0x18008ad74  jz      short loc_18008AD97
0x18008ad76  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008ad7b  cmp     [rax+7CCh], esi
0x18008ad81  jz      short loc_18008AD97
0x18008ad83  mov     r9d, esi; int
0x18008ad86  mov     r8d, 97h; int
0x18008ad8c  mov     rdx, r14; char *
0x18008ad8f  mov     rcx, rax; this
0x18008ad92  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008ad97  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008ad9e  jb      loc_18008ACD6
0x18008ada4  mov     edx, 0Eh
0x18008ada9  jmp     loc_18008ACB8
0x18008adae  mov     rax, [r15]
0x18008adb1  lea     rcx, [rbp+57h+var_90]
0x18008adb5  mov     rbx, [rax]
0x18008adb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008adbd  lea     r8, [rbp+57h+var_90]
0x18008adc1  mov     rcx, r15
0x18008adc4  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18008adcb  mov     rax, rbx
0x18008adce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008add3  test    eax, eax
0x18008add5  js      short loc_18008AE21
0x18008add7  mov     rcx, [rbp+57h+var_90]
0x18008addb  lea     rdx, [rbp+57h+var_40]
0x18008addf  mov     [rbp+57h+var_40], rdi
0x18008ade3  mov     [rbp+57h+var_38], rdi
0x18008ade7  mov     rax, [rcx]
0x18008adea  mov     rax, [rax+50h]
0x18008adee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008adf3  mov     rcx, [rbp+57h+arg_10]
0x18008adf7  lea     rdx, [rbp+57h+var_38]
0x18008adfb  mov     rax, [rcx]
0x18008adfe  mov     rax, [rax+30h]
0x18008ae02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae07  mov     rdx, [rbp+57h+var_40]
0x18008ae0b  cmp     [rbp+57h+var_38], rdx
0x18008ae0f  jz      short loc_18008AE21
0x18008ae11  mov     rcx, [rbp+57h+arg_10]
0x18008ae15  mov     rax, [rcx]
0x18008ae18  mov     rax, [rax+38h]
0x18008ae1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae21  mov     rax, [rbp+57h+arg_10]
0x18008ae25  mov     [r12], rax
0x18008ae29  mov     [rbp+57h+arg_10], rdi
0x18008ae2d  jmp     loc_18008ACD6
0x18008ae32  lea     rcx, [rbp+57h+arg_10]
0x18008ae36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ae3b  mov     rdx, r12
0x18008ae3e  mov     rcx, r15
0x18008ae41  call    MFCreateMFByteStreamFromHandleProvider
0x18008ae46  mov     esi, eax
0x18008ae48  test    eax, eax
0x18008ae4a  js      short loc_18008AE7D
0x18008ae4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18008ae53  jb      loc_18008B6D4
0x18008ae59  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae60  lea     r8, WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids
0x18008ae67  mov     edx, 0Fh
0x18008ae6c  mov     r9, r15
0x18008ae6f  mov     rcx, [rcx+10h]
0x18008ae73  call    WPP_SF_q
0x18008ae78  jmp     loc_18008B6D4
0x18008ae7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18008ae84  lea     r14, WPP_d1e115e4b615311347691cd6ab38f97b_Traceguids
0x18008ae8b  jb      short loc_18008AEAC
0x18008ae8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae94  mov     edx, 10h
0x18008ae99  mov     r9, r15
0x18008ae9c  mov     [rsp+0C0h+var_A0], eax
0x18008aea0  mov     r8, r14
0x18008aea3  mov     rcx, [rcx+10h]
0x18008aea7  call    WPP_SF_qD
  ... truncated ...
```
