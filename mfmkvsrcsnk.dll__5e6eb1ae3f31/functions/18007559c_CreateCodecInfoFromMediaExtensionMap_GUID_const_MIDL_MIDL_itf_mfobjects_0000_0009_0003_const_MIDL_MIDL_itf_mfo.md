# CreateCodecInfoFromMediaExtensionMap(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,CodecPackInfo &,bool *)

- ea: `0x18007559c`
- end: `0x1800761a7`
- name: `?CreateCodecInfoFromMediaExtensionMap@@YAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUCodecPackInfo@@PEA_N@Z`
- size: `3083`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ae44`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d44`
- `0x180020d84`
- `0x180071330`
- `0x18007515c`
- `0x18007559c`
- `0x1800770c8`
- `0x1800775b0`
- `0x1800777fc`
- `0x180077fb4`
- `0x180078900`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075e52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800756bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007614f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800756bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007614f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075e64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075e64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075637`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800756f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007579d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007591a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800759f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075aa7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075b58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075c0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075cc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075d6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075e80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075f3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075fef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800760a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075637`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800756f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007579d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007591a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800759f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075aa7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075b58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075c0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075cc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075d6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075e80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075f3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075fef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800760a0`

## string_xrefs

- `0x1800755cc`: `CreateCodecInfoFromMediaExtensionMap`

## pseudocode

```c
__int64 __fastcall CreateCodecInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rdx
  int SubMapFromMap; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  _QWORD *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  GUID v39; // xmm0
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  int v76; // r14d
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  _BYTE v99[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v100; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string1; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  __int64 v103; // [rsp+50h] [rbp-29h] BYREF
  INT32 result; // [rsp+58h] [rbp-21h] BYREF
  __int64 v105; // [rsp+60h] [rbp-19h] BYREF
  __int64 v106; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string2; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF

  v100 = 0;
  v105 = 0;
  v103 = 0;
  v106 = 0;
  string = 0;
  string1 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v99, "CreateCodecInfoFromMediaExtensionMap", 1167);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  SubMapFromMap = GetSubMapFromMap(a4, L"MediaCodec", &v100);
  if ( SubMapFromMap < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != SubMapFromMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateCodecInfoFromMediaExtensionMap",
          1167,
          SubMapFromMap);
    }
    if ( g_wppLevels )
    {
      v13 = 143;
LABEL_183:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        SubMapFromMap);
      goto LABEL_184;
    }
    goto LABEL_184;
  }
  WindowsDeleteString(string);
  string = 0;
  SubMapFromMap = CreateStringFromMap(v100, L"@Category", &string);
  if ( SubMapFromMap >= 0 )
  {
    v20 = (_QWORD *)(a5 + 448);
    SubMapFromMap = CreateCodecCategoryFromString(string, (struct _GUID *)(a5 + 448));
    if ( SubMapFromMap < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v26, "CreateCodecInfoFromMediaExtensionMap", 1169, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 145;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    if ( memcmp_0(&GUID_00000000_0000_0000_0000_000000000000, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    {
      v30 = *v20 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      if ( *v20 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
        v30 = *(_QWORD *)(a5 + 456) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
      if ( v30 )
      {
        if ( g_wppLevels >= 0x10u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, a4);
        goto LABEL_184;
      }
    }
    v31 = *v20 - *(_QWORD *)&MFT_CATEGORY_AUDIO_DECODER.Data1;
    if ( *v20 == *(_QWORD *)&MFT_CATEGORY_AUDIO_DECODER.Data1 )
      v31 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_AUDIO_DECODER.Data4;
    if ( !v31 )
      goto LABEL_64;
    v32 = *v20 - *(_QWORD *)&MFT_CATEGORY_AUDIO_ENCODER.Data1;
    if ( *v20 == *(_QWORD *)&MFT_CATEGORY_AUDIO_ENCODER.Data1 )
      v32 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_AUDIO_ENCODER.Data4;
    if ( v32 )
    {
      v33 = *v20 - *(_QWORD *)&MFT_CATEGORY_VIDEO_DECODER.Data1;
      if ( *v20 == *(_QWORD *)&MFT_CATEGORY_VIDEO_DECODER.Data1 )
        v33 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_VIDEO_DECODER.Data4;
      if ( v33 )
      {
        v34 = *v20 - *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1;
        if ( *v20 == *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1 )
          v34 = *(_QWORD *)(a5 + 456) - *(_QWORD *)MFT_CATEGORY_VIDEO_ENCODER.Data4;
        if ( v34 )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          SubMapFromMap = -1072875845;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != -1072875845 )
              CallStackContext::TraceFailure(v37, "CreateCodecInfoFromMediaExtensionMap", 1192, -1072875845);
          }
          if ( !g_wppLevels )
            goto LABEL_184;
          v38 = 147;
          goto LABEL_62;
        }
      }
      v39 = MFMediaType_Video;
    }
    else
    {
LABEL_64:
      v39 = MFMediaType_Audio;
    }
    *(GUID *)(a5 + 464) = v39;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    SubMapFromMap = GetSubMapFromMap(v100, L"MediaEncodingProperties", &v105);
    if ( SubMapFromMap < 0 )
    {
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)v45 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v45, "CreateCodecInfoFromMediaExtensionMap", 1196, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 148;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
    SubMapFromMap = GetSubMapFromMap(v105, L"InputTypes", &v103);
    if ( SubMapFromMap < 0 )
    {
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v51, "CreateCodecInfoFromMediaExtensionMap", 1197, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 149;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    SubMapFromMap = CreateTypeVectorFromMap(v103, L"InputType", a5 + 464, a5 + 72);
    if ( SubMapFromMap < 0 )
    {
      v55 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
        {
          v55 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v55 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
        if ( *((_DWORD *)v57 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v57, "CreateCodecInfoFromMediaExtensionMap", 1198, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 150;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
    SubMapFromMap = GetSubMapFromMap(v105, L"OutputTypes", &v106);
    if ( SubMapFromMap < 0 )
    {
      v61 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
        CallStackTracing::s_wpInstance = v62;
        if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        {
          v61 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v61 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v61 + 8) )
      {
        v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)v63 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v63, "CreateCodecInfoFromMediaExtensionMap", 1223, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 153;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    SubMapFromMap = CreateTypeVectorFromMap(v106, L"OutputType", a5 + 464, a5 + 480);
    if ( SubMapFromMap < 0 )
    {
      v67 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65, v66);
        CallStackTracing::s_wpInstance = v68;
        if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
        {
          v67 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v67 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v67 + 8) )
      {
        v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
        if ( *((_DWORD *)v69 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v69, "CreateCodecInfoFromMediaExtensionMap", 1224, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 154;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    SubMapFromMap = CreateInprocMFTExtensionInfoFromMediaExtensionMap(a4, v100, a5);
    if ( SubMapFromMap < 0 )
    {
      v73 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
        CallStackTracing::s_wpInstance = v74;
        if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
        {
          v73 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v73 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v73 + 8) )
      {
        v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
        if ( *((_DWORD *)v75 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v75, "CreateCodecInfoFromMediaExtensionMap", 1249, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 157;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    v76 = 0;
    WindowsDeleteString(string1);
    string1 = 0;
    if ( (int)CreateStringFromMap(v100, L"@CodecType", &string1) >= 0 )
    {
      result = -1;
      if ( WindowsCreateStringReference(L"hardware", 8u, &hstringHeader, &string2) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      SubMapFromMap = WindowsCompareStringOrdinal(string1, string2, &result);
      if ( SubMapFromMap < 0 )
      {
        v80 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77, v78, v79);
          CallStackTracing::s_wpInstance = v81;
          if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
          {
            v80 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v80 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v80 + 8) )
        {
          v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
          if ( *((_DWORD *)v82 + 499) != SubMapFromMap )
            CallStackContext::TraceFailure(v82, "CreateCodecInfoFromMediaExtensionMap", 1256, SubMapFromMap);
        }
        if ( g_wppLevels )
        {
          v13 = 158;
          goto LABEL_183;
        }
        goto LABEL_184;
      }
      if ( !result )
        v76 = 1;
    }
    if ( *(_BYTE *)(a5 + 33) )
    {
      *(_DWORD *)(a5 + 64) |= v76 != 0 ? 6 : 1;
    }
    else
    {
      if ( v76 )
      {
        v83 = (__int64 *)CallStackTracing::s_wpInstance;
        SubMapFromMap = -1072875845;
        if ( !CallStackTracing::s_wpInstance )
        {
          v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77, v78, v79);
          CallStackTracing::s_wpInstance = v84;
          if ( v84 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
          {
            v83 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v83 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v83 + 8) )
        {
          v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
          if ( *((_DWORD *)v85 + 499) != -1072875845 )
            CallStackContext::TraceFailure(v85, "CreateCodecInfoFromMediaExtensionMap", 1270, -1072875845);
        }
        if ( !g_wppLevels )
          goto LABEL_184;
        v38 = 159;
LABEL_62:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v38,
          WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
          0,
          -1072875845);
        goto LABEL_184;
      }
      *(_DWORD *)(a5 + 64) |= 1u;
    }
    SubMapFromMap = CreateStringVectorFromMap(v103, v77, (__int64)L"@MkvCodecId", v79, a5 + 856);
    if ( SubMapFromMap >= 0 )
    {
      SubMapFromMap = CreateStringVectorFromMap(v103, v86, (__int64)L"@CodecMimeType", v88, a5 + 1064);
      if ( SubMapFromMap < 0 )
      {
        v95 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v92, v93, v94);
          CallStackTracing::s_wpInstance = v96;
          if ( v96 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
          {
            v95 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v95 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v95 + 8) )
        {
          v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
          if ( *((_DWORD *)v97 + 499) != SubMapFromMap )
            CallStackContext::TraceFailure(v97, "CreateCodecInfoFromMediaExtensionMap", 1278, SubMapFromMap);
        }
        if ( g_wppLevels )
        {
          v13 = 161;
          goto LABEL_183;
        }
      }
    }
    else
    {
      v89 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v86, v87, v88);
        CallStackTracing::s_wpInstance = v90;
        if ( v90 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(v90, 2032) )
        {
          v89 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v89 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v89 + 8) )
      {
        v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
        if ( *((_DWORD *)v91 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v91, "CreateCodecInfoFromMediaExtensionMap", 1277, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 160;
        goto LABEL_183;
      }
    }
    goto LABEL_184;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != SubMapFromMap )
      CallStackContext::TraceFailure(v19, "CreateCodecInfoFromMediaExtensionMap", 1168, SubMapFromMap);
  }
  if ( g_wppLevels )
  {
    v13 = 144;
    goto LABEL_183;
  }
LABEL_184:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v99);
  WindowsDeleteString(string1);
  string1 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  return (unsigned int)SubMapFromMap;
}

```

## disassembly

```asm
0x18007559c  mov     [rsp-8+arg_0], rbx
0x1800755a1  mov     [rsp-8+arg_8], rsi
0x1800755a6  push    rbp
0x1800755a7  push    rdi
0x1800755a8  push    r12
0x1800755aa  push    r14
0x1800755ac  push    r15
0x1800755ae  lea     rbp, [rsp-27h]
0x1800755b3  sub     rsp, 0A0h
0x1800755ba  mov     rax, cs:__security_cookie
0x1800755c1  xor     rax, rsp
0x1800755c4  mov     [rbp+47h+var_30], rax
0x1800755c8  mov     rsi, [rbp+47h+arg_20]
0x1800755cc  lea     r12, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x1800755d3  xor     r15d, r15d
0x1800755d6  lea     rcx, [rbp+47h+var_90]; this
0x1800755da  mov     edi, 48Fh
0x1800755df  mov     [rbp+47h+var_88], r15
0x1800755e3  mov     r8d, edi; int
0x1800755e6  mov     [rbp+47h+var_60], r15
0x1800755ea  mov     rdx, r12; char *
0x1800755ed  mov     [rbp+47h+var_70], r15
0x1800755f1  mov     r14, r9
0x1800755f4  mov     [rbp+47h+var_58], r15
0x1800755f8  mov     [rbp+47h+string], r15
0x1800755fc  mov     [rbp+47h+string1], r15
0x180075600  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180075605  lea     rcx, [rbp+47h+var_88]
0x180075609  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007560e  lea     r8, [rbp+47h+var_88]
0x180075612  mov     rcx, r14
0x180075615  lea     rdx, aMediacodec; "MediaCodec"
0x18007561c  call    GetSubMapFromMap
0x180075621  mov     ebx, eax
0x180075623  test    eax, eax
0x180075625  jns     loc_1800756B8
0x18007562b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075632  test    rcx, rcx
0x180075635  jnz     short loc_180075678
0x180075637  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007563d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180075644  mov     rcx, rax
0x180075647  test    rax, rax
0x18007564a  jz      short loc_18007566A
0x18007564c  mov     rax, [rax]
0x18007564f  mov     edx, 7F0h
0x180075654  mov     rax, [rax+8]
0x180075658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007565d  test    eax, eax
0x18007565f  jz      short loc_18007566A
0x180075661  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075668  jmp     short loc_180075678
0x18007566a  lea     rcx, qword_1800D6F70; this
0x180075671  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180075678  cmp     [rcx+8], r15b
0x18007567c  jz      short loc_18007569C
0x18007567e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075683  cmp     [rax+7CCh], ebx
0x180075689  jz      short loc_18007569C
0x18007568b  mov     r9d, ebx; int
0x18007568e  mov     r8d, edi; int
0x180075691  mov     rdx, r12; char *
0x180075694  mov     rcx, rax; this
0x180075697  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007569c  mov     edi, 1
0x1800756a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800756a8  jb      loc_180076134
0x1800756ae  mov     edx, 8Fh
0x1800756b3  jmp     loc_180076116
0x1800756b8  mov     rcx, [rbp+47h+string]; string
0x1800756bc  call    cs:__imp_WindowsDeleteString
0x1800756c2  mov     rcx, [rbp+47h+var_88]
0x1800756c6  lea     r8, [rbp+47h+string]
0x1800756ca  lea     rdx, aCategory; "@Category"
0x1800756d1  mov     [rbp+47h+string], r15
0x1800756d5  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800756da  mov     ebx, eax
0x1800756dc  test    eax, eax
0x1800756de  jns     loc_180075774
0x1800756e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800756eb  test    rcx, rcx
0x1800756ee  jnz     short loc_180075731
0x1800756f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800756f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800756fd  mov     rcx, rax
0x180075700  test    rax, rax
0x180075703  jz      short loc_180075723
0x180075705  mov     rax, [rax]
0x180075708  mov     edx, 7F0h
0x18007570d  mov     rax, [rax+8]
0x180075711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075716  test    eax, eax
0x180075718  jz      short loc_180075723
0x18007571a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075721  jmp     short loc_180075731
0x180075723  lea     rcx, qword_1800D6F70; this
0x18007572a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180075731  cmp     [rcx+8], r15b
0x180075735  jz      short loc_180075758
0x180075737  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007573c  cmp     [rax+7CCh], ebx
0x180075742  jz      short loc_180075758
0x180075744  mov     r9d, ebx; int
0x180075747  mov     r8d, 490h; int
0x18007574d  mov     rdx, r12; char *
0x180075750  mov     rcx, rax; this
0x180075753  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180075758  mov     edi, 1
0x18007575d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180075764  jb      loc_180076134
0x18007576a  mov     edx, 90h
0x18007576f  jmp     loc_180076116
0x180075774  mov     rcx, [rbp+47h+string]; string1
0x180075778  lea     rdi, [rsi+1C0h]
0x18007577f  mov     rdx, rdi; struct _GUID *
0x180075782  call    ?CreateCodecCategoryFromString@@YAJPEAUHSTRING__@@PEAU_GUID@@@Z; CreateCodecCategoryFromString(HSTRING__ *,_GUID *)
0x180075787  mov     ebx, eax
0x180075789  test    eax, eax
0x18007578b  jns     loc_180075821
0x180075791  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075798  test    rcx, rcx
0x18007579b  jnz     short loc_1800757DE
0x18007579d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800757a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800757aa  mov     rcx, rax
0x1800757ad  test    rax, rax
0x1800757b0  jz      short loc_1800757D0
0x1800757b2  mov     rax, [rax]
0x1800757b5  mov     edx, 7F0h
0x1800757ba  mov     rax, [rax+8]
0x1800757be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757c3  test    eax, eax
0x1800757c5  jz      short loc_1800757D0
0x1800757c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800757ce  jmp     short loc_1800757DE
0x1800757d0  lea     rcx, qword_1800D6F70; this
0x1800757d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800757de  cmp     [rcx+8], r15b
0x1800757e2  jz      short loc_180075805
0x1800757e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800757e9  cmp     [rax+7CCh], ebx
0x1800757ef  jz      short loc_180075805
0x1800757f1  mov     r9d, ebx; int
0x1800757f4  mov     r8d, 491h; int
0x1800757fa  mov     rdx, r12; char *
0x1800757fd  mov     rcx, rax; this
0x180075800  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180075805  mov     edi, 1
0x18007580a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180075811  jb      loc_180076134
0x180075817  mov     edx, 91h
0x18007581c  jmp     loc_180076116
0x180075821  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000; Buf1
0x180075828  mov     r8d, 10h; Size
0x18007582e  mov     rdx, rcx; Buf2
0x180075831  call    memcmp_0
0x180075836  test    eax, eax
0x180075838  jz      short loc_180075887
0x18007583a  mov     rax, [rdi]
0x18007583d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180075844  jnz     short loc_180075851
0x180075846  mov     rax, [rdi+8]
0x18007584a  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180075851  test    rax, rax
0x180075854  jz      short loc_180075887
0x180075856  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x18007585d  jb      loc_180076134
0x180075863  mov     rcx, cs:WPP_GLOBAL_Control
0x18007586a  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180075871  mov     edx, 92h
0x180075876  mov     r9, r14
0x180075879  mov     rcx, [rcx+10h]
0x18007587d  call    WPP_SF_q
0x180075882  jmp     loc_180076134
0x180075887  mov     rax, [rdi]
0x18007588a  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x180075891  jnz     short loc_18007589E
0x180075893  mov     rax, [rdi+8]
0x180075897  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data4
0x18007589e  test    rax, rax
0x1800758a1  jz      loc_1800759AB
0x1800758a7  mov     rax, [rdi]
0x1800758aa  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x1800758b1  jnz     short loc_1800758BE
0x1800758b3  mov     rax, [rdi+8]
0x1800758b7  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data4
0x1800758be  test    rax, rax
0x1800758c1  jz      loc_1800759AB
0x1800758c7  mov     rax, [rdi]
0x1800758ca  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x1800758d1  jnz     short loc_1800758DE
0x1800758d3  mov     rax, [rdi+8]
0x1800758d7  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data4
0x1800758de  test    rax, rax
0x1800758e1  jz      loc_1800759A2
0x1800758e7  mov     rax, [rdi]
0x1800758ea  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800758f1  jnz     short loc_1800758FE
0x1800758f3  mov     rax, [rdi+8]
0x1800758f7  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data4
0x1800758fe  test    rax, rax
0x180075901  jz      loc_1800759A2
0x180075907  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007590e  mov     esi, 0C00D36BBh
0x180075913  mov     ebx, esi
0x180075915  test    rcx, rcx
0x180075918  jnz     short loc_18007595B
0x18007591a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180075920  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180075927  mov     rcx, rax
0x18007592a  test    rax, rax
0x18007592d  jz      short loc_18007594D
0x18007592f  mov     rax, [rax]
0x180075932  mov     edx, 7F0h
0x180075937  mov     rax, [rax+8]
0x18007593b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075940  test    eax, eax
0x180075942  jz      short loc_18007594D
0x180075944  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007594b  jmp     short loc_18007595B
0x18007594d  lea     rcx, qword_1800D6F70; this
0x180075954  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007595b  cmp     [rcx+8], r15b
0x18007595f  jz      short loc_180075982
0x180075961  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075966  cmp     [rax+7CCh], esi
0x18007596c  jz      short loc_180075982
0x18007596e  mov     r9d, esi; int
0x180075971  mov     r8d, 4A8h; int
0x180075977  mov     rdx, r12; char *
0x18007597a  mov     rcx, rax; this
0x18007597d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180075982  mov     edi, 1
0x180075987  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007598e  jb      loc_180076134
0x180075994  mov     edx, 93h
0x180075999  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18007599d  jmp     loc_18007611A
0x1800759a2  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x1800759a9  jmp     short loc_1800759B2
0x1800759ab  movups  xmm0, xmmword ptr cs:MFMediaType_Audio.Data1
0x1800759b2  lea     rdi, [rsi+1D0h]
0x1800759b9  lea     rcx, [rbp+47h+var_60]
0x1800759bd  movdqu  xmmword ptr [rdi], xmm0
0x1800759c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800759c6  mov     rcx, [rbp+47h+var_88]
0x1800759ca  lea     r8, [rbp+47h+var_60]
0x1800759ce  lea     rdx, aMediaencodingp; "MediaEncodingProperties"
0x1800759d5  call    GetSubMapFromMap
0x1800759da  mov     ebx, eax
0x1800759dc  test    eax, eax
0x1800759de  jns     loc_180075A74
0x1800759e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800759eb  test    rcx, rcx
0x1800759ee  jnz     short loc_180075A31
0x1800759f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800759f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800759fd  mov     rcx, rax
0x180075a00  test    rax, rax
0x180075a03  jz      short loc_180075A23
0x180075a05  mov     rax, [rax]
0x180075a08  mov     edx, 7F0h
0x180075a0d  mov     rax, [rax+8]
0x180075a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a16  test    eax, eax
0x180075a18  jz      short loc_180075A23
0x180075a1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075a21  jmp     short loc_180075A31
0x180075a23  lea     rcx, qword_1800D6F70; this
0x180075a2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180075a31  cmp     [rcx+8], r15b
0x180075a35  jz      short loc_180075A58
0x180075a37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075a3c  cmp     [rax+7CCh], ebx
0x180075a42  jz      short loc_180075A58
0x180075a44  mov     r9d, ebx; int
0x180075a47  mov     r8d, 4ACh; int
0x180075a4d  mov     rdx, r12; char *
0x180075a50  mov     rcx, rax; this
0x180075a53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180075a58  mov     edi, 1
0x180075a5d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180075a64  jb      loc_180076134
0x180075a6a  mov     edx, 94h
0x180075a6f  jmp     loc_180076116
0x180075a74  lea     rcx, [rbp+47h+var_70]
0x180075a78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075a7d  mov     rcx, [rbp+47h+var_60]
0x180075a81  lea     r8, [rbp+47h+var_70]
0x180075a85  lea     rdx, aInputtypes; "InputTypes"
0x180075a8c  call    GetSubMapFromMap
0x180075a91  mov     ebx, eax
0x180075a93  test    eax, eax
0x180075a95  jns     loc_180075B2B
0x180075a9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075aa2  test    rcx, rcx
0x180075aa5  jnz     short loc_180075AE8
0x180075aa7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180075aad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180075ab4  mov     rcx, rax
  ... truncated ...
```
