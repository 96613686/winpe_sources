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
  wchar_t *v5; // rcx
  HRESULT v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  HRESULT (__stdcall *SetGUID)(IMFMediaType *, const GUID *const, const GUID *const); // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  _QWORD *v47; // r14
  __int64 v48; // rdx
  __int64 v49; // r9
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // r15
  __int64 v55; // rdx
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rcx
  __int64 (__fastcall *v68)(__int64, const IID *, const wchar_t *); // rax
  __int64 v69; // rdx
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  wchar_t *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  wchar_t *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  _BYTE v82[8]; // [rsp+40h] [rbp-20h] BYREF
  IMFMediaType *ppMFType; // [rsp+48h] [rbp-18h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+50h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v82,
    "CAC3MediaSourcePlugin::BuildPresentationDescriptor",
    917);
  ppDescriptor = 0;
  ppMFType = 0;
  if ( !(unsigned int)CAC3FrameHeader::IsValidFrameHeader(a2) )
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    v6 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAC3MediaSourcePlugin::BuildPresentationDescriptor",
          925,
          -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 56;
LABEL_191:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids, this, v6);
LABEL_192:
    ComSmartPtr<CMPEGFrame>::operator=((char *)this + 544, 0);
    goto LABEL_196;
  }
  *((_DWORD *)this + 139) = *((unsigned __int16 *)a2 + 3);
  *((_DWORD *)this + 138) = 8 * *((unsigned __int16 *)a2 + 4);
  v6 = MFCreateMediaType(&ppMFType);
  if ( v6 < 0 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v6 )
        CallStackContext::TraceFailure(v13, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 932, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 57;
    goto LABEL_191;
  }
  v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
         ppMFType,
         &MF_MT_MAJOR_TYPE,
         &MFMediaType_Audio);
  if ( v6 < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
      if ( *((_DWORD *)v17 + 499) != v6 )
        CallStackContext::TraceFailure(v17, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 934, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 58;
    goto LABEL_191;
  }
  SetGUID = ppMFType->lpVtbl->SetGUID;
  if ( (unsigned __int16)(*((_WORD *)a2 + 1) - 11) > 5u )
  {
    v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
           ppMFType,
           &MF_MT_SUBTYPE,
           &MFAudioFormat_Dolby_AC3);
    if ( v6 < 0 )
    {
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v6 )
          CallStackContext::TraceFailure(v26, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 942, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v9 = 60;
      goto LABEL_191;
    }
  }
  else
  {
    v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
           ppMFType,
           &MF_MT_SUBTYPE,
           &MFAudioFormat_Dolby_DDPlus);
    if ( v6 < 0 )
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v6 )
          CallStackContext::TraceFailure(v22, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 938, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v9 = 59;
      goto LABEL_191;
    }
  }
  v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_SAMPLES_PER_SECOND,
         *((unsigned __int16 *)a2 + 3));
  if ( v6 < 0 )
  {
    v28 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
      if ( *((_DWORD *)v30 + 499) != v6 )
        CallStackContext::TraceFailure(v30, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 945, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 61;
    goto LABEL_191;
  }
  v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
         *((unsigned __int16 *)a2 + 4));
  if ( v6 < 0 )
  {
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != v6 )
        CallStackContext::TraceFailure(v34, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 946, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 62;
    goto LABEL_191;
  }
  v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_NUM_CHANNELS,
         *((unsigned __int16 *)a2 + 5));
  if ( v6 < 0 )
  {
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v36 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v36 + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v38 + 499) != v6 )
        CallStackContext::TraceFailure(v38, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 947, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 63;
    goto LABEL_191;
  }
  v6 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_AUDIO_CHANNEL_MASK,
         *((unsigned __int16 *)a2 + 6));
  if ( v6 < 0 )
  {
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
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
      if ( *((_DWORD *)v42 + 499) != v6 )
        CallStackContext::TraceFailure(v42, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 948, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 64;
    goto LABEL_191;
  }
  v6 = MFCreateStreamDescriptor(1u, 1u, &ppMFType, &ppDescriptor);
  if ( v6 < 0 )
  {
    v44 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
      CallStackTracing::s_wpInstance = v45;
      if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v44 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v44 + 8) )
    {
      v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
      if ( *((_DWORD *)v46 + 499) != v6 )
        CallStackContext::TraceFailure(v46, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 950, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 65;
    goto LABEL_191;
  }
  v47 = (_QWORD *)((char *)this + 544);
  v6 = MFCreatePresentationDescriptor(1u, &ppDescriptor, (IMFPresentationDescriptor **)this + 68);
  if ( v6 < 0 )
  {
    v50 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
      CallStackTracing::s_wpInstance = v51;
      if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
      {
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v52 + 499) != v6 )
        CallStackContext::TraceFailure(v52, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 952, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 66;
    goto LABEL_191;
  }
  v53 = *((_QWORD *)this + 70);
  v54 = 0;
  if ( v53 != -1 )
  {
    v54 = llMulDiv(v53, 10000000, *((unsigned __int16 *)a2 + 4), v49);
    v6 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64))(*(_QWORD *)*v47 + 176LL))(*v47, &MF_PD_DURATION, v54);
    if ( v6 < 0 )
    {
      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)v58 + 499) != v6 )
          CallStackContext::TraceFailure(v58, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 958, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v9 = 67;
      goto LABEL_191;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v47 + 176LL))(
           *v47,
           &MF_PD_TOTAL_FILE_SIZE,
           *((_QWORD *)this + 70));
    if ( v6 < 0 )
    {
      v60 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
        CallStackTracing::s_wpInstance = v61;
        if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
        {
          v60 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v60 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v60 + 8) )
      {
        v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
        if ( *((_DWORD *)v62 + 499) != v6 )
          CallStackContext::TraceFailure(v62, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 959, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v9 = 68;
      goto LABEL_191;
    }
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v47 + 168LL))(
         *v47,
         &MF_PD_AUDIO_ENCODING_BITRATE,
         *((unsigned int *)this + 138));
  if ( v6 < 0 )
  {
    v64 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63);
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
      if ( *((_DWORD *)v66 + 499) != v6 )
        CallStackContext::TraceFailure(v66, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 962, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 69;
    goto LABEL_191;
  }
  v67 = *v47;
  v68 = *(__int64 (__fastcall **)(__int64, const IID *, const wchar_t *))(*(_QWORD *)*v47 + 200LL);
  if ( (unsigned __int16)(*((_WORD *)a2 + 1) - 11) > 5u )
  {
    v6 = v68(v67, &MF_PD_MIME_TYPE, L"audio/vnd.dolby.dd-raw");
    if ( v6 < 0 )
    {
      v74 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73);
        CallStackTracing::s_wpInstance = v75;
        if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
        {
          v74 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v74 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
        if ( *((_DWORD *)v76 + 499) != v6 )
          CallStackContext::TraceFailure(v76, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 970, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v9 = 71;
      goto LABEL_191;
    }
  }
  else
  {
    v6 = v68(v67, &MF_PD_MIME_TYPE, L"audio/eac3");
    if ( v6 < 0 )
    {
      v70 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v69);
        CallStackTracing::s_wpInstance = v71;
        if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
        {
          v70 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v70 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v70 + 8) )
      {
        v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
        if ( *((_DWORD *)v72 + 499) != v6 )
          CallStackContext::TraceFailure(v72, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 966, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_192;
      v9 = 70;
      goto LABEL_191;
    }
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v47 + 280LL))(*v47, 0);
  if ( v6 < 0 )
  {
    v78 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77);
      CallStackTracing::s_wpInstance = v79;
      if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
      {
        v78 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v78 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v78 + 8) )
    {
      v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
      if ( *((_DWORD *)v80 + 499) != v6 )
        CallStackContext::TraceFailure(v80, "CAC3MediaSourcePlugin::BuildPresentationDescriptor", 973, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_192;
    v9 = 72;
    goto LABEL_191;
  }
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_qidi(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      73,
      WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
      this,
      *((_QWORD *)this + 70),
      *((_DWORD *)this + 138),
      v54);
  *((_QWORD *)this + 72) = 0;
LABEL_196:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFType);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppDescriptor);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v82);
  return (unsigned int)v6;
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
