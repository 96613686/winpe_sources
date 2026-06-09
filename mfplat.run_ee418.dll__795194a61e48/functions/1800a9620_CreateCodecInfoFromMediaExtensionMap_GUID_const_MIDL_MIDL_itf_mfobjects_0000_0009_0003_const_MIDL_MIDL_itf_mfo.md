# CreateCodecInfoFromMediaExtensionMap(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,CodecPackInfo &,bool *)

- ea: `0x1800a9620`
- end: `0x1800aa4a2`
- name: `?CreateCodecInfoFromMediaExtensionMap@@YAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUCodecPackInfo@@PEA_N@Z`
- size: `3714`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a93a4`

## callees

- `0x180004870`
- `0x18001e1c4`
- `0x18001f3ac`
- `0x180020458`
- `0x180020b80`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800802e0`
- `0x1800a9620`
- `0x1800aa4a8`
- `0x1800aa698`
- `0x1801200d0`
- `0x1801250c8`
- `0x18014aa80`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aa102`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aa102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9d82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9d82`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a9d3f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a9fcf`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a9d3f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a9fcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800aa114`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800aa114`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aa0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aa0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa40b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa40b`

## string_xrefs

- `0x1800a9674`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9721`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a97dc`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9888`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9a0b`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9add`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9b90`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9c40`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9cf9`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9e17`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9ecd`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800a9f89`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800aa070`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800aa184`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800aa247`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800aa2fd`: `CreateCodecInfoFromMediaExtensionMap`
- `0x1800aa3af`: `CreateCodecInfoFromMediaExtensionMap`

## pseudocode

```c
__int64 __fastcall CreateCodecInfoFromMediaExtensionMap(
        _QWORD *a1,
        const IID *a2,
        OLECHAR *a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6)
{
  HRESULT SubMapFromMap; // ebx
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  _QWORD *v15; // rsi
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  GUID v27; // xmm0
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  int v36; // edx
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  LPOLESTR v41; // r13
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  int v46; // esi
  int v47; // edx
  int v48; // r9d
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  int v53; // edx
  int v54; // r9d
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  CallStackScopeTrace v64; // [rsp+30h] [rbp-59h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-51h] BYREF
  __int64 v66; // [rsp+40h] [rbp-49h] BYREF
  __int64 v67; // [rsp+48h] [rbp-41h] BYREF
  HSTRING string1; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-31h] BYREF
  __int64 v70; // [rsp+60h] [rbp-29h] BYREF
  __int64 v71; // [rsp+68h] [rbp-21h] BYREF
  HSTRING string2; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-11h] BYREF

  lpsz = a3;
  if ( a6 )
    *a6 = 1;
  v66 = 0;
  v70 = 0;
  v67 = 0;
  v71 = 0;
  string = 0;
  string1 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v64, "CreateCodecInfoFromMediaExtensionMap", 1167);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  SubMapFromMap = GetSubMapFromMap(a4, L"MediaCodec", &v66);
  if ( SubMapFromMap < 0 )
  {
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( ThreadRelativeContext->m_result != SubMapFromMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateCodecInfoFromMediaExtensionMap",
          1167,
          SubMapFromMap);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v12 = 143;
LABEL_211:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        SubMapFromMap);
      goto LABEL_212;
    }
    goto LABEL_212;
  }
  WindowsDeleteString(string);
  string = 0;
  SubMapFromMap = CreateStringFromMap(v66, L"@Category", &string);
  if ( SubMapFromMap >= 0 )
  {
    v15 = (_QWORD *)(a5 + 448);
    SubMapFromMap = CreateCodecCategoryFromString(string, (struct _GUID *)(a5 + 448));
    if ( SubMapFromMap < 0 )
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
        if ( v17->m_result != SubMapFromMap )
          CallStackContext::TraceFailure(v17, "CreateCodecInfoFromMediaExtensionMap", 1169, SubMapFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v12 = 145;
        goto LABEL_211;
      }
      goto LABEL_212;
    }
    v18 = *a1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( *a1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
      v18 = a1[1] - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v18 )
    {
      v19 = *v15 - *a1;
      if ( *v15 == *a1 )
        v19 = *(_QWORD *)(a5 + 456) - a1[1];
      if ( v19 )
      {
        if ( a6 )
          *a6 = 0;
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, a4);
        goto LABEL_212;
      }
    }
    v20 = *v15 - *(_QWORD *)&MFT_CATEGORY_AUDIO_DECODER.Data1;
    if ( *v15 == *(_QWORD *)&MFT_CATEGORY_AUDIO_DECODER.Data1 )
      v20 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_AUDIO_DECODER.Data4;
    if ( !v20 )
      goto LABEL_66;
    v21 = *v15 - *(_QWORD *)&MFT_CATEGORY_AUDIO_ENCODER.Data1;
    if ( *v15 == *(_QWORD *)&MFT_CATEGORY_AUDIO_ENCODER.Data1 )
      v21 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_AUDIO_ENCODER.Data4;
    if ( v21 )
    {
      v22 = *v15 - *(_QWORD *)&MFT_CATEGORY_VIDEO_DECODER.Data1;
      if ( *v15 == *(_QWORD *)&MFT_CATEGORY_VIDEO_DECODER.Data1 )
        v22 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_VIDEO_DECODER.Data4;
      if ( v22 )
      {
        v23 = *v15 - *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1;
        if ( *v15 == *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1 )
          v23 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_VIDEO_ENCODER.Data4;
        if ( v23 )
        {
          v24 = CallStackTracing::s_wpInstance;
          SubMapFromMap = -1072875845;
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
            if ( v25->m_result != -1072875845 )
              CallStackContext::TraceFailure(v25, "CreateCodecInfoFromMediaExtensionMap", 1192, -1072875845);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_212;
          v26 = 147;
          goto LABEL_64;
        }
      }
      v27 = MFMediaType_Video;
    }
    else
    {
LABEL_66:
      v27 = MFMediaType_Audio;
    }
    *(GUID *)(a5 + 464) = v27;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    SubMapFromMap = GetSubMapFromMap(v66, L"MediaEncodingProperties", &v70);
    if ( SubMapFromMap < 0 )
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
        if ( v29->m_result != SubMapFromMap )
          CallStackContext::TraceFailure(v29, "CreateCodecInfoFromMediaExtensionMap", 1196, SubMapFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v12 = 148;
        goto LABEL_211;
      }
      goto LABEL_212;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    SubMapFromMap = GetSubMapFromMap(v70, L"InputTypes", &v67);
    if ( SubMapFromMap < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
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
        if ( v31->m_result != SubMapFromMap )
          CallStackContext::TraceFailure(v31, "CreateCodecInfoFromMediaExtensionMap", 1197, SubMapFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v12 = 149;
        goto LABEL_211;
      }
      goto LABEL_212;
    }
    SubMapFromMap = CreateTypeVectorFromMap(v67, L"InputType", a5 + 464, a5 + 72);
    if ( SubMapFromMap < 0 )
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
        if ( v33->m_result != SubMapFromMap )
          CallStackContext::TraceFailure(v33, "CreateCodecInfoFromMediaExtensionMap", 1198, SubMapFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v12 = 150;
        goto LABEL_211;
      }
      goto LABEL_212;
    }
    if ( !a2 )
      goto LABEL_116;
    v64 = 0;
    SubMapFromMap = MatchTypeFromAppManifest(a5 + 464, a2, a5 + 72, &v64);
    if ( SubMapFromMap < 0 )
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
        if ( v35->m_result != SubMapFromMap )
          CallStackContext::TraceFailure(v35, "CreateCodecInfoFromMediaExtensionMap", 1203, SubMapFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v12 = 151;
        goto LABEL_211;
      }
      goto LABEL_212;
    }
    if ( v64 )
    {
LABEL_116:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
      SubMapFromMap = GetSubMapFromMap(v70, L"OutputTypes", &v71);
      if ( SubMapFromMap < 0 )
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
          if ( v38->m_result != SubMapFromMap )
            CallStackContext::TraceFailure(v38, "CreateCodecInfoFromMediaExtensionMap", 1223, SubMapFromMap);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v12 = 153;
          goto LABEL_211;
        }
        goto LABEL_212;
      }
      SubMapFromMap = CreateTypeVectorFromMap(v71, L"OutputType", a5 + 464, a5 + 480);
      if ( SubMapFromMap < 0 )
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
          if ( v40->m_result != SubMapFromMap )
            CallStackContext::TraceFailure(v40, "CreateCodecInfoFromMediaExtensionMap", 1224, SubMapFromMap);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v12 = 154;
          goto LABEL_211;
        }
        goto LABEL_212;
      }
      v41 = lpsz;
      if ( !lpsz )
        goto LABEL_153;
      v64 = 0;
      SubMapFromMap = MatchTypeFromAppManifest(a5 + 464, lpsz, a5 + 480, &v64);
      if ( SubMapFromMap < 0 )
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
          if ( v43->m_result != SubMapFromMap )
            CallStackContext::TraceFailure(v43, "CreateCodecInfoFromMediaExtensionMap", 1229, SubMapFromMap);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v12 = 155;
          goto LABEL_211;
        }
        goto LABEL_212;
      }
      if ( v64 )
      {
LABEL_153:
        SubMapFromMap = CreateInprocMFTExtensionInfoFromMediaExtensionMap(a4, v66, a5);
        if ( SubMapFromMap < 0 )
        {
          v44 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v44 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v44->m_fEnabled )
          {
            v45 = CallStackTracing::GetThreadRelativeContext(v44);
            if ( v45->m_result != SubMapFromMap )
              CallStackContext::TraceFailure(v45, "CreateCodecInfoFromMediaExtensionMap", 1249, SubMapFromMap);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v12 = 157;
            goto LABEL_211;
          }
          goto LABEL_212;
        }
        v46 = 0;
        WindowsDeleteString(string1);
        string1 = 0;
        if ( (int)CreateStringFromMap(v66, L"@CodecType", &string1) >= 0 )
        {
          LODWORD(lpsz) = -1;
          if ( WindowsCreateStringReference(L"hardware", 8u, &hstringHeader, &string2) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          SubMapFromMap = WindowsCompareStringOrdinal(string1, string2, (INT32 *)&lpsz);
          if ( SubMapFromMap < 0 )
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
              if ( v50->m_result != SubMapFromMap )
                CallStackContext::TraceFailure(v50, "CreateCodecInfoFromMediaExtensionMap", 1256, SubMapFromMap);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v12 = 158;
              goto LABEL_211;
            }
            goto LABEL_212;
          }
          if ( !(_DWORD)lpsz )
            v46 = 1;
        }
        if ( *(_BYTE *)(a5 + 33) )
        {
          *(_DWORD *)(a5 + 64) |= v46 != 0 ? 6 : 1;
        }
        else
        {
          if ( v46 )
          {
            v51 = CallStackTracing::s_wpInstance;
            SubMapFromMap = -1072875845;
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
              if ( v52->m_result != -1072875845 )
                CallStackContext::TraceFailure(v52, "CreateCodecInfoFromMediaExtensionMap", 1270, -1072875845);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_212;
            v26 = 159;
LABEL_64:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v26,
              &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
              0,
              -1072875845);
            goto LABEL_212;
          }
          *(_DWORD *)(a5 + 64) |= 1u;
        }
        SubMapFromMap = CreateStringVectorFromMap(v67, v47, (unsigned int)L"@MkvCodecId", v48, a5 + 856);
        if ( SubMapFromMap >= 0 )
        {
          SubMapFromMap = CreateStringVectorFromMap(v67, v53, (unsigned int)L"@CodecMimeType", v54, a5 + 1064);
          if ( SubMapFromMap < 0 )
          {
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
              if ( v58->m_result != SubMapFromMap )
                CallStackContext::TraceFailure(v58, "CreateCodecInfoFromMediaExtensionMap", 1278, SubMapFromMap);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v12 = 161;
              goto LABEL_211;
            }
          }
        }
        else
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
            if ( v56->m_result != SubMapFromMap )
              CallStackContext::TraceFailure(v56, "CreateCodecInfoFromMediaExtensionMap", 1277, SubMapFromMap);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v12 = 160;
            goto LABEL_211;
          }
        }
        goto LABEL_212;
      }
      if ( a6 )
        *a6 = 0;
      lpsz = 0;
      if ( StringFromCLSID((const IID *const)v41 + 1, &lpsz) < 0 )
        goto LABEL_212;
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
      {
        v36 = 156;
        goto LABEL_114;
      }
    }
    else
    {
      if ( a6 )
        *a6 = 0;
      lpsz = 0;
      if ( StringFromCLSID(a2 + 1, &lpsz) < 0 )
        goto LABEL_212;
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
      {
        v36 = 152;
LABEL_114:
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          (unsigned int)&WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
          a4,
          (__int64)lpsz);
      }
    }
    CoTaskMemFree(lpsz);
    goto LABEL_212;
  }
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
    if ( v14->m_result != SubMapFromMap )
      CallStackContext::TraceFailure(v14, "CreateCodecInfoFromMediaExtensionMap", 1168, SubMapFromMap);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v12 = 144;
    goto LABEL_211;
  }
LABEL_212:
  CallStackScopeTrace::~CallStackScopeTrace(&v64);
  WindowsDeleteString(string1);
  string1 = 0;
  WindowsDeleteString(string);
  v59 = v71;
  string = 0;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
  v60 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  }
  v61 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  }
  v62 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  }
  return (unsigned int)SubMapFromMap;
}

```

## disassembly

```asm
0x1800a9620  mov     [rsp-8+arg_0], rbx
0x1800a9625  push    rbp
0x1800a9626  push    rsi
0x1800a9627  push    rdi
0x1800a9628  push    r12
0x1800a962a  push    r13
0x1800a962c  push    r14
0x1800a962e  push    r15
0x1800a9630  lea     rbp, [rsp-17h]
0x1800a9635  sub     rsp, 0A0h
0x1800a963c  mov     rax, cs:__security_cookie
0x1800a9643  xor     rax, rsp
0x1800a9646  mov     [rbp+47h+var_40], rax
0x1800a964a  mov     r14, [rbp+47h+arg_28]
0x1800a964e  xor     esi, esi
0x1800a9650  mov     rdi, [rbp+47h+arg_20]
0x1800a9654  mov     r12, r9
0x1800a9657  mov     [rbp+47h+lpsz], r8
0x1800a965b  mov     r13, rdx
0x1800a965e  mov     r15, rcx
0x1800a9661  test    r14, r14
0x1800a9664  jz      short loc_1800A966A
0x1800a9666  mov     byte ptr [r14], 1
0x1800a966a  mov     r8d, 48Fh; int
0x1800a9670  mov     [rbp+47h+var_90], rsi
0x1800a9674  lea     rdx, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800a967b  mov     [rbp+47h+var_70], rsi
0x1800a967f  lea     rcx, [rbp+47h+var_A0]; this
0x1800a9683  mov     [rbp+47h+var_88], rsi
0x1800a9687  mov     [rbp+47h+var_68], rsi
0x1800a968b  mov     [rbp+47h+string], rsi
0x1800a968f  mov     [rbp+47h+string1], rsi
0x1800a9693  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a9698  lea     rcx, [rbp+47h+var_90]
0x1800a969c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a96a1  lea     r8, [rbp+47h+var_90]
0x1800a96a5  mov     rcx, r12
0x1800a96a8  lea     rdx, aMediacodec; "MediaCodec"
0x1800a96af  call    GetSubMapFromMap
0x1800a96b4  mov     ebx, eax
0x1800a96b6  test    eax, eax
0x1800a96b8  jns     loc_1800A974D
0x1800a96be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a96c5  xor     r15d, r15d
0x1800a96c8  test    rcx, rcx
0x1800a96cb  jnz     short loc_1800A970B
0x1800a96cd  mov     rdx, cs:stru_1801FC290.__vftable
0x1800a96d4  lea     rcx, stru_1801FC290
0x1800a96db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a96e2  mov     rax, [rdx+8]
0x1800a96e6  mov     edx, 7F0h
0x1800a96eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a96f0  test    eax, eax
0x1800a96f2  jnz     short loc_1800A9704
0x1800a96f4  lea     rcx, stru_1801F8A30
0x1800a96fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9702  jmp     short loc_1800A970B
0x1800a9704  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a970b  cmp     [rcx+8], r15b
0x1800a970f  jz      short loc_1800A9736
0x1800a9711  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9716  cmp     [rax+7CCh], ebx
0x1800a971c  jz      short loc_1800A9736
0x1800a971e  mov     r9d, ebx; int
0x1800a9721  lea     rdx, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800a9728  mov     r8d, 48Fh; int
0x1800a972e  mov     rcx, rax; this
0x1800a9731  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9736  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a973d  jb      loc_1800AA3F0
0x1800a9743  mov     edx, 8Fh
0x1800a9748  jmp     loc_1800AA3D2
0x1800a974d  mov     rcx, [rbp+47h+string]; string
0x1800a9751  call    cs:__imp_WindowsDeleteString
0x1800a9757  mov     rcx, [rbp+47h+var_90]
0x1800a975b  lea     r8, [rbp+47h+string]
0x1800a975f  lea     rdx, aCategory; "@Category"
0x1800a9766  mov     [rbp+47h+string], rsi
0x1800a976a  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800a976f  mov     ebx, eax
0x1800a9771  test    eax, eax
0x1800a9773  jns     loc_1800A9808
0x1800a9779  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9780  xor     r15d, r15d
0x1800a9783  test    rcx, rcx
0x1800a9786  jnz     short loc_1800A97C6
0x1800a9788  mov     rax, cs:stru_1801FC290.__vftable
0x1800a978f  lea     rcx, stru_1801FC290
0x1800a9796  mov     edx, 7F0h
0x1800a979b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97a2  mov     rax, [rax+8]
0x1800a97a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a97ab  test    eax, eax
0x1800a97ad  jnz     short loc_1800A97BF
0x1800a97af  lea     rcx, stru_1801F8A30
0x1800a97b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97bd  jmp     short loc_1800A97C6
0x1800a97bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a97c6  cmp     [rcx+8], r15b
0x1800a97ca  jz      short loc_1800A97F1
0x1800a97cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a97d1  cmp     [rax+7CCh], ebx
0x1800a97d7  jz      short loc_1800A97F1
0x1800a97d9  mov     r9d, ebx; int
0x1800a97dc  lea     rdx, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800a97e3  mov     r8d, 490h; int
0x1800a97e9  mov     rcx, rax; this
0x1800a97ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a97f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a97f8  jb      loc_1800AA3F0
0x1800a97fe  mov     edx, 90h
0x1800a9803  jmp     loc_1800AA3D2
0x1800a9808  mov     rcx, [rbp+47h+string]; string1
0x1800a980c  lea     rsi, [rdi+1C0h]
0x1800a9813  mov     rdx, rsi; struct _GUID *
0x1800a9816  call    ?CreateCodecCategoryFromString@@YAJPEAUHSTRING__@@PEAU_GUID@@@Z; CreateCodecCategoryFromString(HSTRING__ *,_GUID *)
0x1800a981b  mov     ebx, eax
0x1800a981d  test    eax, eax
0x1800a981f  jns     loc_1800A98B4
0x1800a9825  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a982c  xor     r15d, r15d
0x1800a982f  test    rcx, rcx
0x1800a9832  jnz     short loc_1800A9872
0x1800a9834  mov     rax, cs:stru_1801FC290.__vftable
0x1800a983b  lea     rcx, stru_1801FC290
0x1800a9842  mov     edx, 7F0h
0x1800a9847  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a984e  mov     rax, [rax+8]
0x1800a9852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9857  test    eax, eax
0x1800a9859  jnz     short loc_1800A986B
0x1800a985b  lea     rcx, stru_1801F8A30
0x1800a9862  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9869  jmp     short loc_1800A9872
0x1800a986b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9872  cmp     [rcx+8], r15b
0x1800a9876  jz      short loc_1800A989D
0x1800a9878  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a987d  cmp     [rax+7CCh], ebx
0x1800a9883  jz      short loc_1800A989D
0x1800a9885  mov     r9d, ebx; int
0x1800a9888  lea     rdx, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800a988f  mov     r8d, 491h; int
0x1800a9895  mov     rcx, rax; this
0x1800a9898  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a989d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a98a4  jb      loc_1800AA3F0
0x1800a98aa  mov     edx, 91h
0x1800a98af  jmp     loc_1800AA3D2
0x1800a98b4  mov     rax, [r15]
0x1800a98b7  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a98be  jnz     short loc_1800A98CB
0x1800a98c0  mov     rax, [r15+8]
0x1800a98c4  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800a98cb  test    rax, rax
0x1800a98ce  jz      short loc_1800A9921
0x1800a98d0  mov     rax, [rsi]
0x1800a98d3  sub     rax, [r15]
0x1800a98d6  jnz     short loc_1800A98E0
0x1800a98d8  mov     rax, [rsi+8]
0x1800a98dc  sub     rax, [r15+8]
0x1800a98e0  xor     r15d, r15d
0x1800a98e3  test    rax, rax
0x1800a98e6  jz      short loc_1800A9924
0x1800a98e8  test    r14, r14
0x1800a98eb  jz      short loc_1800A98F0
0x1800a98ed  mov     [r14], r15b
0x1800a98f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1800a98f7  jb      loc_1800AA3F0
0x1800a98fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9904  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800a990b  mov     edx, 92h
0x1800a9910  mov     r9, r12
0x1800a9913  mov     rcx, [rcx+10h]
0x1800a9917  call    WPP_SF_q
0x1800a991c  jmp     loc_1800AA3F0
0x1800a9921  xor     r15d, r15d
0x1800a9924  mov     rax, [rsi]
0x1800a9927  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x1800a992e  jnz     short loc_1800A993B
0x1800a9930  mov     rax, [rsi+8]
0x1800a9934  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data4
0x1800a993b  test    rax, rax
0x1800a993e  jz      loc_1800A9A44
0x1800a9944  mov     rax, [rsi]
0x1800a9947  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x1800a994e  jnz     short loc_1800A995B
0x1800a9950  mov     rax, [rsi+8]
0x1800a9954  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data4
0x1800a995b  test    rax, rax
0x1800a995e  jz      loc_1800A9A44
0x1800a9964  mov     rax, [rsi]
0x1800a9967  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x1800a996e  jnz     short loc_1800A997B
0x1800a9970  mov     rax, [rsi+8]
0x1800a9974  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data4
0x1800a997b  test    rax, rax
0x1800a997e  jz      loc_1800A9A3B
0x1800a9984  mov     rax, [rsi]
0x1800a9987  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800a998e  jnz     short loc_1800A999B
0x1800a9990  mov     rax, [rsi+8]
0x1800a9994  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data4
0x1800a999b  test    rax, rax
0x1800a999e  jz      loc_1800A9A3B
0x1800a99a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a99ab  mov     edi, 0C00D36BBh
0x1800a99b0  mov     ebx, edi
0x1800a99b2  test    rcx, rcx
0x1800a99b5  jnz     short loc_1800A99F5
0x1800a99b7  mov     rax, cs:stru_1801FC290.__vftable
0x1800a99be  lea     rcx, stru_1801FC290
0x1800a99c5  mov     edx, 7F0h
0x1800a99ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a99d1  mov     rax, [rax+8]
0x1800a99d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99da  test    eax, eax
0x1800a99dc  jnz     short loc_1800A99EE
0x1800a99de  lea     rcx, stru_1801F8A30
0x1800a99e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a99ec  jmp     short loc_1800A99F5
0x1800a99ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a99f5  cmp     [rcx+8], r15b
0x1800a99f9  jz      short loc_1800A9A20
0x1800a99fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9a00  cmp     [rax+7CCh], edi
0x1800a9a06  jz      short loc_1800A9A20
0x1800a9a08  mov     r9d, edi; int
0x1800a9a0b  lea     rdx, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800a9a12  mov     r8d, 4A8h; int
0x1800a9a18  mov     rcx, rax; this
0x1800a9a1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9a20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9a27  jb      loc_1800AA3F0
0x1800a9a2d  mov     edx, 93h
0x1800a9a32  mov     dword ptr [rsp+0D0h+var_B0], edi
0x1800a9a36  jmp     loc_1800AA3D6
0x1800a9a3b  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x1800a9a42  jmp     short loc_1800A9A4B
0x1800a9a44  movups  xmm0, xmmword ptr cs:MFMediaType_Audio.Data1
0x1800a9a4b  lea     rsi, [rdi+1D0h]
0x1800a9a52  lea     rcx, [rbp+47h+var_70]
0x1800a9a56  movdqu  xmmword ptr [rsi], xmm0
0x1800a9a5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a9a5f  mov     rcx, [rbp+47h+var_90]
0x1800a9a63  lea     r8, [rbp+47h+var_70]
0x1800a9a67  lea     rdx, aMediaencodingp; "MediaEncodingProperties"
0x1800a9a6e  call    GetSubMapFromMap
0x1800a9a73  mov     ebx, eax
0x1800a9a75  test    eax, eax
0x1800a9a77  jns     loc_1800A9B09
0x1800a9a7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a84  test    rcx, rcx
0x1800a9a87  jnz     short loc_1800A9AC7
0x1800a9a89  mov     rax, cs:stru_1801FC290.__vftable
0x1800a9a90  lea     rcx, stru_1801FC290
0x1800a9a97  mov     edx, 7F0h
0x1800a9a9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9aa3  mov     rax, [rax+8]
0x1800a9aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9aac  test    eax, eax
0x1800a9aae  jnz     short loc_1800A9AC0
0x1800a9ab0  lea     rcx, stru_1801F8A30
0x1800a9ab7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9abe  jmp     short loc_1800A9AC7
0x1800a9ac0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9ac7  cmp     [rcx+8], r15b
0x1800a9acb  jz      short loc_1800A9AF2
0x1800a9acd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9ad2  cmp     [rax+7CCh], ebx
0x1800a9ad8  jz      short loc_1800A9AF2
0x1800a9ada  mov     r9d, ebx; int
0x1800a9add  lea     rdx, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800a9ae4  mov     r8d, 4ACh; int
0x1800a9aea  mov     rcx, rax; this
0x1800a9aed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9af2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9af9  jb      loc_1800AA3F0
0x1800a9aff  mov     edx, 94h
0x1800a9b04  jmp     loc_1800AA3D2
0x1800a9b09  lea     rcx, [rbp+47h+var_88]
0x1800a9b0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a9b12  mov     rcx, [rbp+47h+var_70]
0x1800a9b16  lea     r8, [rbp+47h+var_88]
0x1800a9b1a  lea     rdx, aInputtypes; "InputTypes"
0x1800a9b21  call    GetSubMapFromMap
0x1800a9b26  mov     ebx, eax
0x1800a9b28  test    eax, eax
0x1800a9b2a  jns     loc_1800A9BBC
0x1800a9b30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b37  test    rcx, rcx
0x1800a9b3a  jnz     short loc_1800A9B7A
0x1800a9b3c  mov     rax, cs:stru_1801FC290.__vftable
0x1800a9b43  lea     rcx, stru_1801FC290
0x1800a9b4a  mov     edx, 7F0h
0x1800a9b4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b56  mov     rax, [rax+8]
0x1800a9b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9b5f  test    eax, eax
0x1800a9b61  jnz     short loc_1800A9B73
  ... truncated ...
```
