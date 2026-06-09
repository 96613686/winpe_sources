# CreateCodecInfoFromMediaExtensionMap(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,CodecPackInfo &,bool *)

- ea: `0x1800789cc`
- end: `0x180079656`
- name: `?CreateCodecInfoFromMediaExtensionMap@@YAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUCodecPackInfo@@PEA_N@Z`
- size: `3210`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004cdb4`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b58`
- `0x180021b9c`
- `0x1800744d8`
- `0x180078554`
- `0x1800789cc`
- `0x18007a670`
- `0x18007ab98`
- `0x18007adf8`
- `0x18007b64c`
- `0x18007bff8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800792d0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800792d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800795e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800795f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800795e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800795f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800792e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800792e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800792b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800792b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078a67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078b2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078bdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078d62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078e3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078efb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007906f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800791d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007930a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800793cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007953c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078a67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078b2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078bdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078d62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078e3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078efb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007906f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800791d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007930a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800793cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007953c`

## string_xrefs

- `0x1800789fc`: `CreateCodecInfoFromMediaExtensionMap`

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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
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
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, a4);
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
              v35 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v43 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v49 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v55 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v61 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v67 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v73 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v80 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v83 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
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
            v95 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v89 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v17 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x1800789cc  mov     [rsp-8+arg_0], rbx
0x1800789d1  mov     [rsp-8+arg_8], rsi
0x1800789d6  push    rbp
0x1800789d7  push    rdi
0x1800789d8  push    r12
0x1800789da  push    r14
0x1800789dc  push    r15
0x1800789de  lea     rbp, [rsp-27h]
0x1800789e3  sub     rsp, 0A0h
0x1800789ea  mov     rax, cs:__security_cookie
0x1800789f1  xor     rax, rsp
0x1800789f4  mov     [rbp+47h+var_30], rax
0x1800789f8  mov     rsi, [rbp+47h+arg_20]
0x1800789fc  lea     r12, aCreatecodecinf; "CreateCodecInfoFromMediaExtensionMap"
0x180078a03  xor     r15d, r15d
0x180078a06  lea     rcx, [rbp+47h+var_90]; this
0x180078a0a  mov     edi, 48Fh
0x180078a0f  mov     [rbp+47h+var_88], r15
0x180078a13  mov     r8d, edi; int
0x180078a16  mov     [rbp+47h+var_60], r15
0x180078a1a  mov     rdx, r12; char *
0x180078a1d  mov     [rbp+47h+var_70], r15
0x180078a21  mov     r14, r9
0x180078a24  mov     [rbp+47h+var_58], r15
0x180078a28  mov     [rbp+47h+string], r15
0x180078a2c  mov     [rbp+47h+string1], r15
0x180078a30  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180078a35  lea     rcx, [rbp+47h+var_88]
0x180078a39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180078a3e  lea     r8, [rbp+47h+var_88]
0x180078a42  mov     rcx, r14
0x180078a45  lea     rdx, aMediacodec; "MediaCodec"
0x180078a4c  call    GetSubMapFromMap
0x180078a51  mov     ebx, eax
0x180078a53  test    eax, eax
0x180078a55  jns     loc_180078AEE
0x180078a5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078a62  test    rcx, rcx
0x180078a65  jnz     short loc_180078AAE
0x180078a67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078a6e  nop     dword ptr [rax+rax+00h]
0x180078a73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078a7a  mov     rcx, rax
0x180078a7d  test    rax, rax
0x180078a80  jz      short loc_180078AA0
0x180078a82  mov     rax, [rax]
0x180078a85  mov     edx, 7F0h
0x180078a8a  mov     rax, [rax+8]
0x180078a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a93  test    eax, eax
0x180078a95  jz      short loc_180078AA0
0x180078a97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078a9e  jmp     short loc_180078AAE
0x180078aa0  lea     rcx, qword_1800DBF70; this
0x180078aa7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078aae  cmp     [rcx+8], r15b
0x180078ab2  jz      short loc_180078AD2
0x180078ab4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078ab9  cmp     [rax+7CCh], ebx
0x180078abf  jz      short loc_180078AD2
0x180078ac1  mov     r9d, ebx; int
0x180078ac4  mov     r8d, edi; int
0x180078ac7  mov     rdx, r12; char *
0x180078aca  mov     rcx, rax; this
0x180078acd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078ad2  mov     edi, 1
0x180078ad7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180078ade  jb      loc_1800795D6
0x180078ae4  mov     edx, 8Fh
0x180078ae9  jmp     loc_1800795B8
0x180078aee  mov     rcx, [rbp+47h+string]; string
0x180078af2  call    cs:__imp_WindowsDeleteString
0x180078af9  nop     dword ptr [rax+rax+00h]
0x180078afe  mov     rcx, [rbp+47h+var_88]
0x180078b02  lea     r8, [rbp+47h+string]
0x180078b06  lea     rdx, aCategory; "@Category"
0x180078b0d  mov     [rbp+47h+string], r15
0x180078b11  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180078b16  mov     ebx, eax
0x180078b18  test    eax, eax
0x180078b1a  jns     loc_180078BB6
0x180078b20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078b27  test    rcx, rcx
0x180078b2a  jnz     short loc_180078B73
0x180078b2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078b33  nop     dword ptr [rax+rax+00h]
0x180078b38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078b3f  mov     rcx, rax
0x180078b42  test    rax, rax
0x180078b45  jz      short loc_180078B65
0x180078b47  mov     rax, [rax]
0x180078b4a  mov     edx, 7F0h
0x180078b4f  mov     rax, [rax+8]
0x180078b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b58  test    eax, eax
0x180078b5a  jz      short loc_180078B65
0x180078b5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078b63  jmp     short loc_180078B73
0x180078b65  lea     rcx, qword_1800DBF70; this
0x180078b6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078b73  cmp     [rcx+8], r15b
0x180078b77  jz      short loc_180078B9A
0x180078b79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078b7e  cmp     [rax+7CCh], ebx
0x180078b84  jz      short loc_180078B9A
0x180078b86  mov     r9d, ebx; int
0x180078b89  mov     r8d, 490h; int
0x180078b8f  mov     rdx, r12; char *
0x180078b92  mov     rcx, rax; this
0x180078b95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078b9a  mov     edi, 1
0x180078b9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180078ba6  jb      loc_1800795D6
0x180078bac  mov     edx, 90h
0x180078bb1  jmp     loc_1800795B8
0x180078bb6  mov     rcx, [rbp+47h+string]; string1
0x180078bba  lea     rdi, [rsi+1C0h]
0x180078bc1  mov     rdx, rdi; struct _GUID *
0x180078bc4  call    ?CreateCodecCategoryFromString@@YAJPEAUHSTRING__@@PEAU_GUID@@@Z; CreateCodecCategoryFromString(HSTRING__ *,_GUID *)
0x180078bc9  mov     ebx, eax
0x180078bcb  test    eax, eax
0x180078bcd  jns     loc_180078C69
0x180078bd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078bda  test    rcx, rcx
0x180078bdd  jnz     short loc_180078C26
0x180078bdf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078be6  nop     dword ptr [rax+rax+00h]
0x180078beb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078bf2  mov     rcx, rax
0x180078bf5  test    rax, rax
0x180078bf8  jz      short loc_180078C18
0x180078bfa  mov     rax, [rax]
0x180078bfd  mov     edx, 7F0h
0x180078c02  mov     rax, [rax+8]
0x180078c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c0b  test    eax, eax
0x180078c0d  jz      short loc_180078C18
0x180078c0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078c16  jmp     short loc_180078C26
0x180078c18  lea     rcx, qword_1800DBF70; this
0x180078c1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078c26  cmp     [rcx+8], r15b
0x180078c2a  jz      short loc_180078C4D
0x180078c2c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078c31  cmp     [rax+7CCh], ebx
0x180078c37  jz      short loc_180078C4D
0x180078c39  mov     r9d, ebx; int
0x180078c3c  mov     r8d, 491h; int
0x180078c42  mov     rdx, r12; char *
0x180078c45  mov     rcx, rax; this
0x180078c48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078c4d  mov     edi, 1
0x180078c52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180078c59  jb      loc_1800795D6
0x180078c5f  mov     edx, 91h
0x180078c64  jmp     loc_1800795B8
0x180078c69  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000; Buf1
0x180078c70  mov     r8d, 10h; Size
0x180078c76  mov     rdx, rcx; Buf2
0x180078c79  call    memcmp_0
0x180078c7e  test    eax, eax
0x180078c80  jz      short loc_180078CCF
0x180078c82  mov     rax, [rdi]
0x180078c85  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180078c8c  jnz     short loc_180078C99
0x180078c8e  mov     rax, [rdi+8]
0x180078c92  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180078c99  test    rax, rax
0x180078c9c  jz      short loc_180078CCF
0x180078c9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180078ca5  jb      loc_1800795D6
0x180078cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180078cb2  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180078cb9  mov     edx, 92h
0x180078cbe  mov     r9, r14
0x180078cc1  mov     rcx, [rcx+10h]
0x180078cc5  call    WPP_SF_q
0x180078cca  jmp     loc_1800795D6
0x180078ccf  mov     rax, [rdi]
0x180078cd2  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x180078cd9  jnz     short loc_180078CE6
0x180078cdb  mov     rax, [rdi+8]
0x180078cdf  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data4
0x180078ce6  test    rax, rax
0x180078ce9  jz      loc_180078DF9
0x180078cef  mov     rax, [rdi]
0x180078cf2  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x180078cf9  jnz     short loc_180078D06
0x180078cfb  mov     rax, [rdi+8]
0x180078cff  sub     rax, qword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data4
0x180078d06  test    rax, rax
0x180078d09  jz      loc_180078DF9
0x180078d0f  mov     rax, [rdi]
0x180078d12  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x180078d19  jnz     short loc_180078D26
0x180078d1b  mov     rax, [rdi+8]
0x180078d1f  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data4
0x180078d26  test    rax, rax
0x180078d29  jz      loc_180078DF0
0x180078d2f  mov     rax, [rdi]
0x180078d32  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x180078d39  jnz     short loc_180078D46
0x180078d3b  mov     rax, [rdi+8]
0x180078d3f  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data4
0x180078d46  test    rax, rax
0x180078d49  jz      loc_180078DF0
0x180078d4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078d56  mov     esi, 0C00D36BBh
0x180078d5b  mov     ebx, esi
0x180078d5d  test    rcx, rcx
0x180078d60  jnz     short loc_180078DA9
0x180078d62  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078d69  nop     dword ptr [rax+rax+00h]
0x180078d6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078d75  mov     rcx, rax
0x180078d78  test    rax, rax
0x180078d7b  jz      short loc_180078D9B
0x180078d7d  mov     rax, [rax]
0x180078d80  mov     edx, 7F0h
0x180078d85  mov     rax, [rax+8]
0x180078d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d8e  test    eax, eax
0x180078d90  jz      short loc_180078D9B
0x180078d92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078d99  jmp     short loc_180078DA9
0x180078d9b  lea     rcx, qword_1800DBF70; this
0x180078da2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078da9  cmp     [rcx+8], r15b
0x180078dad  jz      short loc_180078DD0
0x180078daf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078db4  cmp     [rax+7CCh], esi
0x180078dba  jz      short loc_180078DD0
0x180078dbc  mov     r9d, esi; int
0x180078dbf  mov     r8d, 4A8h; int
0x180078dc5  mov     rdx, r12; char *
0x180078dc8  mov     rcx, rax; this
0x180078dcb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078dd0  mov     edi, 1
0x180078dd5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180078ddc  jb      loc_1800795D6
0x180078de2  mov     edx, 93h
0x180078de7  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180078deb  jmp     loc_1800795BC
0x180078df0  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x180078df7  jmp     short loc_180078E00
0x180078df9  movups  xmm0, xmmword ptr cs:MFMediaType_Audio.Data1
0x180078e00  lea     rdi, [rsi+1D0h]
0x180078e07  lea     rcx, [rbp+47h+var_60]
0x180078e0b  movdqu  xmmword ptr [rdi], xmm0
0x180078e0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180078e14  mov     rcx, [rbp+47h+var_88]
0x180078e18  lea     r8, [rbp+47h+var_60]
0x180078e1c  lea     rdx, aMediaencodingp; "MediaEncodingProperties"
0x180078e23  call    GetSubMapFromMap
0x180078e28  mov     ebx, eax
0x180078e2a  test    eax, eax
0x180078e2c  jns     loc_180078EC8
0x180078e32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078e39  test    rcx, rcx
0x180078e3c  jnz     short loc_180078E85
0x180078e3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078e45  nop     dword ptr [rax+rax+00h]
0x180078e4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078e51  mov     rcx, rax
0x180078e54  test    rax, rax
0x180078e57  jz      short loc_180078E77
0x180078e59  mov     rax, [rax]
0x180078e5c  mov     edx, 7F0h
0x180078e61  mov     rax, [rax+8]
0x180078e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e6a  test    eax, eax
0x180078e6c  jz      short loc_180078E77
0x180078e6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078e75  jmp     short loc_180078E85
0x180078e77  lea     rcx, qword_1800DBF70; this
0x180078e7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078e85  cmp     [rcx+8], r15b
0x180078e89  jz      short loc_180078EAC
0x180078e8b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078e90  cmp     [rax+7CCh], ebx
0x180078e96  jz      short loc_180078EAC
0x180078e98  mov     r9d, ebx; int
0x180078e9b  mov     r8d, 4ACh; int
0x180078ea1  mov     rdx, r12; char *
0x180078ea4  mov     rcx, rax; this
0x180078ea7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078eac  mov     edi, 1
0x180078eb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180078eb8  jb      loc_1800795D6
0x180078ebe  mov     edx, 94h
0x180078ec3  jmp     loc_1800795B8
0x180078ec8  lea     rcx, [rbp+47h+var_70]
0x180078ecc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180078ed1  mov     rcx, [rbp+47h+var_60]
0x180078ed5  lea     r8, [rbp+47h+var_70]
0x180078ed9  lea     rdx, aInputtypes; "InputTypes"
0x180078ee0  call    GetSubMapFromMap
0x180078ee5  mov     ebx, eax
0x180078ee7  test    eax, eax
0x180078ee9  jns     loc_180078F85
  ... truncated ...
```
