# CAC3MediaSourcePlugin::BuildPresentationDescriptor(CAC3FrameHeader *)

- ea: `0x180137030`
- end: `0x180137d9d`
- name: `?BuildPresentationDescriptor@CAC3MediaSourcePlugin@@AEAAJPEAUCAC3FrameHeader@@@Z`
- size: `3437`
- prototype: `int(CAC3MediaSourcePlugin *__hidden this, struct CAC3FrameHeader *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800debc0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18004a8a8`
- `0x18006bb54`
- `0x180079680`
- `0x180110ed0`
- `0x180137030`
- `0x180138280`
- `0x1801394f8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801370a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137162`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013721e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801372ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137393`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013744d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137507`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801375c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013767b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137731`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801377eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801378c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137983`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137a3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137b0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137bb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137c64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801370a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137162`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013721e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801372ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137393`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013744d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137507`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801375c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013767b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137731`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801377eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801378c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137983`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137a3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137b0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137bb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180137c64`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1801377c9`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1801377c9`
- `MFPlat!MFCreateStreamDescriptor` at `0x18013770f`
- `MFPlat!MFCreateStreamDescriptor` at `0x18013770f`
- `MFPlat!MFCreateMediaType` at `0x180137140`
- `MFPlat!MFCreateMediaType` at `0x180137140`

## string_xrefs

- `0x180137058`: `CAC3MediaSourcePlugin::BuildPresentationDescriptor`

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
        v5 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v24 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v20 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v28 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v32 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v36 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v40 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v44 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v50 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v56 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v60 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v64 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v74 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v70 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v78 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
0x180137030  mov     [rsp-38h+arg_10], rbx
0x180137035  push    rbp
0x180137036  push    rsi
0x180137037  push    rdi
0x180137038  push    r12
0x18013703a  push    r13
0x18013703c  push    r14
0x18013703e  push    r15
0x180137040  mov     rbp, rsp
0x180137043  sub     rsp, 60h
0x180137047  mov     rax, cs:__security_cookie
0x18013704e  xor     rax, rsp
0x180137051  mov     [rbp+var_8], rax
0x180137055  mov     rsi, rdx
0x180137058  lea     r13, aCac3mediasourc_1; "CAC3MediaSourcePlugin::BuildPresentatio"...
0x18013705f  mov     rdi, rcx
0x180137062  mov     rdx, r13; char *
0x180137065  mov     r8d, 395h; int
0x18013706b  lea     rcx, [rbp+var_20]; this
0x18013706f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180137074  xor     r12d, r12d
0x180137077  mov     rcx, rsi; this
0x18013707a  mov     [rbp+ppDescriptor], r12
0x18013707e  mov     [rbp+ppMFType], r12
0x180137082  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x180137087  test    eax, eax
0x180137089  jnz     loc_180137125
0x18013708f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137096  mov     ebx, 0C00D36BEh
0x18013709b  test    rcx, rcx
0x18013709e  jnz     short loc_1801370E7
0x1801370a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801370a7  nop     dword ptr [rax+rax+00h]
0x1801370ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801370b3  mov     rcx, rax
0x1801370b6  test    rax, rax
0x1801370b9  jz      short loc_1801370D9
0x1801370bb  mov     rax, [rax]
0x1801370be  mov     edx, 7F0h
0x1801370c3  mov     rax, [rax+8]
0x1801370c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801370cc  test    eax, eax
0x1801370ce  jz      short loc_1801370D9
0x1801370d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801370d7  jmp     short loc_1801370E7
0x1801370d9  lea     rcx, qword_1801B97E0; this
0x1801370e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801370e7  cmp     [rcx+8], r12b
0x1801370eb  jz      short loc_18013710E
0x1801370ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801370f2  cmp     [rax+7CCh], ebx
0x1801370f8  jz      short loc_18013710E
0x1801370fa  mov     r9d, ebx; int
0x1801370fd  mov     r8d, 39Dh; int
0x180137103  mov     rdx, r13; char *
0x180137106  mov     rcx, rax; this
0x180137109  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013710e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180137115  jb      loc_180137CFE
0x18013711b  mov     edx, 38h ; '8'
0x180137120  jmp     loc_180137CE0
0x180137125  movzx   eax, word ptr [rsi+6]
0x180137129  lea     rcx, [rbp+ppMFType]; ppMFType
0x18013712d  mov     [rdi+22Ch], eax
0x180137133  movzx   eax, word ptr [rsi+8]
0x180137137  shl     eax, 3
0x18013713a  mov     [rdi+228h], eax
0x180137140  call    cs:__imp_MFCreateMediaType
0x180137147  nop     dword ptr [rax+rax+00h]
0x18013714c  mov     ebx, eax
0x18013714e  test    eax, eax
0x180137150  jns     loc_1801371E7
0x180137156  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013715d  test    rcx, rcx
0x180137160  jnz     short loc_1801371A9
0x180137162  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180137169  nop     dword ptr [rax+rax+00h]
0x18013716e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180137175  mov     rcx, rax
0x180137178  test    rax, rax
0x18013717b  jz      short loc_18013719B
0x18013717d  mov     rax, [rax]
0x180137180  mov     edx, 7F0h
0x180137185  mov     rax, [rax+8]
0x180137189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013718e  test    eax, eax
0x180137190  jz      short loc_18013719B
0x180137192  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137199  jmp     short loc_1801371A9
0x18013719b  lea     rcx, qword_1801B97E0; this
0x1801371a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801371a9  cmp     [rcx+8], r12b
0x1801371ad  jz      short loc_1801371D0
0x1801371af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801371b4  cmp     [rax+7CCh], ebx
0x1801371ba  jz      short loc_1801371D0
0x1801371bc  mov     r9d, ebx; int
0x1801371bf  mov     r8d, 3A4h; int
0x1801371c5  mov     rdx, r13; char *
0x1801371c8  mov     rcx, rax; this
0x1801371cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801371d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801371d7  jb      loc_180137CFE
0x1801371dd  mov     edx, 39h ; '9'
0x1801371e2  jmp     loc_180137CE0
0x1801371e7  mov     rcx, [rbp+ppMFType]
0x1801371eb  lea     r8, MFMediaType_Audio
0x1801371f2  lea     rdx, MF_MT_MAJOR_TYPE
0x1801371f9  mov     rax, [rcx]
0x1801371fc  mov     rax, [rax+0C0h]
0x180137203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137208  mov     ebx, eax
0x18013720a  test    eax, eax
0x18013720c  jns     loc_1801372A3
0x180137212  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137219  test    rcx, rcx
0x18013721c  jnz     short loc_180137265
0x18013721e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180137225  nop     dword ptr [rax+rax+00h]
0x18013722a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180137231  mov     rcx, rax
0x180137234  test    rax, rax
0x180137237  jz      short loc_180137257
0x180137239  mov     rax, [rax]
0x18013723c  mov     edx, 7F0h
0x180137241  mov     rax, [rax+8]
0x180137245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013724a  test    eax, eax
0x18013724c  jz      short loc_180137257
0x18013724e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137255  jmp     short loc_180137265
0x180137257  lea     rcx, qword_1801B97E0; this
0x18013725e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180137265  cmp     [rcx+8], r12b
0x180137269  jz      short loc_18013728C
0x18013726b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180137270  cmp     [rax+7CCh], ebx
0x180137276  jz      short loc_18013728C
0x180137278  mov     r9d, ebx; int
0x18013727b  mov     r8d, 3A6h; int
0x180137281  mov     rdx, r13; char *
0x180137284  mov     rcx, rax; this
0x180137287  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013728c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180137293  jb      loc_180137CFE
0x180137299  mov     edx, 3Ah ; ':'
0x18013729e  jmp     loc_180137CE0
0x1801372a3  movzx   eax, word ptr [rsi+2]
0x1801372a7  lea     rdx, MF_MT_SUBTYPE
0x1801372ae  mov     rcx, [rbp+ppMFType]
0x1801372b2  sub     ax, 0Bh
0x1801372b6  cmp     ax, 5
0x1801372ba  mov     rax, [rcx]
0x1801372bd  mov     rax, [rax+0C0h]
0x1801372c4  ja      loc_180137371
0x1801372ca  lea     r8, MFAudioFormat_Dolby_DDPlus
0x1801372d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801372d6  mov     ebx, eax
0x1801372d8  test    eax, eax
0x1801372da  jns     loc_180137418
0x1801372e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801372e7  test    rcx, rcx
0x1801372ea  jnz     short loc_180137333
0x1801372ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801372f3  nop     dword ptr [rax+rax+00h]
0x1801372f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801372ff  mov     rcx, rax
0x180137302  test    rax, rax
0x180137305  jz      short loc_180137325
0x180137307  mov     rax, [rax]
0x18013730a  mov     edx, 7F0h
0x18013730f  mov     rax, [rax+8]
0x180137313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137318  test    eax, eax
0x18013731a  jz      short loc_180137325
0x18013731c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137323  jmp     short loc_180137333
0x180137325  lea     rcx, qword_1801B97E0; this
0x18013732c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180137333  cmp     [rcx+8], r12b
0x180137337  jz      short loc_18013735A
0x180137339  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013733e  cmp     [rax+7CCh], ebx
0x180137344  jz      short loc_18013735A
0x180137346  mov     r9d, ebx; int
0x180137349  mov     r8d, 3AAh; int
0x18013734f  mov     rdx, r13; char *
0x180137352  mov     rcx, rax; this
0x180137355  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013735a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180137361  jb      loc_180137CFE
0x180137367  mov     edx, 3Bh ; ';'
0x18013736c  jmp     loc_180137CE0
0x180137371  lea     r8, MFAudioFormat_Dolby_AC3
0x180137378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013737d  mov     ebx, eax
0x18013737f  test    eax, eax
0x180137381  jns     loc_180137418
0x180137387  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013738e  test    rcx, rcx
0x180137391  jnz     short loc_1801373DA
0x180137393  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013739a  nop     dword ptr [rax+rax+00h]
0x18013739f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801373a6  mov     rcx, rax
0x1801373a9  test    rax, rax
0x1801373ac  jz      short loc_1801373CC
0x1801373ae  mov     rax, [rax]
0x1801373b1  mov     edx, 7F0h
0x1801373b6  mov     rax, [rax+8]
0x1801373ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801373bf  test    eax, eax
0x1801373c1  jz      short loc_1801373CC
0x1801373c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801373ca  jmp     short loc_1801373DA
0x1801373cc  lea     rcx, qword_1801B97E0; this
0x1801373d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801373da  cmp     [rcx+8], r12b
0x1801373de  jz      short loc_180137401
0x1801373e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801373e5  cmp     [rax+7CCh], ebx
0x1801373eb  jz      short loc_180137401
0x1801373ed  mov     r9d, ebx; int
0x1801373f0  mov     r8d, 3AEh; int
0x1801373f6  mov     rdx, r13; char *
0x1801373f9  mov     rcx, rax; this
0x1801373fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180137401  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180137408  jb      loc_180137CFE
0x18013740e  mov     edx, 3Ch ; '<'
0x180137413  jmp     loc_180137CE0
0x180137418  mov     rcx, [rbp+ppMFType]
0x18013741c  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180137423  movzx   r8d, word ptr [rsi+6]
0x180137428  mov     rax, [rcx]
0x18013742b  mov     rax, [rax+0A8h]
0x180137432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137437  mov     ebx, eax
0x180137439  test    eax, eax
0x18013743b  jns     loc_1801374D2
0x180137441  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137448  test    rcx, rcx
0x18013744b  jnz     short loc_180137494
0x18013744d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180137454  nop     dword ptr [rax+rax+00h]
0x180137459  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180137460  mov     rcx, rax
0x180137463  test    rax, rax
0x180137466  jz      short loc_180137486
0x180137468  mov     rax, [rax]
0x18013746b  mov     edx, 7F0h
0x180137470  mov     rax, [rax+8]
0x180137474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137479  test    eax, eax
0x18013747b  jz      short loc_180137486
0x18013747d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137484  jmp     short loc_180137494
0x180137486  lea     rcx, qword_1801B97E0; this
0x18013748d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180137494  cmp     [rcx+8], r12b
0x180137498  jz      short loc_1801374BB
0x18013749a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013749f  cmp     [rax+7CCh], ebx
0x1801374a5  jz      short loc_1801374BB
0x1801374a7  mov     r9d, ebx; int
0x1801374aa  mov     r8d, 3B1h; int
0x1801374b0  mov     rdx, r13; char *
0x1801374b3  mov     rcx, rax; this
0x1801374b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801374bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801374c2  jb      loc_180137CFE
0x1801374c8  mov     edx, 3Dh ; '='
0x1801374cd  jmp     loc_180137CE0
0x1801374d2  mov     rcx, [rbp+ppMFType]
0x1801374d6  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x1801374dd  movzx   r8d, word ptr [rsi+8]
0x1801374e2  mov     rax, [rcx]
0x1801374e5  mov     rax, [rax+0A8h]
0x1801374ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801374f1  mov     ebx, eax
0x1801374f3  test    eax, eax
0x1801374f5  jns     loc_18013758C
0x1801374fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180137502  test    rcx, rcx
0x180137505  jnz     short loc_18013754E
0x180137507  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013750e  nop     dword ptr [rax+rax+00h]
0x180137513  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013751a  mov     rcx, rax
0x18013751d  test    rax, rax
0x180137520  jz      short loc_180137540
0x180137522  mov     rax, [rax]
0x180137525  mov     edx, 7F0h
0x18013752a  mov     rax, [rax+8]
0x18013752e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137533  test    eax, eax
0x180137535  jz      short loc_180137540
0x180137537  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013753e  jmp     short loc_18013754E
0x180137540  lea     rcx, qword_1801B97E0; this
  ... truncated ...
```
