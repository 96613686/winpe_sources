# CAVIStreamSink::ProcessSample(IMFSample *)

- ea: `0x1800eb490`
- end: `0x1800ebfd2`
- name: `?ProcessSample@CAVIStreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `2882`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180043c9c`
- `0x1800734a8`
- `0x180073b14`
- `0x1800c5d34`
- `0x1800eb490`
- `0x1801095a8`
- `0x18011e37c`
- `0x180125f30`
- `0x180128414`
- `0x180128690`
- `0x18012b0dc`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb5b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb5d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebe4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb5b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb5d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebe4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb4f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb5e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb4f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb5e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb520`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb600`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb6a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb74b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb825`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb907`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb9b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eba80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebb43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebbf8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebca1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebd41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebe75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebec4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb520`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb600`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb6a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb74b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb825`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb907`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eb9b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eba80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebb43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebbf8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebca1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebd41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebe75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ebec4`

## string_xrefs

- `0x1800eb4a7`: `CAVIStreamSink::ProcessSample`
- `0x1800eb87c`: `CAVIStreamSink::ProcessSample`
- `0x1800eb95e`: `CAVIStreamSink::ProcessSample`
- `0x1800eba0a`: `CAVIStreamSink::ProcessSample`
- `0x1800eba36`: `CAVIStreamSink::ProcessSample`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::ProcessSample(CAVIStreamSink *this, struct IMFSample *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int SamplesPerSecond; // ebx
  __int64 v6; // rdx
  char *v7; // r14
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // r12
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  signed int v29; // r12d
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  CAVIStreamSink::StreamSampleQueueEntry *v58; // rax
  __int64 v59; // rdx
  _QWORD *v60; // rax
  _QWORD *v61; // rcx
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct IMFMediaBuffer *v70; // [rsp+30h] [rbp-28h] BYREF
  __int64 v71; // [rsp+38h] [rbp-20h] BYREF
  double v72[3]; // [rsp+40h] [rbp-18h] BYREF
  CAVIMediaSink *v73; // [rsp+A0h] [rbp+48h] BYREF
  int v74; // [rsp+A8h] [rbp+50h] BYREF
  unsigned int v75; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v76; // [rsp+B8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v73, "CAVIStreamSink::ProcessSample", 103);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 560);
  v74 = 0;
  SamplesPerSecond = a2 == 0 ? 0x80004003 : 0;
  v76 = 0;
  v71 = 0;
  v75 = 0;
  v70 = 0;
  v73 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 14);
  v7 = (char *)this - 16;
  if ( !*((_QWORD *)this + 45) )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -1072870856;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072870856 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::ProcessSample", 114, -1072870856);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v11 = 23;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
      (char *)this - 16,
      SamplesPerSecond);
LABEL_13:
    LeaveCriticalSection(v4);
    goto LABEL_169;
  }
  Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(&v73, (char *)this + 360);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 14);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 520);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 13);
  if ( !a2 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v15, "CAVIStreamSink::ProcessSample", 121, SamplesPerSecond);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v11 = 24;
    goto LABEL_12;
  }
  SamplesPerSecond = CBaseStreamSink::ProcessSample(this, a2);
  if ( SamplesPerSecond < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v19, "CAVIStreamSink::ProcessSample", 124, SamplesPerSecond);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v11 = 25;
    goto LABEL_12;
  }
  SamplesPerSecond = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleTime)(a2, &v76);
  if ( SamplesPerSecond < 0 )
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
      if ( *((_DWORD *)v23 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v23, "CAVIStreamSink::ProcessSample", 127, SamplesPerSecond);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v11 = 26;
    goto LABEL_12;
  }
  if ( *((_DWORD *)v7 + 118) )
  {
    if ( *((_BYTE *)this + 481) )
    {
      v24 = v76 - *((_QWORD *)this + 59);
      v72[0] = 0.0;
      SamplesPerSecond = CAVIStreamSink::GetSamplesPerSecond((CAVIStreamSink *)((char *)this - 16), v72);
      if ( SamplesPerSecond < 0 )
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
          if ( *((_DWORD *)v28 + 499) != SamplesPerSecond )
            CallStackContext::TraceFailure(v28, "CAVIStreamSink::ProcessSample", 136, SamplesPerSecond);
        }
        if ( !g_wppLevels )
          goto LABEL_13;
        v11 = 27;
        goto LABEL_12;
      }
      v29 = (int)((double)(int)v24 * v72[0] / 10000000.0 + 0.9);
      if ( v29 > 0 )
      {
        SamplesPerSecond = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 46) + 32LL))(
                             *((_QWORD *)this + 46),
                             0,
                             0x80000000LL,
                             (unsigned int)v29);
        if ( SamplesPerSecond < 0 )
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != SamplesPerSecond )
              CallStackContext::TraceFailure(v33, "CAVIStreamSink::ProcessSample", 140, SamplesPerSecond);
          }
          if ( !g_wppLevels )
            goto LABEL_13;
          v11 = 28;
          goto LABEL_12;
        }
        SamplesPerSecond = CAVIMediaSink::WriteDroppedFramesToStdIndex(v73, (char *)this + 492, v29);
        if ( SamplesPerSecond < 0 )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != SamplesPerSecond )
              CallStackContext::TraceFailure(v37, "CAVIStreamSink::ProcessSample", 141, SamplesPerSecond);
          }
          if ( !g_wppLevels )
            goto LABEL_13;
          v11 = 29;
          goto LABEL_12;
        }
      }
      *((_BYTE *)this + 481) = 0;
      if ( *((_BYTE *)this + 480) )
        *((_BYTE *)this + 480) = 0;
    }
  }
  else
  {
    *((_QWORD *)this + 58) = v76;
  }
  SamplesPerSecond = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleDuration)(a2, &v71);
  if ( SamplesPerSecond < 0 )
  {
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v41 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v41, "CAVIStreamSink::ProcessSample", 150, SamplesPerSecond);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v11 = 30;
    goto LABEL_12;
  }
  v42 = v71 + *((_QWORD *)v7 + 61);
  ++*((_DWORD *)this + 114);
  *((_QWORD *)this + 59) = v42;
  SamplesPerSecond = ((__int64 (__fastcall *)(struct IMFSample *, int *))a2->lpVtbl->GetBufferCount)(a2, &v74);
  if ( SamplesPerSecond < 0 )
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
      if ( *((_DWORD *)v46 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v46, "CAVIStreamSink::ProcessSample", 154, SamplesPerSecond);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v11 = 31;
    goto LABEL_12;
  }
  if ( v74 )
  {
    SamplesPerSecond = ((__int64 (__fastcall *)(struct IMFSample *, struct IMFMediaBuffer **))a2->lpVtbl->ConvertToContiguousBuffer)(
                         a2,
                         &v70);
    if ( SamplesPerSecond < 0 )
    {
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v48 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v48 + 8) )
      {
        v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
        if ( *((_DWORD *)v50 + 499) != SamplesPerSecond )
          CallStackContext::TraceFailure(v50, "CAVIStreamSink::ProcessSample", 158, SamplesPerSecond);
      }
      if ( !g_wppLevels )
        goto LABEL_13;
      v11 = 32;
      goto LABEL_12;
    }
    SamplesPerSecond = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))v70->lpVtbl->GetCurrentLength)(
                         v70,
                         &v75);
    if ( SamplesPerSecond < 0 )
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
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
        if ( *((_DWORD *)v54 + 499) != SamplesPerSecond )
          CallStackContext::TraceFailure(v54, "CAVIStreamSink::ProcessSample", 159, SamplesPerSecond);
      }
      if ( !g_wppLevels )
        goto LABEL_13;
      v11 = 33;
      goto LABEL_12;
    }
    if ( *((_DWORD *)v7 + 125) > v75 )
    {
      v55 = (wchar_t *)CallStackTracing::s_wpInstance;
      SamplesPerSecond = -1072875855;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
        {
          v55 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v55 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
        if ( *((_DWORD *)v57 + 499) != -1072875855 )
          CallStackContext::TraceFailure(v57, "CAVIStreamSink::ProcessSample", 163, -1072875855);
      }
      if ( !g_wppLevels )
        goto LABEL_13;
      v11 = 34;
      goto LABEL_12;
    }
    if ( *((_DWORD *)this + 113) < v75 )
      *((_DWORD *)this + 113) = v75;
    v58 = (CAVIStreamSink::StreamSampleQueueEntry *)operator new(0x70u);
    if ( !v58
      || (v60 = (_QWORD *)CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(v58, v70, v76, v71)) == 0 )
    {
      v65 = (wchar_t *)CallStackTracing::s_wpInstance;
      SamplesPerSecond = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
        CallStackTracing::s_wpInstance = v66;
        if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
        {
          v65 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v65 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v65 + 8) )
      {
        v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
        if ( *((_DWORD *)v67 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v67, "CAVIStreamSink::ProcessSample", 172, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_13;
      v11 = 35;
      goto LABEL_12;
    }
    v61 = (_QWORD *)*((_QWORD *)this + 64);
    *v60 = (char *)this + 504;
    v60[1] = v61;
    *v61 = v60;
    ++*((_DWORD *)this + 124);
    *((_QWORD *)this + 64) = v60;
    if ( (unsigned __int8)byte_1801B110A >= 8u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        36,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        *((unsigned int *)this + 124));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 13);
  SamplesPerSecond = CAVIMediaSink::NotifySampleReceived(v73);
  if ( SamplesPerSecond < 0 )
  {
    v63 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
      CallStackTracing::s_wpInstance = v64;
      if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
      {
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v63 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v63 + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
      if ( *((_DWORD *)v68 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v68, "CAVIStreamSink::ProcessSample", 178, SamplesPerSecond);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        (char *)this - 16,
        SamplesPerSecond);
  }
LABEL_169:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v70);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v73);
  return (unsigned int)SamplesPerSecond;
}

```

## disassembly

```asm
0x1800eb490  push    rbp
0x1800eb492  push    rbx
0x1800eb493  push    rsi
0x1800eb494  push    rdi
0x1800eb495  push    r12
0x1800eb497  push    r13
0x1800eb499  push    r14
0x1800eb49b  push    r15
0x1800eb49d  mov     rbp, rsp
0x1800eb4a0  sub     rsp, 58h
0x1800eb4a4  mov     r15, rdx
0x1800eb4a7  lea     r12, aCavistreamsink_3; "CAVIStreamSink::ProcessSample"
0x1800eb4ae  mov     rdi, rcx
0x1800eb4b1  mov     rdx, r12; char *
0x1800eb4b4  mov     r8d, 67h ; 'g'; int
0x1800eb4ba  lea     rcx, [rbp+arg_0]; this
0x1800eb4be  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800eb4c3  mov     rax, r15
0x1800eb4c6  lea     rsi, [rdi+230h]
0x1800eb4cd  neg     rax
0x1800eb4d0  mov     rcx, rsi; lpCriticalSection
0x1800eb4d3  sbb     ebx, ebx
0x1800eb4d5  xor     r13d, r13d
0x1800eb4d8  not     ebx
0x1800eb4da  mov     [rbp+arg_8], r13d
0x1800eb4de  and     ebx, 80004003h
0x1800eb4e4  mov     [rbp+arg_18], r13
0x1800eb4e8  mov     [rbp+var_20], r13
0x1800eb4ec  mov     [rbp+arg_10], r13d
0x1800eb4f0  mov     [rbp+var_28], r13
0x1800eb4f4  mov     [rbp+arg_0], r13
0x1800eb4f8  call    cs:__imp_EnterCriticalSection
0x1800eb4fe  lea     r14, [rdi-10h]
0x1800eb502  cmp     [r14+178h], r13
0x1800eb509  jnz     loc_1800EB5C2
0x1800eb50f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb516  mov     ebx, 0C00D4A38h
0x1800eb51b  test    rcx, rcx
0x1800eb51e  jnz     short loc_1800EB561
0x1800eb520  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eb526  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb52d  mov     rcx, rax
0x1800eb530  test    rax, rax
0x1800eb533  jz      short loc_1800EB553
0x1800eb535  mov     rax, [rax]
0x1800eb538  mov     edx, 7F0h
0x1800eb53d  mov     rax, [rax+8]
0x1800eb541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb546  test    eax, eax
0x1800eb548  jz      short loc_1800EB553
0x1800eb54a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb551  jmp     short loc_1800EB561
0x1800eb553  lea     rcx, qword_1801B07E0; this
0x1800eb55a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb561  cmp     [rcx+8], r13b
0x1800eb565  jz      short loc_1800EB588
0x1800eb567  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eb56c  cmp     [rax+7CCh], ebx
0x1800eb572  jz      short loc_1800EB588
0x1800eb574  mov     r9d, ebx; int
0x1800eb577  mov     r8d, 72h ; 'r'; int
0x1800eb57d  mov     rdx, r12; char *
0x1800eb580  mov     rcx, rax; this
0x1800eb583  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eb588  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eb58f  jb      short loc_1800EB5B4
0x1800eb591  mov     edx, 17h
0x1800eb596  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb59d  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800eb5a4  mov     r9, r14
0x1800eb5a7  mov     [rsp+58h+var_38], ebx
0x1800eb5ab  mov     rcx, [rcx+10h]
0x1800eb5af  call    WPP_SF_qD
0x1800eb5b4  mov     rcx, rsi; lpCriticalSection
0x1800eb5b7  call    cs:__imp_LeaveCriticalSection
0x1800eb5bd  jmp     loc_1800EBFA4
0x1800eb5c2  lea     rdx, [rdi+168h]
0x1800eb5c9  lea     rcx, [rbp+arg_0]
0x1800eb5cd  call    ??4?$ComPtr@VCAVIMediaSink@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(Microsoft::WRL::ComPtr<CAVIMediaSink> const &)
0x1800eb5d2  mov     rcx, rsi; lpCriticalSection
0x1800eb5d5  call    cs:__imp_LeaveCriticalSection
0x1800eb5db  lea     rsi, [rdi+208h]
0x1800eb5e2  mov     rcx, rsi; lpCriticalSection
0x1800eb5e5  call    cs:__imp_EnterCriticalSection
0x1800eb5eb  test    r15, r15
0x1800eb5ee  jnz     loc_1800EB67F
0x1800eb5f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb5fb  test    rcx, rcx
0x1800eb5fe  jnz     short loc_1800EB641
0x1800eb600  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eb606  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb60d  mov     rcx, rax
0x1800eb610  test    rax, rax
0x1800eb613  jz      short loc_1800EB633
0x1800eb615  mov     rax, [rax]
0x1800eb618  mov     edx, 7F0h
0x1800eb61d  mov     rax, [rax+8]
0x1800eb621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb626  test    eax, eax
0x1800eb628  jz      short loc_1800EB633
0x1800eb62a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb631  jmp     short loc_1800EB641
0x1800eb633  lea     rcx, qword_1801B07E0; this
0x1800eb63a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb641  cmp     [rcx+8], r13b
0x1800eb645  jz      short loc_1800EB668
0x1800eb647  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eb64c  cmp     [rax+7CCh], ebx
0x1800eb652  jz      short loc_1800EB668
0x1800eb654  mov     r9d, ebx; int
0x1800eb657  mov     r8d, 79h ; 'y'; int
0x1800eb65d  mov     rdx, r12; char *
0x1800eb660  mov     rcx, rax; this
0x1800eb663  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eb668  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eb66f  jb      loc_1800EB5B4
0x1800eb675  mov     edx, 18h
0x1800eb67a  jmp     loc_1800EB596
0x1800eb67f  mov     rdx, r15; struct IMFSample *
0x1800eb682  mov     rcx, rdi; this
0x1800eb685  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x1800eb68a  mov     ebx, eax
0x1800eb68c  test    eax, eax
0x1800eb68e  jns     loc_1800EB71F
0x1800eb694  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb69b  test    rcx, rcx
0x1800eb69e  jnz     short loc_1800EB6E1
0x1800eb6a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eb6a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb6ad  mov     rcx, rax
0x1800eb6b0  test    rax, rax
0x1800eb6b3  jz      short loc_1800EB6D3
0x1800eb6b5  mov     rax, [rax]
0x1800eb6b8  mov     edx, 7F0h
0x1800eb6bd  mov     rax, [rax+8]
0x1800eb6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6c6  test    eax, eax
0x1800eb6c8  jz      short loc_1800EB6D3
0x1800eb6ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb6d1  jmp     short loc_1800EB6E1
0x1800eb6d3  lea     rcx, qword_1801B07E0; this
0x1800eb6da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb6e1  cmp     [rcx+8], r13b
0x1800eb6e5  jz      short loc_1800EB708
0x1800eb6e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eb6ec  cmp     [rax+7CCh], ebx
0x1800eb6f2  jz      short loc_1800EB708
0x1800eb6f4  mov     r9d, ebx; int
0x1800eb6f7  mov     r8d, 7Ch ; '|'; int
0x1800eb6fd  mov     rdx, r12; char *
0x1800eb700  mov     rcx, rax; this
0x1800eb703  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eb708  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eb70f  jb      loc_1800EB5B4
0x1800eb715  mov     edx, 19h
0x1800eb71a  jmp     loc_1800EB596
0x1800eb71f  mov     rax, [r15]
0x1800eb722  lea     rdx, [rbp+arg_18]
0x1800eb726  mov     rcx, r15
0x1800eb729  mov     rax, [rax+118h]
0x1800eb730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb735  mov     ebx, eax
0x1800eb737  test    eax, eax
0x1800eb739  jns     loc_1800EB7CA
0x1800eb73f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb746  test    rcx, rcx
0x1800eb749  jnz     short loc_1800EB78C
0x1800eb74b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eb751  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb758  mov     rcx, rax
0x1800eb75b  test    rax, rax
0x1800eb75e  jz      short loc_1800EB77E
0x1800eb760  mov     rax, [rax]
0x1800eb763  mov     edx, 7F0h
0x1800eb768  mov     rax, [rax+8]
0x1800eb76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb771  test    eax, eax
0x1800eb773  jz      short loc_1800EB77E
0x1800eb775  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb77c  jmp     short loc_1800EB78C
0x1800eb77e  lea     rcx, qword_1801B07E0; this
0x1800eb785  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb78c  cmp     [rcx+8], r13b
0x1800eb790  jz      short loc_1800EB7B3
0x1800eb792  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eb797  cmp     [rax+7CCh], ebx
0x1800eb79d  jz      short loc_1800EB7B3
0x1800eb79f  mov     r9d, ebx; int
0x1800eb7a2  mov     r8d, 7Fh; int
0x1800eb7a8  mov     rdx, r12; char *
0x1800eb7ab  mov     rcx, rax; this
0x1800eb7ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eb7b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eb7ba  jb      loc_1800EB5B4
0x1800eb7c0  mov     edx, 1Ah
0x1800eb7c5  jmp     loc_1800EB596
0x1800eb7ca  cmp     [r14+1D8h], r13d
0x1800eb7d1  jnz     short loc_1800EB7E3
0x1800eb7d3  mov     rax, [rbp+arg_18]
0x1800eb7d7  mov     [rdi+1D0h], rax
0x1800eb7de  jmp     loc_1800EBA54
0x1800eb7e3  cmp     [rdi+1E1h], r13b
0x1800eb7ea  jz      loc_1800EBA54
0x1800eb7f0  mov     r12, [rbp+arg_18]
0x1800eb7f4  lea     rdx, [rbp+var_18]; double *
0x1800eb7f8  sub     r12, [rdi+1D8h]
0x1800eb7ff  xorps   xmm0, xmm0
0x1800eb802  mov     rcx, r14; this
0x1800eb805  movsd   [rbp+var_18], xmm0
0x1800eb80a  call    ?GetSamplesPerSecond@CAVIStreamSink@@AEAAJPEAN@Z; CAVIStreamSink::GetSamplesPerSecond(double *)
0x1800eb80f  mov     ebx, eax
0x1800eb811  test    eax, eax
0x1800eb813  jns     loc_1800EB8A8
0x1800eb819  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb820  test    rcx, rcx
0x1800eb823  jnz     short loc_1800EB866
0x1800eb825  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eb82b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb832  mov     rcx, rax
0x1800eb835  test    rax, rax
0x1800eb838  jz      short loc_1800EB858
0x1800eb83a  mov     rax, [rax]
0x1800eb83d  mov     edx, 7F0h
0x1800eb842  mov     rax, [rax+8]
0x1800eb846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb84b  test    eax, eax
0x1800eb84d  jz      short loc_1800EB858
0x1800eb84f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb856  jmp     short loc_1800EB866
0x1800eb858  lea     rcx, qword_1801B07E0; this
0x1800eb85f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb866  cmp     [rcx+8], r13b
0x1800eb86a  jz      short loc_1800EB891
0x1800eb86c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eb871  cmp     [rax+7CCh], ebx
0x1800eb877  jz      short loc_1800EB891
0x1800eb879  mov     r9d, ebx; int
0x1800eb87c  lea     rdx, aCavistreamsink_3; "CAVIStreamSink::ProcessSample"
0x1800eb883  mov     r8d, 88h; int
0x1800eb889  mov     rcx, rax; this
0x1800eb88c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eb891  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eb898  jb      loc_1800EB5B4
0x1800eb89e  mov     edx, 1Bh
0x1800eb8a3  jmp     loc_1800EB596
0x1800eb8a8  xorps   xmm0, xmm0
0x1800eb8ab  cvtsi2sd xmm0, r12
0x1800eb8b0  mulsd   xmm0, [rbp+var_18]
0x1800eb8b5  divsd   xmm0, cs:__real@416312d000000000
0x1800eb8bd  addsd   xmm0, cs:__real@3feccccccccccccd
0x1800eb8c5  cvttsd2si r12d, xmm0
0x1800eb8ca  test    r12d, r12d
0x1800eb8cd  jle     loc_1800EBA36
0x1800eb8d3  mov     rcx, [rdi+170h]
0x1800eb8da  mov     r9d, r12d
0x1800eb8dd  xor     edx, edx
0x1800eb8df  mov     r8d, 80000000h
0x1800eb8e5  mov     rax, [rcx]
0x1800eb8e8  mov     rax, [rax+20h]
0x1800eb8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb8f1  mov     ebx, eax
0x1800eb8f3  test    eax, eax
0x1800eb8f5  jns     loc_1800EB98A
0x1800eb8fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb902  test    rcx, rcx
0x1800eb905  jnz     short loc_1800EB948
0x1800eb907  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eb90d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb914  mov     rcx, rax
0x1800eb917  test    rax, rax
0x1800eb91a  jz      short loc_1800EB93A
0x1800eb91c  mov     rax, [rax]
0x1800eb91f  mov     edx, 7F0h
0x1800eb924  mov     rax, [rax+8]
0x1800eb928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb92d  test    eax, eax
0x1800eb92f  jz      short loc_1800EB93A
0x1800eb931  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb938  jmp     short loc_1800EB948
0x1800eb93a  lea     rcx, qword_1801B07E0; this
0x1800eb941  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eb948  cmp     [rcx+8], r13b
0x1800eb94c  jz      short loc_1800EB973
0x1800eb94e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eb953  cmp     [rax+7CCh], ebx
0x1800eb959  jz      short loc_1800EB973
0x1800eb95b  mov     r9d, ebx; int
0x1800eb95e  lea     rdx, aCavistreamsink_3; "CAVIStreamSink::ProcessSample"
0x1800eb965  mov     r8d, 8Ch; int
0x1800eb96b  mov     rcx, rax; this
0x1800eb96e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eb973  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eb97a  jb      loc_1800EB5B4
0x1800eb980  mov     edx, 1Ch
0x1800eb985  jmp     loc_1800EB596
0x1800eb98a  mov     rcx, [rbp+arg_0]; this
0x1800eb98e  lea     rdx, [rdi+1ECh]; char *
0x1800eb995  mov     r8d, r12d; unsigned int
0x1800eb998  call    ?WriteDroppedFramesToStdIndex@CAVIMediaSink@@QEAAJPEADK@Z; CAVIMediaSink::WriteDroppedFramesToStdIndex(char *,ulong)
0x1800eb99d  mov     ebx, eax
  ... truncated ...
```
