# CMP3MediaSourcePlugin::ParseData(IMFMediaBuffer *,unsigned __int64,ulong,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *,unsigned __int64 *)

- ea: `0x1800e3ea0`
- end: `0x1800e4a03`
- name: `?ParseData@CMP3MediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@_KKPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@PEA_K@Z`
- size: `2915`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct IMFMediaBuffer *, HANDLE, __int64, struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180036cec`
- `0x18003b238`
- `0x180058af4`
- `0x1800612cc`
- `0x180079680`
- `0x1800ba240`
- `0x1800e3ea0`
- `0x1800fb8c4`
- `0x180110ed0`
- `0x180121750`
- `0x180139588`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e49cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e49cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3ee0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3ee0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3f45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e405d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4125`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4388`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e441d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e44b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4547`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e45dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4690`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4744`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e47f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e48fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3f45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e405d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4125`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4388`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e441d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e44b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4547`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e45dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4690`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e4744`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e47f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e48fc`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800e4232`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800e48da`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800e4232`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800e48da`
- `MFPlat!MFCreateSample` at `0x1800e4250`
- `MFPlat!MFCreateSample` at `0x1800e4250`

## string_xrefs

- `0x1800e3ef2`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e3fa2`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e40ba`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e4182`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e43e5`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e447a`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e450f`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e45a4`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e4639`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e46ed`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e47a1`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e4853`: `CMP3MediaSourcePlugin::ParseData`
- `0x1800e4959`: `CMP3MediaSourcePlugin::ParseData`

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
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v26 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v59 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v56 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v53 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v50 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v47 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v44 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
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
            v40 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v64 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v69 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800e3ea0  mov     [rsp-38h+arg_10], rbx
0x1800e3ea5  push    rbp
0x1800e3ea6  push    rsi
0x1800e3ea7  push    rdi
0x1800e3ea8  push    r12
0x1800e3eaa  push    r13
0x1800e3eac  push    r14
0x1800e3eae  push    r15
0x1800e3eb0  mov     rbp, rsp
0x1800e3eb3  sub     rsp, 80h
0x1800e3eba  mov     rax, cs:__security_cookie
0x1800e3ec1  xor     rax, rsp
0x1800e3ec4  mov     [rbp+var_8], rax
0x1800e3ec8  mov     rdi, [rbp+arg_28]
0x1800e3ecc  lea     rbx, [rcx+28h]
0x1800e3ed0  mov     rsi, rcx
0x1800e3ed3  mov     [rbp+var_38], rcx
0x1800e3ed7  mov     rcx, rbx; lpCriticalSection
0x1800e3eda  mov     r14, r8
0x1800e3edd  mov     r13, rdx
0x1800e3ee0  call    cs:__imp_EnterCriticalSection
0x1800e3ee7  nop     dword ptr [rax+rax+00h]
0x1800e3eec  mov     r8d, 624h; int
0x1800e3ef2  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800e3ef9  lea     rcx, [rbp+var_3F]; this
0x1800e3efd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e3f02  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800e3f09  lea     rdx, [rbp+var_C]
0x1800e3f0d  mov     rax, [r13+0]
0x1800e3f11  xor     r12b, r12b
0x1800e3f14  mov     rcx, r13
0x1800e3f17  mov     [rbp+var_40], r12b
0x1800e3f1b  mov     [rbp+var_C], 0
0x1800e3f22  mov     rax, [rax+28h]
0x1800e3f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3f2b  add     rsi, 0FFFFFFFFFFFFFFF0h
0x1800e3f2f  mov     edi, eax
0x1800e3f31  test    eax, eax
0x1800e3f33  jns     loc_1800E3FEC
0x1800e3f39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3f40  test    rcx, rcx
0x1800e3f43  jnz     short loc_1800E3F8C
0x1800e3f45  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e3f4c  nop     dword ptr [rax+rax+00h]
0x1800e3f51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3f58  mov     rcx, rax
0x1800e3f5b  test    rax, rax
0x1800e3f5e  jz      short loc_1800E3F7E
0x1800e3f60  mov     rax, [rax]
0x1800e3f63  mov     edx, 7F0h
0x1800e3f68  mov     rax, [rax+8]
0x1800e3f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3f71  test    eax, eax
0x1800e3f73  jz      short loc_1800E3F7E
0x1800e3f75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3f7c  jmp     short loc_1800E3F8C
0x1800e3f7e  lea     rcx, qword_1801B97E0; this
0x1800e3f85  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3f8c  cmp     [rcx+8], r12b
0x1800e3f90  jz      short loc_1800E3FB7
0x1800e3f92  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e3f97  cmp     [rax+7CCh], edi
0x1800e3f9d  jz      short loc_1800E3FB7
0x1800e3f9f  mov     r9d, edi; int
0x1800e3fa2  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800e3fa9  mov     r8d, 62Bh; int
0x1800e3faf  mov     rcx, rax; this
0x1800e3fb2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e3fb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e3fbe  jb      loc_1800E49C1
0x1800e3fc4  mov     edx, 0AEh
0x1800e3fc9  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800e3fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3fd7  mov     r9, rsi
0x1800e3fda  mov     dword ptr [rsp+80h+var_60], edi
0x1800e3fde  mov     rcx, [rcx+10h]
0x1800e3fe2  call    WPP_SF_qD
0x1800e3fe7  jmp     loc_1800E49C1
0x1800e3fec  lea     r15, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800e3ff3  cmp     [rsi+538h], r14
0x1800e3ffa  jz      short loc_1800E402B
0x1800e3ffc  mov     rcx, rsi; this
0x1800e3fff  call    ?FlushInternal@CMP3MediaSourcePlugin@@AEAAXXZ; CMP3MediaSourcePlugin::FlushInternal(void)
0x1800e4004  cmp     cs:byte_1801BA10B, 10h
0x1800e400b  jb      short loc_1800E402B
0x1800e400d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4014  mov     edx, 0AFh
0x1800e4019  mov     r9, rsi
0x1800e401c  mov     r8, r15
0x1800e401f  mov     rcx, [rcx+88h]
0x1800e4026  call    WPP_SF_q
0x1800e402b  mov     rcx, [rbp+var_38]
0x1800e402f  mov     rdx, r13; struct IMFMediaBuffer *
0x1800e4032  mov     eax, [rbp+var_C]
0x1800e4035  add     [rcx+528h], rax
0x1800e403c  mov     rcx, rsi; this
0x1800e403f  call    ?CombineParseDataBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@@Z; CMP3MediaSourcePlugin::CombineParseDataBuffer(IMFMediaBuffer *)
0x1800e4044  xor     r14d, r14d
0x1800e4047  mov     edi, eax
0x1800e4049  test    eax, eax
0x1800e404b  jns     loc_1800E40E9
0x1800e4051  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e4058  test    rcx, rcx
0x1800e405b  jnz     short loc_1800E40A4
0x1800e405d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e4064  nop     dword ptr [rax+rax+00h]
0x1800e4069  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e4070  mov     rcx, rax
0x1800e4073  test    rax, rax
0x1800e4076  jz      short loc_1800E4096
0x1800e4078  mov     rax, [rax]
0x1800e407b  mov     edx, 7F0h
0x1800e4080  mov     rax, [rax+8]
0x1800e4084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4089  test    eax, eax
0x1800e408b  jz      short loc_1800E4096
0x1800e408d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e4094  jmp     short loc_1800E40A4
0x1800e4096  lea     rcx, qword_1801B97E0; this
0x1800e409d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e40a4  cmp     [rcx+8], r14b
0x1800e40a8  jz      short loc_1800E40CF
0x1800e40aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e40af  cmp     [rax+7CCh], edi
0x1800e40b5  jz      short loc_1800E40CF
0x1800e40b7  mov     r9d, edi; int
0x1800e40ba  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800e40c1  mov     r8d, 636h; int
0x1800e40c7  mov     rcx, rax; this
0x1800e40ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e40cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e40d6  jb      loc_1800E49C1
0x1800e40dc  mov     edx, 0B0h
0x1800e40e1  mov     r8, r15
0x1800e40e4  jmp     loc_1800E3FD0
0x1800e40e9  mov     rcx, [rsi+528h]
0x1800e40f0  lea     r9, [rbp+var_10]
0x1800e40f4  mov     [rbp+var_10], r14d
0x1800e40f8  lea     rdx, [rbp+var_20]
0x1800e40fc  mov     [rbp+var_20], r14
0x1800e4100  xor     r8d, r8d
0x1800e4103  mov     rax, [rcx]
0x1800e4106  mov     rax, [rax+18h]
0x1800e410a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e410f  mov     edi, eax
0x1800e4111  test    eax, eax
0x1800e4113  jns     loc_1800E41AE
0x1800e4119  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e4120  test    rcx, rcx
0x1800e4123  jnz     short loc_1800E416C
0x1800e4125  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e412c  nop     dword ptr [rax+rax+00h]
0x1800e4131  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e4138  mov     rcx, rax
0x1800e413b  test    rax, rax
0x1800e413e  jz      short loc_1800E415E
0x1800e4140  mov     rax, [rax]
0x1800e4143  mov     edx, 7F0h
0x1800e4148  mov     rax, [rax+8]
0x1800e414c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4151  test    eax, eax
0x1800e4153  jz      short loc_1800E415E
0x1800e4155  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e415c  jmp     short loc_1800E416C
0x1800e415e  lea     rcx, qword_1801B97E0; this
0x1800e4165  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e416c  cmp     [rcx+8], r14b
0x1800e4170  jz      short loc_1800E4197
0x1800e4172  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e4177  cmp     [rax+7CCh], edi
0x1800e417d  jz      short loc_1800E4197
0x1800e417f  mov     r9d, edi; int
0x1800e4182  lea     rdx, aCmp3mediasourc_37; "CMP3MediaSourcePlugin::ParseData"
0x1800e4189  mov     r8d, 63Ah; int
0x1800e418f  mov     rcx, rax; this
0x1800e4192  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e4197  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e419e  jb      loc_1800E49C1
0x1800e41a4  mov     edx, 0B1h
0x1800e41a9  jmp     loc_1800E40E1
0x1800e41ae  mov     r13, [rbp+var_38]
0x1800e41b2  mov     r8d, [rbp+var_10]
0x1800e41b6  cmp     r14, r8
0x1800e41b9  jnb     loc_1800E47CD
0x1800e41bf  test    r12b, r12b
0x1800e41c2  jnz     loc_1800E47CD
0x1800e41c8  mov     rdx, [rbp+var_20]
0x1800e41cc  lea     rax, [rbp+var_3F]
0x1800e41d0  mov     [rsp+80h+var_50], rax; bool *
0x1800e41d5  lea     r9, [rbp+var_40]; bool *
0x1800e41d9  xor     r12d, r12d
0x1800e41dc  lea     rax, [rbp+var_30]
0x1800e41e0  mov     [rsp+80h+var_58], rax; __int64 *
0x1800e41e5  sub     r8d, r14d; unsigned int
0x1800e41e8  lea     rax, [rbp+dwLength]
0x1800e41ec  mov     [rbp+dwLength], r12d
0x1800e41f0  add     rdx, r14; unsigned __int8 *
0x1800e41f3  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800e41f8  mov     rcx, rsi; this
0x1800e41fb  mov     [rbp+var_3F], r12b
0x1800e41ff  mov     [rbp+var_30], r12
0x1800e4203  call    ?FindMP3Frame@CMP3MediaSourcePlugin@@AEAAJPEBEKPEA_NPEAIPEA_J1@Z; CMP3MediaSourcePlugin::FindMP3Frame(uchar const *,ulong,bool *,uint *,__int64 *,bool *)
0x1800e4208  mov     edi, eax
0x1800e420a  test    eax, eax
0x1800e420c  js      loc_1800E4738
0x1800e4212  cmp     [rbp+var_3F], r12b
0x1800e4216  jz      loc_1800E434F
0x1800e421c  mov     r8d, [rbp+dwLength]; dwLength
0x1800e4220  lea     r9, [rbp+ppBuffer]; ppBuffer
0x1800e4224  mov     rcx, [r13+518h]; pBuffer
0x1800e422b  mov     edx, r14d; cbOffset
0x1800e422e  mov     [rbp+ppBuffer], r12
0x1800e4232  call    cs:__imp_MFCreateMediaBufferWrapper
0x1800e4239  nop     dword ptr [rax+rax+00h]
0x1800e423e  mov     edi, eax
0x1800e4240  test    eax, eax
0x1800e4242  js      loc_1800E4684
0x1800e4248  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1800e424c  mov     [rbp+ppIMFSample], r12
0x1800e4250  call    cs:__imp_MFCreateSample
0x1800e4257  nop     dword ptr [rax+rax+00h]
0x1800e425c  mov     edi, eax
0x1800e425e  test    eax, eax
0x1800e4260  js      loc_1800E45D0
0x1800e4266  mov     rcx, [rbp+ppIMFSample]
0x1800e426a  mov     rdx, [rbp+ppBuffer]
0x1800e426e  mov     rax, [rcx]
0x1800e4271  mov     rax, [rax+150h]
0x1800e4278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e427d  mov     edi, eax
0x1800e427f  test    eax, eax
0x1800e4281  js      loc_1800E453B
0x1800e4287  mov     rcx, [rbp+ppIMFSample]
0x1800e428b  mov     r12, [rbp+var_30]
0x1800e428f  mov     rdx, r12
0x1800e4292  mov     rax, [rcx]
0x1800e4295  mov     rax, [rax+130h]
0x1800e429c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e42a1  mov     edi, eax
0x1800e42a3  test    eax, eax
0x1800e42a5  js      loc_1800E44A6
0x1800e42ab  mov     rcx, [rbp+ppIMFSample]
0x1800e42af  mov     rdx, [rsi+530h]
0x1800e42b6  mov     rax, [rcx]
0x1800e42b9  mov     rax, [rax+120h]
0x1800e42c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e42c5  mov     edi, eax
0x1800e42c7  test    eax, eax
0x1800e42c9  js      loc_1800E4411
0x1800e42cf  cmp     cs:byte_1801BA10B, 20h ; ' '
0x1800e42d6  jb      short loc_1800E4307
0x1800e42d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e42df  mov     edx, 0B8h
0x1800e42e4  mov     rax, [r13+520h]
0x1800e42eb  mov     r9, rsi
0x1800e42ee  mov     [rsp+80h+var_58], r12
0x1800e42f3  mov     r8, r15
0x1800e42f6  mov     [rsp+80h+var_60], rax
0x1800e42fb  mov     rcx, [rcx+88h]
0x1800e4302  call    WPP_SF_qii
0x1800e4307  mov     rdx, [rbp+ppIMFSample]; void *
0x1800e430b  lea     rcx, [r13+358h]; this
0x1800e4312  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x1800e4317  test    rax, rax
0x1800e431a  jz      short loc_1800E4377
0x1800e431c  mov     rcx, [rsi+530h]
0x1800e4323  mov     eax, [rbp+dwLength]
0x1800e4326  add     rcx, r12
0x1800e4329  mov     [r13+520h], rcx
0x1800e4330  add     r14, rax
0x1800e4333  lea     rcx, [rbp+ppIMFSample]; void *
0x1800e4337  mov     [rbp+ppIMFSample], 0
0x1800e433f  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e4344  lea     rcx, [rbp+ppBuffer]; void *
0x1800e4348  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e434d  jmp     short loc_1800E4359
0x1800e434f  mov     eax, [rbp+dwLength]
0x1800e4352  test    eax, eax
0x1800e4354  jz      short loc_1800E4362
0x1800e4356  add     r14, rax
0x1800e4359  mov     r12b, [rbp+var_40]
0x1800e435d  jmp     loc_1800E41B2
0x1800e4362  mov     r12b, [rbp+var_40]
0x1800e4366  test    r12b, r12b
0x1800e4369  jnz     loc_1800E41B2
0x1800e436f  inc     r14
0x1800e4372  jmp     loc_1800E41B2
0x1800e4377  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e437e  mov     edi, 8007000Eh
0x1800e4383  test    rcx, rcx
0x1800e4386  jnz     short loc_1800E43CF
0x1800e4388  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e438f  nop     dword ptr [rax+rax+00h]
0x1800e4394  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e439b  mov     rcx, rax
0x1800e439e  test    rax, rax
0x1800e43a1  jz      short loc_1800E43C1
0x1800e43a3  mov     rax, [rax]
0x1800e43a6  mov     edx, 7F0h
0x1800e43ab  mov     rax, [rax+8]
  ... truncated ...
```
