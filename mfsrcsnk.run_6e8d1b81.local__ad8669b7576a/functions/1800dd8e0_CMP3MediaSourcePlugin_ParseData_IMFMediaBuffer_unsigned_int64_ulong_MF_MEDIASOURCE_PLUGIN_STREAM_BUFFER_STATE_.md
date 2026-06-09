# CMP3MediaSourcePlugin::ParseData(IMFMediaBuffer *,unsigned __int64,ulong,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *,unsigned __int64 *)

- ea: `0x1800dd8e0`
- end: `0x1800de3dc`
- name: `?ParseData@CMP3MediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@_KKPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@PEA_K@Z`
- size: `2812`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct IMFMediaBuffer *, HANDLE, __int64, struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800086c8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180034dcc`
- `0x180055890`
- `0x180060768`
- `0x180073b14`
- `0x1800b4a38`
- `0x1800dd8e0`
- `0x1800f4d04`
- `0x1801099f0`
- `0x18011b1e4`
- `0x180131f44`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de3ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de3ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dd920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dd920`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd97f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dda91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddb53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddda4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dde33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddec2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddf51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddfe0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de08e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de13c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de1e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de2e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd97f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dda91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddb53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddda4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dde33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddec2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddf51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddfe0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de08e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de13c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de1e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800de2e2`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800ddc5a`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800de2c6`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800ddc5a`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800de2c6`
- `MFPlat!MFCreateSample` at `0x1800ddc72`
- `MFPlat!MFCreateSample` at `0x1800ddc72`

## string_xrefs

- `0x1800dd92c`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800dd9d6`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800ddae8`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800ddbaa`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800dddfb`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800dde8a`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800ddf19`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800ddfa8`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800de037`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800de0e5`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800de193`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800de23f`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800de339`: `CMP3MediaSourcePlugin::ParseData`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::ParseData(
        struct _RTL_CRITICAL_SECTION *this,
        struct IMFMediaBuffer *a2,
        HANDLE a3,
        __int64 a4,
        struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *a5,
        unsigned __int64 *a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  struct IMFMediaBufferVtbl *lpVtbl; // rax
  bool v11; // r12
  HANDLE *p_LockSemaphore; // rsi
  __int64 v13; // rdx
  HRESULT MP3Frame; // edi
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // r14
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  HANDLE v24; // rcx
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  struct _RTL_CRITICAL_SECTION *v29; // r13
  __int64 v30; // rdx
  IMFMediaBuffer *LockSemaphore; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r12
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rdx
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  IMFMediaBuffer *v67; // rcx
  __int64 v68; // rdx
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  bool v73; // [rsp+40h] [rbp-40h] BYREF
  bool v74[3]; // [rsp+41h] [rbp-3Fh] BYREF
  DWORD dwLength; // [rsp+44h] [rbp-3Ch] BYREF
  struct _RTL_CRITICAL_SECTION *v76; // [rsp+48h] [rbp-38h]
  __int64 v77; // [rsp+50h] [rbp-30h] BYREF
  IMFSample *ppIMFSample; // [rsp+58h] [rbp-28h] BYREF
  __int64 v79; // [rsp+60h] [rbp-20h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v81; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v82; // [rsp+74h] [rbp-Ch] BYREF

  v6 = this + 1;
  v76 = this;
  EnterCriticalSection(this + 1);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v74, "CMP3MediaSourcePlugin::ParseData", 1572);
  *a6 = -1;
  lpVtbl = a2->lpVtbl;
  v11 = 0;
  v73 = 0;
  v82 = 0;
  p_LockSemaphore = &this[-1].LockSemaphore;
  MP3Frame = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))lpVtbl->GetCurrentLength)(a2, &v82);
  if ( MP3Frame < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != MP3Frame )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::ParseData", 1579, MP3Frame);
    }
    if ( !g_wppLevels )
      goto LABEL_159;
    v18 = 174;
    goto LABEL_12;
  }
  if ( p_LockSemaphore[167] != a3 )
  {
    CMP3MediaSourcePlugin::FlushInternal((CMP3MediaSourcePlugin *)p_LockSemaphore);
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        175,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        p_LockSemaphore);
  }
  v76[33].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)v76[33].DebugInfo + v82);
  v19 = 0;
  MP3Frame = CMP3MediaSourcePlugin::CombineParseDataBuffer((CMP3MediaSourcePlugin *)p_LockSemaphore, a2);
  if ( MP3Frame < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
      if ( *((_DWORD *)v23 + 499) != MP3Frame )
        CallStackContext::TraceFailure(v23, "CMP3MediaSourcePlugin::ParseData", 1590, MP3Frame);
    }
    if ( !g_wppLevels )
      goto LABEL_159;
    v18 = 176;
    goto LABEL_12;
  }
  v24 = p_LockSemaphore[165];
  v81 = 0;
  v79 = 0;
  MP3Frame = (*(__int64 (__fastcall **)(HANDLE, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v24 + 24LL))(
               v24,
               &v79,
               0,
               &v81);
  if ( MP3Frame < 0 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != MP3Frame )
        CallStackContext::TraceFailure(v28, "CMP3MediaSourcePlugin::ParseData", 1594, MP3Frame);
    }
    if ( !g_wppLevels )
      goto LABEL_159;
    v18 = 177;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      p_LockSemaphore,
      MP3Frame);
    goto LABEL_159;
  }
  v29 = v76;
  while ( v19 < v81 && !v11 )
  {
    dwLength = 0;
    v74[0] = 0;
    v77 = 0;
    MP3Frame = CMP3MediaSourcePlugin::FindMP3Frame(
                 (CMP3MediaSourcePlugin *)p_LockSemaphore,
                 (const unsigned __int8 *)(v19 + v79),
                 v81 - (unsigned int)v19,
                 &v73,
                 &dwLength,
                 &v77,
                 v74);
    if ( MP3Frame < 0 )
    {
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != MP3Frame )
          CallStackContext::TraceFailure(v61, "CMP3MediaSourcePlugin::ParseData", 1603, MP3Frame);
      }
      if ( !g_wppLevels )
        goto LABEL_142;
      v62 = 178;
      goto LABEL_141;
    }
    if ( v74[0] )
    {
      LockSemaphore = (IMFMediaBuffer *)v29[32].LockSemaphore;
      ppBuffer = 0;
      MP3Frame = MFCreateMediaBufferWrapper(LockSemaphore, v19, dwLength, &ppBuffer);
      if ( MP3Frame < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
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
          if ( *((_DWORD *)v58 + 499) != MP3Frame )
            CallStackContext::TraceFailure(v58, "CMP3MediaSourcePlugin::ParseData", 1607, MP3Frame);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            179,
            &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
            p_LockSemaphore,
            MP3Frame);
        goto LABEL_119;
      }
      ppIMFSample = 0;
      MP3Frame = MFCreateSample(&ppIMFSample);
      if ( MP3Frame < 0 )
      {
        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v53 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
          if ( *((_DWORD *)v55 + 499) != MP3Frame )
            CallStackContext::TraceFailure(v55, "CMP3MediaSourcePlugin::ParseData", 1609, MP3Frame);
        }
        if ( !g_wppLevels )
          goto LABEL_108;
        v43 = 180;
LABEL_107:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v43,
          &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
          p_LockSemaphore,
          MP3Frame);
        goto LABEL_108;
      }
      MP3Frame = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                   ppIMFSample,
                   ppBuffer);
      if ( MP3Frame < 0 )
      {
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
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
          if ( *((_DWORD *)v52 + 499) != MP3Frame )
            CallStackContext::TraceFailure(v52, "CMP3MediaSourcePlugin::ParseData", 1610, MP3Frame);
        }
        if ( !g_wppLevels )
          goto LABEL_108;
        v43 = 181;
        goto LABEL_107;
      }
      v35 = v77;
      MP3Frame = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
                   ppIMFSample,
                   v77);
      if ( MP3Frame < 0 )
      {
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
          {
            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v47 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v47 + 8) )
        {
          v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
          if ( *((_DWORD *)v49 + 499) != MP3Frame )
            CallStackContext::TraceFailure(v49, "CMP3MediaSourcePlugin::ParseData", 1611, MP3Frame);
        }
        if ( !g_wppLevels )
          goto LABEL_108;
        v43 = 182;
        goto LABEL_107;
      }
      MP3Frame = ((__int64 (__fastcall *)(IMFSample *, HANDLE))ppIMFSample->lpVtbl->SetSampleTime)(
                   ppIMFSample,
                   p_LockSemaphore[166]);
      if ( MP3Frame < 0 )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
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
          if ( *((_DWORD *)v46 + 499) != MP3Frame )
            CallStackContext::TraceFailure(v46, "CMP3MediaSourcePlugin::ParseData", 1612, MP3Frame);
        }
        if ( !g_wppLevels )
          goto LABEL_108;
        v43 = 183;
        goto LABEL_107;
      }
      if ( (unsigned __int8)byte_1801B110B >= 0x20u )
        WPP_SF_qii(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          184,
          &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
          p_LockSemaphore,
          v29[32].SpinCount,
          v35);
      if ( !CVPtrList::AddTail((CVPtrList *)&v29[21].OwningThread, ppIMFSample) )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        MP3Frame = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
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
          if ( *((_DWORD *)v42 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v42, "CMP3MediaSourcePlugin::ParseData", 1616, -2147024882);
        }
        if ( g_wppLevels )
        {
          v43 = 185;
          goto LABEL_107;
        }
LABEL_108:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
LABEL_119:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
LABEL_142:
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v29[32].LockSemaphore + 32LL))(v29[32].LockSemaphore);
        goto LABEL_159;
      }
      v39 = dwLength;
      v29[32].SpinCount = (ULONG_PTR)p_LockSemaphore[166] + v35;
      v19 += v39;
      ppIMFSample = 0;
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
LABEL_54:
      v11 = v73;
    }
    else
    {
      if ( dwLength )
      {
        v19 += dwLength;
        goto LABEL_54;
      }
      v11 = v73;
      if ( !v73 )
        ++v19;
    }
  }
  MP3Frame = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)v29[32].LockSemaphore + 32LL))(v29[32].LockSemaphore);
  if ( MP3Frame < 0 )
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
      if ( *((_DWORD *)v66 + 499) != MP3Frame )
        CallStackContext::TraceFailure(v66, "CMP3MediaSourcePlugin::ParseData", 1631, MP3Frame);
    }
    if ( !g_wppLevels )
      goto LABEL_142;
    v62 = 186;
LABEL_141:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v62,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      p_LockSemaphore,
      MP3Frame);
    goto LABEL_142;
  }
  if ( v11 )
  {
    if ( v19 )
    {
      v67 = (IMFMediaBuffer *)v29[32].LockSemaphore;
      ppBuffer = 0;
      MP3Frame = MFCreateMediaBufferWrapper(v67, v19, v81 - v19, &ppBuffer);
      if ( MP3Frame >= 0 )
      {
        ComSmartPtr<IMFMediaBuffer>::operator=(&v29[32].LockSemaphore, &ppBuffer);
      }
      else
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != MP3Frame )
            CallStackContext::TraceFailure(v71, "CMP3MediaSourcePlugin::ParseData", 1638, MP3Frame);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            187,
            &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
            p_LockSemaphore,
            MP3Frame);
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
    }
  }
  else
  {
    ComSmartPtr<IMFMediaBuffer>::operator=(&v29[32].LockSemaphore, 0);
  }
LABEL_159:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v74);
  LeaveCriticalSection(v6);
  return (unsigned int)MP3Frame;
}

```

## disassembly

```asm
0x1800dd8e0  mov     [rsp-38h+arg_10], rbx
0x1800dd8e5  push    rbp
0x1800dd8e6  push    rsi
0x1800dd8e7  push    rdi
0x1800dd8e8  push    r12
0x1800dd8ea  push    r13
0x1800dd8ec  push    r14
0x1800dd8ee  push    r15
0x1800dd8f0  mov     rbp, rsp
0x1800dd8f3  sub     rsp, 80h
0x1800dd8fa  mov     rax, cs:__security_cookie
0x1800dd901  xor     rax, rsp
0x1800dd904  mov     [rbp+var_8], rax
0x1800dd908  mov     rdi, [rbp+arg_28]
0x1800dd90c  lea     rbx, [rcx+28h]
0x1800dd910  mov     rsi, rcx
0x1800dd913  mov     [rbp+var_38], rcx
0x1800dd917  mov     rcx, rbx; lpCriticalSection
0x1800dd91a  mov     r14, r8
0x1800dd91d  mov     r13, rdx
0x1800dd920  call    cs:__imp_EnterCriticalSection
0x1800dd926  mov     r8d, 624h; int
0x1800dd92c  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800dd933  lea     rcx, [rbp+var_3F]; this
0x1800dd937  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800dd93c  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800dd943  lea     rdx, [rbp+var_C]
0x1800dd947  mov     rax, [r13+0]
0x1800dd94b  xor     r12b, r12b
0x1800dd94e  mov     rcx, r13
0x1800dd951  mov     [rbp+var_40], r12b
0x1800dd955  mov     [rbp+var_C], 0
0x1800dd95c  mov     rax, [rax+28h]
0x1800dd960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd965  add     rsi, 0FFFFFFFFFFFFFFF0h
0x1800dd969  mov     edi, eax
0x1800dd96b  test    eax, eax
0x1800dd96d  jns     loc_1800DDA20
0x1800dd973  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd97a  test    rcx, rcx
0x1800dd97d  jnz     short loc_1800DD9C0
0x1800dd97f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dd985  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd98c  mov     rcx, rax
0x1800dd98f  test    rax, rax
0x1800dd992  jz      short loc_1800DD9B2
0x1800dd994  mov     rax, [rax]
0x1800dd997  mov     edx, 7F0h
0x1800dd99c  mov     rax, [rax+8]
0x1800dd9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd9a5  test    eax, eax
0x1800dd9a7  jz      short loc_1800DD9B2
0x1800dd9a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd9b0  jmp     short loc_1800DD9C0
0x1800dd9b2  lea     rcx, qword_1801B07E0; this
0x1800dd9b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd9c0  cmp     [rcx+8], r12b
0x1800dd9c4  jz      short loc_1800DD9EB
0x1800dd9c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dd9cb  cmp     [rax+7CCh], edi
0x1800dd9d1  jz      short loc_1800DD9EB
0x1800dd9d3  mov     r9d, edi; int
0x1800dd9d6  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800dd9dd  mov     r8d, 62Bh; int
0x1800dd9e3  mov     rcx, rax; this
0x1800dd9e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dd9eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dd9f2  jb      loc_1800DE3A1
0x1800dd9f8  mov     edx, 0AEh
0x1800dd9fd  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800dda04  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dda0b  mov     r9, rsi
0x1800dda0e  mov     dword ptr [rsp+80h+var_60], edi
0x1800dda12  mov     rcx, [rcx+10h]
0x1800dda16  call    WPP_SF_qD
0x1800dda1b  jmp     loc_1800DE3A1
0x1800dda20  lea     r15, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800dda27  cmp     [rsi+538h], r14
0x1800dda2e  jz      short loc_1800DDA5F
0x1800dda30  mov     rcx, rsi; this
0x1800dda33  call    ?FlushInternal@CMP3MediaSourcePlugin@@AEAAXXZ; CMP3MediaSourcePlugin::FlushInternal(void)
0x1800dda38  cmp     cs:byte_1801B110B, 10h
0x1800dda3f  jb      short loc_1800DDA5F
0x1800dda41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dda48  mov     edx, 0AFh
0x1800dda4d  mov     r9, rsi
0x1800dda50  mov     r8, r15
0x1800dda53  mov     rcx, [rcx+88h]
0x1800dda5a  call    WPP_SF_q
0x1800dda5f  mov     rcx, [rbp+var_38]
0x1800dda63  mov     rdx, r13; struct IMFMediaBuffer *
0x1800dda66  mov     eax, [rbp+var_C]
0x1800dda69  add     [rcx+528h], rax
0x1800dda70  mov     rcx, rsi; this
0x1800dda73  call    ?CombineParseDataBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@@Z; CMP3MediaSourcePlugin::CombineParseDataBuffer(IMFMediaBuffer *)
0x1800dda78  xor     r14d, r14d
0x1800dda7b  mov     edi, eax
0x1800dda7d  test    eax, eax
0x1800dda7f  jns     loc_1800DDB17
0x1800dda85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dda8c  test    rcx, rcx
0x1800dda8f  jnz     short loc_1800DDAD2
0x1800dda91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dda97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dda9e  mov     rcx, rax
0x1800ddaa1  test    rax, rax
0x1800ddaa4  jz      short loc_1800DDAC4
0x1800ddaa6  mov     rax, [rax]
0x1800ddaa9  mov     edx, 7F0h
0x1800ddaae  mov     rax, [rax+8]
0x1800ddab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddab7  test    eax, eax
0x1800ddab9  jz      short loc_1800DDAC4
0x1800ddabb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddac2  jmp     short loc_1800DDAD2
0x1800ddac4  lea     rcx, qword_1801B07E0; this
0x1800ddacb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddad2  cmp     [rcx+8], r14b
0x1800ddad6  jz      short loc_1800DDAFD
0x1800ddad8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ddadd  cmp     [rax+7CCh], edi
0x1800ddae3  jz      short loc_1800DDAFD
0x1800ddae5  mov     r9d, edi; int
0x1800ddae8  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800ddaef  mov     r8d, 636h; int
0x1800ddaf5  mov     rcx, rax; this
0x1800ddaf8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ddafd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddb04  jb      loc_1800DE3A1
0x1800ddb0a  mov     edx, 0B0h
0x1800ddb0f  mov     r8, r15
0x1800ddb12  jmp     loc_1800DDA04
0x1800ddb17  mov     rcx, [rsi+528h]
0x1800ddb1e  lea     r9, [rbp+var_10]
0x1800ddb22  mov     [rbp+var_10], r14d
0x1800ddb26  lea     rdx, [rbp+var_20]
0x1800ddb2a  mov     [rbp+var_20], r14
0x1800ddb2e  xor     r8d, r8d
0x1800ddb31  mov     rax, [rcx]
0x1800ddb34  mov     rax, [rax+18h]
0x1800ddb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb3d  mov     edi, eax
0x1800ddb3f  test    eax, eax
0x1800ddb41  jns     loc_1800DDBD6
0x1800ddb47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddb4e  test    rcx, rcx
0x1800ddb51  jnz     short loc_1800DDB94
0x1800ddb53  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ddb59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddb60  mov     rcx, rax
0x1800ddb63  test    rax, rax
0x1800ddb66  jz      short loc_1800DDB86
0x1800ddb68  mov     rax, [rax]
0x1800ddb6b  mov     edx, 7F0h
0x1800ddb70  mov     rax, [rax+8]
0x1800ddb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb79  test    eax, eax
0x1800ddb7b  jz      short loc_1800DDB86
0x1800ddb7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddb84  jmp     short loc_1800DDB94
0x1800ddb86  lea     rcx, qword_1801B07E0; this
0x1800ddb8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddb94  cmp     [rcx+8], r14b
0x1800ddb98  jz      short loc_1800DDBBF
0x1800ddb9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ddb9f  cmp     [rax+7CCh], edi
0x1800ddba5  jz      short loc_1800DDBBF
0x1800ddba7  mov     r9d, edi; int
0x1800ddbaa  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800ddbb1  mov     r8d, 63Ah; int
0x1800ddbb7  mov     rcx, rax; this
0x1800ddbba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ddbbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddbc6  jb      loc_1800DE3A1
0x1800ddbcc  mov     edx, 0B1h
0x1800ddbd1  jmp     loc_1800DDB0F
0x1800ddbd6  mov     r13, [rbp+var_38]
0x1800ddbda  mov     r8d, [rbp+var_10]
0x1800ddbde  cmp     r14, r8
0x1800ddbe1  jnb     loc_1800DE1BF
0x1800ddbe7  test    r12b, r12b
0x1800ddbea  jnz     loc_1800DE1BF
0x1800ddbf0  mov     rdx, [rbp+var_20]
0x1800ddbf4  lea     rax, [rbp+var_3F]
0x1800ddbf8  mov     [rsp+80h+var_50], rax; bool *
0x1800ddbfd  lea     r9, [rbp+var_40]; bool *
0x1800ddc01  xor     r12d, r12d
0x1800ddc04  lea     rax, [rbp+var_30]
0x1800ddc08  mov     [rsp+80h+var_58], rax; __int64 *
0x1800ddc0d  sub     r8d, r14d; unsigned int
0x1800ddc10  lea     rax, [rbp+dwLength]
0x1800ddc14  mov     [rbp+dwLength], r12d
0x1800ddc18  add     rdx, r14; unsigned __int8 *
0x1800ddc1b  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800ddc20  mov     rcx, rsi; this
0x1800ddc23  mov     [rbp+var_3F], r12b
0x1800ddc27  mov     [rbp+var_30], r12
0x1800ddc2b  call    ?FindMP3Frame@CMP3MediaSourcePlugin@@AEAAJPEBEKPEA_NPEAIPEA_J1@Z; CMP3MediaSourcePlugin::FindMP3Frame(uchar const *,ulong,bool *,uint *,__int64 *,bool *)
0x1800ddc30  mov     edi, eax
0x1800ddc32  test    eax, eax
0x1800ddc34  js      loc_1800DE130
0x1800ddc3a  cmp     [rbp+var_3F], r12b
0x1800ddc3e  jz      loc_1800DDD6B
0x1800ddc44  mov     r8d, [rbp+dwLength]; dwLength
0x1800ddc48  lea     r9, [rbp+ppBuffer]; ppBuffer
0x1800ddc4c  mov     rcx, [r13+518h]; pBuffer
0x1800ddc53  mov     edx, r14d; cbOffset
0x1800ddc56  mov     [rbp+ppBuffer], r12
0x1800ddc5a  call    cs:__imp_MFCreateMediaBufferWrapper
0x1800ddc60  mov     edi, eax
0x1800ddc62  test    eax, eax
0x1800ddc64  js      loc_1800DE082
0x1800ddc6a  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1800ddc6e  mov     [rbp+ppIMFSample], r12
0x1800ddc72  call    cs:__imp_MFCreateSample
0x1800ddc78  mov     edi, eax
0x1800ddc7a  test    eax, eax
0x1800ddc7c  js      loc_1800DDFD4
0x1800ddc82  mov     rcx, [rbp+ppIMFSample]
0x1800ddc86  mov     rdx, [rbp+ppBuffer]
0x1800ddc8a  mov     rax, [rcx]
0x1800ddc8d  mov     rax, [rax+150h]
0x1800ddc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddc99  mov     edi, eax
0x1800ddc9b  test    eax, eax
0x1800ddc9d  js      loc_1800DDF45
0x1800ddca3  mov     rcx, [rbp+ppIMFSample]
0x1800ddca7  mov     r12, [rbp+var_30]
0x1800ddcab  mov     rdx, r12
0x1800ddcae  mov     rax, [rcx]
0x1800ddcb1  mov     rax, [rax+130h]
0x1800ddcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddcbd  mov     edi, eax
0x1800ddcbf  test    eax, eax
0x1800ddcc1  js      loc_1800DDEB6
0x1800ddcc7  mov     rcx, [rbp+ppIMFSample]
0x1800ddccb  mov     rdx, [rsi+530h]
0x1800ddcd2  mov     rax, [rcx]
0x1800ddcd5  mov     rax, [rax+120h]
0x1800ddcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddce1  mov     edi, eax
0x1800ddce3  test    eax, eax
0x1800ddce5  js      loc_1800DDE27
0x1800ddceb  cmp     cs:byte_1801B110B, 20h ; ' '
0x1800ddcf2  jb      short loc_1800DDD23
0x1800ddcf4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddcfb  mov     edx, 0B8h
0x1800ddd00  mov     rax, [r13+520h]
0x1800ddd07  mov     r9, rsi
0x1800ddd0a  mov     [rsp+80h+var_58], r12
0x1800ddd0f  mov     r8, r15
0x1800ddd12  mov     [rsp+80h+var_60], rax
0x1800ddd17  mov     rcx, [rcx+88h]
0x1800ddd1e  call    WPP_SF_qii
0x1800ddd23  mov     rdx, [rbp+ppIMFSample]; void *
0x1800ddd27  lea     rcx, [r13+358h]; this
0x1800ddd2e  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x1800ddd33  test    rax, rax
0x1800ddd36  jz      short loc_1800DDD93
0x1800ddd38  mov     rcx, [rsi+530h]
0x1800ddd3f  mov     eax, [rbp+dwLength]
0x1800ddd42  add     rcx, r12
0x1800ddd45  mov     [r13+520h], rcx
0x1800ddd4c  add     r14, rax
0x1800ddd4f  lea     rcx, [rbp+ppIMFSample]; void *
0x1800ddd53  mov     [rbp+ppIMFSample], 0
0x1800ddd5b  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ddd60  lea     rcx, [rbp+ppBuffer]; void *
0x1800ddd64  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ddd69  jmp     short loc_1800DDD75
0x1800ddd6b  mov     eax, [rbp+dwLength]
0x1800ddd6e  test    eax, eax
0x1800ddd70  jz      short loc_1800DDD7E
0x1800ddd72  add     r14, rax
0x1800ddd75  mov     r12b, [rbp+var_40]
0x1800ddd79  jmp     loc_1800DDBDA
0x1800ddd7e  mov     r12b, [rbp+var_40]
0x1800ddd82  test    r12b, r12b
0x1800ddd85  jnz     loc_1800DDBDA
0x1800ddd8b  inc     r14
0x1800ddd8e  jmp     loc_1800DDBDA
0x1800ddd93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ddd9a  mov     edi, 8007000Eh
0x1800ddd9f  test    rcx, rcx
0x1800ddda2  jnz     short loc_1800DDDE5
0x1800ddda4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dddaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dddb1  mov     rcx, rax
0x1800dddb4  test    rax, rax
0x1800dddb7  jz      short loc_1800DDDD7
0x1800dddb9  mov     rax, [rax]
0x1800dddbc  mov     edx, 7F0h
0x1800dddc1  mov     rax, [rax+8]
0x1800dddc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dddca  test    eax, eax
0x1800dddcc  jz      short loc_1800DDDD7
0x1800dddce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dddd5  jmp     short loc_1800DDDE5
0x1800dddd7  lea     rcx, qword_1801B07E0; this
0x1800dddde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
