# CAC3MediaSourcePlugin::BuildPresentationDescriptor(CAC3FrameHeader *)

- ea: `0x18012faf0`
- end: `0x1801307e4`
- name: `?BuildPresentationDescriptor@CAC3MediaSourcePlugin@@AEAAJPEAUCAC3FrameHeader@@@Z`
- size: `3316`
- prototype: `int(CAC3MediaSourcePlugin *__hidden this, struct CAC3FrameHeader *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d8870`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180047a00`
- `0x18006ac64`
- `0x180073b14`
- `0x1801099f0`
- `0x18012faf0`
- `0x180130c90`
- `0x180131eb8`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fb60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fc16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fccc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fd94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fe35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fee9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012ff9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130051`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130105`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801301af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013025d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130334`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801303e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013049e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130568`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130609`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801306b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fb60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fc16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fccc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fd94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fe35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012fee9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012ff9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130051`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130105`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801301af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013025d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130334`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801303e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013049e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130568`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180130609`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801306b2`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180130241`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180130241`
- `MFPlat!MFCreateStreamDescriptor` at `0x180130193`
- `MFPlat!MFCreateStreamDescriptor` at `0x180130193`
- `MFPlat!MFCreateMediaType` at `0x18012fbfa`
- `MFPlat!MFCreateMediaType` at `0x18012fbfa`

## string_xrefs

- `0x18012fb18`: `CAC3MediaSourcePlugin::BuildPresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CAC3MediaSourcePlugin::BuildPresentationDescriptor(
        CAC3MediaSourcePlugin *this,
        struct CAC3FrameHeader *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  wchar_t *v7; // rcx
  HRESULT v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  HRESULT (__stdcall *SetGUID)(IMFMediaType *, const GUID *const, const GUID *const); // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  _QWORD *v67; // r14
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rcx
  __int64 v75; // r15
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  wchar_t *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  wchar_t *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  __int64 v94; // rcx
  __int64 (__fastcall *v95)(__int64, const IID *, const wchar_t *); // rax
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // r9
  wchar_t *v99; // rcx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // r9
  wchar_t *v105; // rcx
  CallStackTracing *v106; // rax
  struct CallStackContext *v107; // rax
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // r9
  wchar_t *v111; // rcx
  CallStackTracing *v112; // rax
  struct CallStackContext *v113; // rax
  _BYTE v115[8]; // [rsp+40h] [rbp-20h] BYREF
  IMFMediaType *ppMFType; // [rsp+48h] [rbp-18h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+50h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v115,
    "CAC3MediaSourcePlugin::BuildPresentationDescriptor",
    917);
  ppDescriptor = 0;
  ppMFType = 0;
  if ( !(unsigned int)CAC3FrameHeader::IsValidFrameHeader(a2) )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    v8 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAC3MediaSourcePlugin::BuildPresentationDescriptor",
          925,
          -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 56;
LABEL_191:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids, this, v8);
LABEL_192:
    ComSmartPtr<CMPEGFrame>::operator=((char *)this + 544, 0);
    goto LABEL_196;
  }
  *((_DWORD *)this + 139) = *((unsigned __int16 *)a2 + 3);
  *((_DWORD *)this + 138) = 8 * *((unsigned __int16 *)a2 + 4);
  v8 = MFCreateMediaType(&ppMFType);
  if ( v8 < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v8 )
        CallStackContext::TraceFailure(v17, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 932, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 57;
    goto LABEL_191;
  }
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
         ppMFType,
         &MF_MT_MAJOR_TYPE,
         &MFMediaType_Audio);
  if ( v8 < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != v8 )
        CallStackContext::TraceFailure(v23, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 934, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 58;
    goto LABEL_191;
  }
  SetGUID = ppMFType->lpVtbl->SetGUID;
  if ( (unsigned __int16)(*((_WORD *)a2 + 1) - 11) > 5u )
  {
    v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
           ppMFType,
           &MF_MT_SUBTYPE,
           &MFAudioFormat_Dolby_AC3);
    if ( v8 < 0 )
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != v8 )
          CallStackContext::TraceFailure(v36, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 942, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v11 = 60;
      goto LABEL_191;
    }
  }
  else
  {
    v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
           ppMFType,
           &MF_MT_SUBTYPE,
           &MFAudioFormat_Dolby_DDPlus);
    if ( v8 < 0 )
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != v8 )
          CallStackContext::TraceFailure(v30, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 938, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v11 = 59;
      goto LABEL_191;
    }
  }
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_SAMPLES_PER_SECOND,
         *((unsigned __int16 *)a2 + 3));
  if ( v8 < 0 )
  {
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
      CallStackTracing::s_wpInstance = v41;
      if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v40 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v40 + 8) )
    {
      v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
      if ( *((_DWORD *)v42 + 499) != v8 )
        CallStackContext::TraceFailure(v42, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 945, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 61;
    goto LABEL_191;
  }
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
         *((unsigned __int16 *)a2 + 4));
  if ( v8 < 0 )
  {
    v46 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
      CallStackTracing::s_wpInstance = v47;
      if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v46 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v46 + 8) )
    {
      v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
      if ( *((_DWORD *)v48 + 499) != v8 )
        CallStackContext::TraceFailure(v48, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 946, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 62;
    goto LABEL_191;
  }
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_NUM_CHANNELS,
         *((unsigned __int16 *)a2 + 5));
  if ( v8 < 0 )
  {
    v52 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
      if ( *((_DWORD *)v54 + 499) != v8 )
        CallStackContext::TraceFailure(v54, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 947, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 63;
    goto LABEL_191;
  }
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_CHANNEL_MASK,
         *((unsigned __int16 *)a2 + 6));
  if ( v8 < 0 )
  {
    v58 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
      CallStackTracing::s_wpInstance = v59;
      if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
      {
        v58 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v58 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v58 + 8) )
    {
      v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
      if ( *((_DWORD *)v60 + 499) != v8 )
        CallStackContext::TraceFailure(v60, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 948, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 64;
    goto LABEL_191;
  }
  v8 = MFCreateStreamDescriptor(1u, 1u, &ppMFType, &ppDescriptor);
  if ( v8 < 0 )
  {
    v64 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62, v63);
      CallStackTracing::s_wpInstance = v65;
      if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
      {
        v64 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v64 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v64 + 8) )
    {
      v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
      if ( *((_DWORD *)v66 + 499) != v8 )
        CallStackContext::TraceFailure(v66, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 950, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 65;
    goto LABEL_191;
  }
  v67 = (_QWORD *)((char *)this + 544);
  v8 = MFCreatePresentationDescriptor(1u, &ppDescriptor, (IMFPresentationDescriptor **)this + 68);
  if ( v8 < 0 )
  {
    v71 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
      CallStackTracing::s_wpInstance = v72;
      if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
      {
        v71 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v71 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v71 + 8) )
    {
      v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
      if ( *((_DWORD *)v73 + 499) != v8 )
        CallStackContext::TraceFailure(v73, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 952, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 66;
    goto LABEL_191;
  }
  v74 = *((_QWORD *)this + 70);
  v75 = 0;
  if ( v74 != -1 )
  {
    v75 = llMulDiv(v74, 10000000, *((unsigned __int16 *)a2 + 4), v70);
    v8 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64))(*(_QWORD *)*v67 + 176LL))(*v67, &MF_PD_DURATION, v75);
    if ( v8 < 0 )
    {
      v79 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
        CallStackTracing::s_wpInstance = v80;
        if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
        {
          v79 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v79 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v79 + 8) )
      {
        v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
        if ( *((_DWORD *)v81 + 499) != v8 )
          CallStackContext::TraceFailure(v81, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 958, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v11 = 67;
      goto LABEL_191;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v67 + 176LL))(
           *v67,
           &MF_PD_TOTAL_FILE_SIZE,
           *((_QWORD *)this + 70));
    if ( v8 < 0 )
    {
      v85 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
        CallStackTracing::s_wpInstance = v86;
        if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
        {
          v85 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v85 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v85 + 8) )
      {
        v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
        if ( *((_DWORD *)v87 + 499) != v8 )
          CallStackContext::TraceFailure(v87, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 959, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v11 = 68;
      goto LABEL_191;
    }
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v67 + 168LL))(
         *v67,
         &MF_PD_AUDIO_ENCODING_BITRATE,
         *((unsigned int *)this + 138));
  if ( v8 < 0 )
  {
    v91 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v88, v89, v90);
      CallStackTracing::s_wpInstance = v92;
      if ( v92 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
      {
        v91 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v91 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v91 + 8) )
    {
      v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
      if ( *((_DWORD *)v93 + 499) != v8 )
        CallStackContext::TraceFailure(v93, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 962, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 69;
    goto LABEL_191;
  }
  v94 = *v67;
  v95 = *(__int64 (__fastcall **)(__int64, const IID *, const wchar_t *))(*(_QWORD *)*v67 + 200LL);
  if ( (unsigned __int16)(*((_WORD *)a2 + 1) - 11) > 5u )
  {
    v8 = v95(v94, &MF_PD_MIME_TYPE, L"audio/vnd.dolby.dd-raw");
    if ( v8 < 0 )
    {
      v105 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v102, v103, v104);
        CallStackTracing::s_wpInstance = v106;
        if ( v106 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(v106, 2032) )
        {
          v105 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v105 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v105 + 8) )
      {
        v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v105);
        if ( *((_DWORD *)v107 + 499) != v8 )
          CallStackContext::TraceFailure(v107, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 970, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v11 = 71;
      goto LABEL_191;
    }
  }
  else
  {
    v8 = v95(v94, &MF_PD_MIME_TYPE, L"audio/eac3");
    if ( v8 < 0 )
    {
      v99 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v96, v97, v98);
        CallStackTracing::s_wpInstance = v100;
        if ( v100 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v100 + 8LL))(v100, 2032) )
        {
          v99 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v99 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v99 + 8) )
      {
        v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v99);
        if ( *((_DWORD *)v101 + 499) != v8 )
          CallStackContext::TraceFailure(v101, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 966, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v11 = 70;
      goto LABEL_191;
    }
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v67 + 280LL))(*v67, 0);
  if ( v8 < 0 )
  {
    v111 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v112 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v108, v109, v110);
      CallStackTracing::s_wpInstance = v112;
      if ( v112 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v112 + 8LL))(v112, 2032) )
      {
        v111 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v111 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v111 + 8) )
    {
      v113 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v111);
      if ( *((_DWORD *)v113 + 499) != v8 )
        CallStackContext::TraceFailure(v113, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 973, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v11 = 72;
    goto LABEL_191;
  }
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_qidi(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      73,
      &WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
      this,
      *((_QWORD *)this + 70),
      *((_DWORD *)this + 138),
      v75);
  *((_QWORD *)this + 72) = 0;
LABEL_196:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFType);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppDescriptor);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v115);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18012faf0  mov     [rsp-38h+arg_10], rbx
0x18012faf5  push    rbp
0x18012faf6  push    rsi
0x18012faf7  push    rdi
0x18012faf8  push    r12
0x18012fafa  push    r13
0x18012fafc  push    r14
0x18012fafe  push    r15
0x18012fb00  mov     rbp, rsp
0x18012fb03  sub     rsp, 60h
0x18012fb07  mov     rax, cs:__security_cookie
0x18012fb0e  xor     rax, rsp
0x18012fb11  mov     [rbp+var_8], rax
0x18012fb15  mov     rsi, rdx
0x18012fb18  lea     r13, aCac3mediasourc_1; "CAC3MediaSourcePlugin::BuildPresentatio"...
0x18012fb1f  mov     rdi, rcx
0x18012fb22  mov     rdx, r13; char *
0x18012fb25  mov     r8d, 395h; int
0x18012fb2b  lea     rcx, [rbp+var_20]; this
0x18012fb2f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18012fb34  xor     r12d, r12d
0x18012fb37  mov     rcx, rsi; this
0x18012fb3a  mov     [rbp+ppDescriptor], r12
0x18012fb3e  mov     [rbp+ppMFType], r12
0x18012fb42  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x18012fb47  test    eax, eax
0x18012fb49  jnz     loc_18012FBDF
0x18012fb4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fb56  mov     ebx, 0C00D36BEh
0x18012fb5b  test    rcx, rcx
0x18012fb5e  jnz     short loc_18012FBA1
0x18012fb60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012fb66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fb6d  mov     rcx, rax
0x18012fb70  test    rax, rax
0x18012fb73  jz      short loc_18012FB93
0x18012fb75  mov     rax, [rax]
0x18012fb78  mov     edx, 7F0h
0x18012fb7d  mov     rax, [rax+8]
0x18012fb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fb86  test    eax, eax
0x18012fb88  jz      short loc_18012FB93
0x18012fb8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fb91  jmp     short loc_18012FBA1
0x18012fb93  lea     rcx, qword_1801B07E0; this
0x18012fb9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fba1  cmp     [rcx+8], r12b
0x18012fba5  jz      short loc_18012FBC8
0x18012fba7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012fbac  cmp     [rax+7CCh], ebx
0x18012fbb2  jz      short loc_18012FBC8
0x18012fbb4  mov     r9d, ebx; int
0x18012fbb7  mov     r8d, 39Dh; int
0x18012fbbd  mov     rdx, r13; char *
0x18012fbc0  mov     rcx, rax; this
0x18012fbc3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012fbc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012fbcf  jb      loc_180130746
0x18012fbd5  mov     edx, 38h ; '8'
0x18012fbda  jmp     loc_180130728
0x18012fbdf  movzx   eax, word ptr [rsi+6]
0x18012fbe3  lea     rcx, [rbp+ppMFType]; ppMFType
0x18012fbe7  mov     [rdi+22Ch], eax
0x18012fbed  movzx   eax, word ptr [rsi+8]
0x18012fbf1  shl     eax, 3
0x18012fbf4  mov     [rdi+228h], eax
0x18012fbfa  call    cs:__imp_MFCreateMediaType
0x18012fc00  mov     ebx, eax
0x18012fc02  test    eax, eax
0x18012fc04  jns     loc_18012FC95
0x18012fc0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fc11  test    rcx, rcx
0x18012fc14  jnz     short loc_18012FC57
0x18012fc16  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012fc1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fc23  mov     rcx, rax
0x18012fc26  test    rax, rax
0x18012fc29  jz      short loc_18012FC49
0x18012fc2b  mov     rax, [rax]
0x18012fc2e  mov     edx, 7F0h
0x18012fc33  mov     rax, [rax+8]
0x18012fc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fc3c  test    eax, eax
0x18012fc3e  jz      short loc_18012FC49
0x18012fc40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fc47  jmp     short loc_18012FC57
0x18012fc49  lea     rcx, qword_1801B07E0; this
0x18012fc50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fc57  cmp     [rcx+8], r12b
0x18012fc5b  jz      short loc_18012FC7E
0x18012fc5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012fc62  cmp     [rax+7CCh], ebx
0x18012fc68  jz      short loc_18012FC7E
0x18012fc6a  mov     r9d, ebx; int
0x18012fc6d  mov     r8d, 3A4h; int
0x18012fc73  mov     rdx, r13; char *
0x18012fc76  mov     rcx, rax; this
0x18012fc79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012fc7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012fc85  jb      loc_180130746
0x18012fc8b  mov     edx, 39h ; '9'
0x18012fc90  jmp     loc_180130728
0x18012fc95  mov     rcx, [rbp+ppMFType]
0x18012fc99  lea     r8, MFMediaType_Audio
0x18012fca0  lea     rdx, MF_MT_MAJOR_TYPE
0x18012fca7  mov     rax, [rcx]
0x18012fcaa  mov     rax, [rax+0C0h]
0x18012fcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fcb6  mov     ebx, eax
0x18012fcb8  test    eax, eax
0x18012fcba  jns     loc_18012FD4B
0x18012fcc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fcc7  test    rcx, rcx
0x18012fcca  jnz     short loc_18012FD0D
0x18012fccc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012fcd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fcd9  mov     rcx, rax
0x18012fcdc  test    rax, rax
0x18012fcdf  jz      short loc_18012FCFF
0x18012fce1  mov     rax, [rax]
0x18012fce4  mov     edx, 7F0h
0x18012fce9  mov     rax, [rax+8]
0x18012fced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fcf2  test    eax, eax
0x18012fcf4  jz      short loc_18012FCFF
0x18012fcf6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fcfd  jmp     short loc_18012FD0D
0x18012fcff  lea     rcx, qword_1801B07E0; this
0x18012fd06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fd0d  cmp     [rcx+8], r12b
0x18012fd11  jz      short loc_18012FD34
0x18012fd13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012fd18  cmp     [rax+7CCh], ebx
0x18012fd1e  jz      short loc_18012FD34
0x18012fd20  mov     r9d, ebx; int
0x18012fd23  mov     r8d, 3A6h; int
0x18012fd29  mov     rdx, r13; char *
0x18012fd2c  mov     rcx, rax; this
0x18012fd2f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012fd34  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012fd3b  jb      loc_180130746
0x18012fd41  mov     edx, 3Ah ; ':'
0x18012fd46  jmp     loc_180130728
0x18012fd4b  movzx   eax, word ptr [rsi+2]
0x18012fd4f  lea     rdx, MF_MT_SUBTYPE
0x18012fd56  mov     rcx, [rbp+ppMFType]
0x18012fd5a  sub     ax, 0Bh
0x18012fd5e  cmp     ax, 5
0x18012fd62  mov     rax, [rcx]
0x18012fd65  mov     rax, [rax+0C0h]
0x18012fd6c  ja      loc_18012FE13
0x18012fd72  lea     r8, MFAudioFormat_Dolby_DDPlus
0x18012fd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fd7e  mov     ebx, eax
0x18012fd80  test    eax, eax
0x18012fd82  jns     loc_18012FEB4
0x18012fd88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fd8f  test    rcx, rcx
0x18012fd92  jnz     short loc_18012FDD5
0x18012fd94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012fd9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fda1  mov     rcx, rax
0x18012fda4  test    rax, rax
0x18012fda7  jz      short loc_18012FDC7
0x18012fda9  mov     rax, [rax]
0x18012fdac  mov     edx, 7F0h
0x18012fdb1  mov     rax, [rax+8]
0x18012fdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fdba  test    eax, eax
0x18012fdbc  jz      short loc_18012FDC7
0x18012fdbe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fdc5  jmp     short loc_18012FDD5
0x18012fdc7  lea     rcx, qword_1801B07E0; this
0x18012fdce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fdd5  cmp     [rcx+8], r12b
0x18012fdd9  jz      short loc_18012FDFC
0x18012fddb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012fde0  cmp     [rax+7CCh], ebx
0x18012fde6  jz      short loc_18012FDFC
0x18012fde8  mov     r9d, ebx; int
0x18012fdeb  mov     r8d, 3AAh; int
0x18012fdf1  mov     rdx, r13; char *
0x18012fdf4  mov     rcx, rax; this
0x18012fdf7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012fdfc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012fe03  jb      loc_180130746
0x18012fe09  mov     edx, 3Bh ; ';'
0x18012fe0e  jmp     loc_180130728
0x18012fe13  lea     r8, MFAudioFormat_Dolby_AC3
0x18012fe1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fe1f  mov     ebx, eax
0x18012fe21  test    eax, eax
0x18012fe23  jns     loc_18012FEB4
0x18012fe29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fe30  test    rcx, rcx
0x18012fe33  jnz     short loc_18012FE76
0x18012fe35  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012fe3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fe42  mov     rcx, rax
0x18012fe45  test    rax, rax
0x18012fe48  jz      short loc_18012FE68
0x18012fe4a  mov     rax, [rax]
0x18012fe4d  mov     edx, 7F0h
0x18012fe52  mov     rax, [rax+8]
0x18012fe56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fe5b  test    eax, eax
0x18012fe5d  jz      short loc_18012FE68
0x18012fe5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fe66  jmp     short loc_18012FE76
0x18012fe68  lea     rcx, qword_1801B07E0; this
0x18012fe6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fe76  cmp     [rcx+8], r12b
0x18012fe7a  jz      short loc_18012FE9D
0x18012fe7c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012fe81  cmp     [rax+7CCh], ebx
0x18012fe87  jz      short loc_18012FE9D
0x18012fe89  mov     r9d, ebx; int
0x18012fe8c  mov     r8d, 3AEh; int
0x18012fe92  mov     rdx, r13; char *
0x18012fe95  mov     rcx, rax; this
0x18012fe98  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012fe9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012fea4  jb      loc_180130746
0x18012feaa  mov     edx, 3Ch ; '<'
0x18012feaf  jmp     loc_180130728
0x18012feb4  mov     rcx, [rbp+ppMFType]
0x18012feb8  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x18012febf  movzx   r8d, word ptr [rsi+6]
0x18012fec4  mov     rax, [rcx]
0x18012fec7  mov     rax, [rax+0A8h]
0x18012fece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fed3  mov     ebx, eax
0x18012fed5  test    eax, eax
0x18012fed7  jns     loc_18012FF68
0x18012fedd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fee4  test    rcx, rcx
0x18012fee7  jnz     short loc_18012FF2A
0x18012fee9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012feef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012fef6  mov     rcx, rax
0x18012fef9  test    rax, rax
0x18012fefc  jz      short loc_18012FF1C
0x18012fefe  mov     rax, [rax]
0x18012ff01  mov     edx, 7F0h
0x18012ff06  mov     rax, [rax+8]
0x18012ff0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ff0f  test    eax, eax
0x18012ff11  jz      short loc_18012FF1C
0x18012ff13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012ff1a  jmp     short loc_18012FF2A
0x18012ff1c  lea     rcx, qword_1801B07E0; this
0x18012ff23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012ff2a  cmp     [rcx+8], r12b
0x18012ff2e  jz      short loc_18012FF51
0x18012ff30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012ff35  cmp     [rax+7CCh], ebx
0x18012ff3b  jz      short loc_18012FF51
0x18012ff3d  mov     r9d, ebx; int
0x18012ff40  mov     r8d, 3B1h; int
0x18012ff46  mov     rdx, r13; char *
0x18012ff49  mov     rcx, rax; this
0x18012ff4c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012ff51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012ff58  jb      loc_180130746
0x18012ff5e  mov     edx, 3Dh ; '='
0x18012ff63  jmp     loc_180130728
0x18012ff68  mov     rcx, [rbp+ppMFType]
0x18012ff6c  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x18012ff73  movzx   r8d, word ptr [rsi+8]
0x18012ff78  mov     rax, [rcx]
0x18012ff7b  mov     rax, [rax+0A8h]
0x18012ff82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ff87  mov     ebx, eax
0x18012ff89  test    eax, eax
0x18012ff8b  jns     loc_18013001C
0x18012ff91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012ff98  test    rcx, rcx
0x18012ff9b  jnz     short loc_18012FFDE
0x18012ff9d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012ffa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012ffaa  mov     rcx, rax
0x18012ffad  test    rax, rax
0x18012ffb0  jz      short loc_18012FFD0
0x18012ffb2  mov     rax, [rax]
0x18012ffb5  mov     edx, 7F0h
0x18012ffba  mov     rax, [rax+8]
0x18012ffbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ffc3  test    eax, eax
0x18012ffc5  jz      short loc_18012FFD0
0x18012ffc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012ffce  jmp     short loc_18012FFDE
0x18012ffd0  lea     rcx, qword_1801B07E0; this
0x18012ffd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012ffde  cmp     [rcx+8], r12b
0x18012ffe2  jz      short loc_180130005
0x18012ffe4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012ffe9  cmp     [rax+7CCh], ebx
0x18012ffef  jz      short loc_180130005
0x18012fff1  mov     r9d, ebx; int
0x18012fff4  mov     r8d, 3B2h; int
  ... truncated ...
```
