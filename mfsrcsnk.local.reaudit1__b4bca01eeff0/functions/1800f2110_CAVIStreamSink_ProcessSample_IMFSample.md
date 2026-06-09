# CAVIStreamSink::ProcessSample(IMFSample *)

- ea: `0x1800f2110`
- end: `0x1800f2cc5`
- name: `?ProcessSample@CAVIStreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `2997`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18004720c`
- `0x1800790a8`
- `0x180079680`
- `0x1800cbd18`
- `0x1800f2110`
- `0x180110a94`
- `0x180124a8c`
- `0x18012cf20`
- `0x18012f59c`
- `0x18012f824`
- `0x1801323d4`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f2243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f2267`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f2b2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f2243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f2267`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f2b2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f2178`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f227d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f2178`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f227d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f21a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f229e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2344`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f23f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f24d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f25bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f266f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2742`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f280b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f28c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2975`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2a1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2b5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2bb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f21a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f229e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2344`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f23f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f24d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f25bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f266f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2742`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f280b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f28c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2975`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2a1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2b5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f2bb0`

## string_xrefs

- `0x1800f2127`: `CAVIStreamSink::ProcessSample`
- `0x1800f2532`: `CAVIStreamSink::ProcessSample`
- `0x1800f261a`: `CAVIStreamSink::ProcessSample`
- `0x1800f26cc`: `CAVIStreamSink::ProcessSample`
- `0x1800f26f8`: `CAVIStreamSink::ProcessSample`

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
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v26 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v31 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v35 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v39 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v44 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v48 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v52 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v55 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v65 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( (unsigned __int8)byte_1801BA10A >= 8u )
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
        v63 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800f2110  push    rbp
0x1800f2112  push    rbx
0x1800f2113  push    rsi
0x1800f2114  push    rdi
0x1800f2115  push    r12
0x1800f2117  push    r13
0x1800f2119  push    r14
0x1800f211b  push    r15
0x1800f211d  mov     rbp, rsp
0x1800f2120  sub     rsp, 58h
0x1800f2124  mov     r15, rdx
0x1800f2127  lea     r12, aCavistreamsink_3; "CAVIStreamSink::ProcessSample"
0x1800f212e  mov     rdi, rcx
0x1800f2131  mov     rdx, r12; char *
0x1800f2134  mov     r8d, 67h ; 'g'; int
0x1800f213a  lea     rcx, [rbp+arg_0]; this
0x1800f213e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f2143  mov     rax, r15
0x1800f2146  lea     rsi, [rdi+230h]
0x1800f214d  neg     rax
0x1800f2150  mov     rcx, rsi; lpCriticalSection
0x1800f2153  sbb     ebx, ebx
0x1800f2155  xor     r13d, r13d
0x1800f2158  not     ebx
0x1800f215a  mov     [rbp+arg_8], r13d
0x1800f215e  and     ebx, 80004003h
0x1800f2164  mov     [rbp+arg_18], r13
0x1800f2168  mov     [rbp+var_20], r13
0x1800f216c  mov     [rbp+arg_10], r13d
0x1800f2170  mov     [rbp+var_28], r13
0x1800f2174  mov     [rbp+arg_0], r13
0x1800f2178  call    cs:__imp_EnterCriticalSection
0x1800f217f  nop     dword ptr [rax+rax+00h]
0x1800f2184  lea     r14, [rdi-10h]
0x1800f2188  cmp     [r14+178h], r13
0x1800f218f  jnz     loc_1800F2254
0x1800f2195  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f219c  mov     ebx, 0C00D4A38h
0x1800f21a1  test    rcx, rcx
0x1800f21a4  jnz     short loc_1800F21ED
0x1800f21a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f21ad  nop     dword ptr [rax+rax+00h]
0x1800f21b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f21b9  mov     rcx, rax
0x1800f21bc  test    rax, rax
0x1800f21bf  jz      short loc_1800F21DF
0x1800f21c1  mov     rax, [rax]
0x1800f21c4  mov     edx, 7F0h
0x1800f21c9  mov     rax, [rax+8]
0x1800f21cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f21d2  test    eax, eax
0x1800f21d4  jz      short loc_1800F21DF
0x1800f21d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f21dd  jmp     short loc_1800F21ED
0x1800f21df  lea     rcx, qword_1801B97E0; this
0x1800f21e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f21ed  cmp     [rcx+8], r13b
0x1800f21f1  jz      short loc_1800F2214
0x1800f21f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f21f8  cmp     [rax+7CCh], ebx
0x1800f21fe  jz      short loc_1800F2214
0x1800f2200  mov     r9d, ebx; int
0x1800f2203  mov     r8d, 72h ; 'r'; int
0x1800f2209  mov     rdx, r12; char *
0x1800f220c  mov     rcx, rax; this
0x1800f220f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f2214  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f221b  jb      short loc_1800F2240
0x1800f221d  mov     edx, 17h
0x1800f2222  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2229  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800f2230  mov     r9, r14
0x1800f2233  mov     [rsp+58h+var_38], ebx
0x1800f2237  mov     rcx, [rcx+10h]
0x1800f223b  call    WPP_SF_qD
0x1800f2240  mov     rcx, rsi; lpCriticalSection
0x1800f2243  call    cs:__imp_LeaveCriticalSection
0x1800f224a  nop     dword ptr [rax+rax+00h]
0x1800f224f  jmp     loc_1800F2C96
0x1800f2254  lea     rdx, [rdi+168h]
0x1800f225b  lea     rcx, [rbp+arg_0]
0x1800f225f  call    ??4?$ComPtr@VCAVIMediaSink@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(Microsoft::WRL::ComPtr<CAVIMediaSink> const &)
0x1800f2264  mov     rcx, rsi; lpCriticalSection
0x1800f2267  call    cs:__imp_LeaveCriticalSection
0x1800f226e  nop     dword ptr [rax+rax+00h]
0x1800f2273  lea     rsi, [rdi+208h]
0x1800f227a  mov     rcx, rsi; lpCriticalSection
0x1800f227d  call    cs:__imp_EnterCriticalSection
0x1800f2284  nop     dword ptr [rax+rax+00h]
0x1800f2289  test    r15, r15
0x1800f228c  jnz     loc_1800F2323
0x1800f2292  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f2299  test    rcx, rcx
0x1800f229c  jnz     short loc_1800F22E5
0x1800f229e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f22a5  nop     dword ptr [rax+rax+00h]
0x1800f22aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f22b1  mov     rcx, rax
0x1800f22b4  test    rax, rax
0x1800f22b7  jz      short loc_1800F22D7
0x1800f22b9  mov     rax, [rax]
0x1800f22bc  mov     edx, 7F0h
0x1800f22c1  mov     rax, [rax+8]
0x1800f22c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f22ca  test    eax, eax
0x1800f22cc  jz      short loc_1800F22D7
0x1800f22ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f22d5  jmp     short loc_1800F22E5
0x1800f22d7  lea     rcx, qword_1801B97E0; this
0x1800f22de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f22e5  cmp     [rcx+8], r13b
0x1800f22e9  jz      short loc_1800F230C
0x1800f22eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f22f0  cmp     [rax+7CCh], ebx
0x1800f22f6  jz      short loc_1800F230C
0x1800f22f8  mov     r9d, ebx; int
0x1800f22fb  mov     r8d, 79h ; 'y'; int
0x1800f2301  mov     rdx, r12; char *
0x1800f2304  mov     rcx, rax; this
0x1800f2307  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f230c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f2313  jb      loc_1800F2240
0x1800f2319  mov     edx, 18h
0x1800f231e  jmp     loc_1800F2222
0x1800f2323  mov     rdx, r15; struct IMFSample *
0x1800f2326  mov     rcx, rdi; this
0x1800f2329  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x1800f232e  mov     ebx, eax
0x1800f2330  test    eax, eax
0x1800f2332  jns     loc_1800F23C9
0x1800f2338  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f233f  test    rcx, rcx
0x1800f2342  jnz     short loc_1800F238B
0x1800f2344  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f234b  nop     dword ptr [rax+rax+00h]
0x1800f2350  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f2357  mov     rcx, rax
0x1800f235a  test    rax, rax
0x1800f235d  jz      short loc_1800F237D
0x1800f235f  mov     rax, [rax]
0x1800f2362  mov     edx, 7F0h
0x1800f2367  mov     rax, [rax+8]
0x1800f236b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2370  test    eax, eax
0x1800f2372  jz      short loc_1800F237D
0x1800f2374  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f237b  jmp     short loc_1800F238B
0x1800f237d  lea     rcx, qword_1801B97E0; this
0x1800f2384  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f238b  cmp     [rcx+8], r13b
0x1800f238f  jz      short loc_1800F23B2
0x1800f2391  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f2396  cmp     [rax+7CCh], ebx
0x1800f239c  jz      short loc_1800F23B2
0x1800f239e  mov     r9d, ebx; int
0x1800f23a1  mov     r8d, 7Ch ; '|'; int
0x1800f23a7  mov     rdx, r12; char *
0x1800f23aa  mov     rcx, rax; this
0x1800f23ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f23b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f23b9  jb      loc_1800F2240
0x1800f23bf  mov     edx, 19h
0x1800f23c4  jmp     loc_1800F2222
0x1800f23c9  mov     rax, [r15]
0x1800f23cc  lea     rdx, [rbp+arg_18]
0x1800f23d0  mov     rcx, r15
0x1800f23d3  mov     rax, [rax+118h]
0x1800f23da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f23df  mov     ebx, eax
0x1800f23e1  test    eax, eax
0x1800f23e3  jns     loc_1800F247A
0x1800f23e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f23f0  test    rcx, rcx
0x1800f23f3  jnz     short loc_1800F243C
0x1800f23f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f23fc  nop     dword ptr [rax+rax+00h]
0x1800f2401  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f2408  mov     rcx, rax
0x1800f240b  test    rax, rax
0x1800f240e  jz      short loc_1800F242E
0x1800f2410  mov     rax, [rax]
0x1800f2413  mov     edx, 7F0h
0x1800f2418  mov     rax, [rax+8]
0x1800f241c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2421  test    eax, eax
0x1800f2423  jz      short loc_1800F242E
0x1800f2425  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f242c  jmp     short loc_1800F243C
0x1800f242e  lea     rcx, qword_1801B97E0; this
0x1800f2435  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f243c  cmp     [rcx+8], r13b
0x1800f2440  jz      short loc_1800F2463
0x1800f2442  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f2447  cmp     [rax+7CCh], ebx
0x1800f244d  jz      short loc_1800F2463
0x1800f244f  mov     r9d, ebx; int
0x1800f2452  mov     r8d, 7Fh; int
0x1800f2458  mov     rdx, r12; char *
0x1800f245b  mov     rcx, rax; this
0x1800f245e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f2463  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f246a  jb      loc_1800F2240
0x1800f2470  mov     edx, 1Ah
0x1800f2475  jmp     loc_1800F2222
0x1800f247a  cmp     [r14+1D8h], r13d
0x1800f2481  jnz     short loc_1800F2493
0x1800f2483  mov     rax, [rbp+arg_18]
0x1800f2487  mov     [rdi+1D0h], rax
0x1800f248e  jmp     loc_1800F2716
0x1800f2493  cmp     [rdi+1E1h], r13b
0x1800f249a  jz      loc_1800F2716
0x1800f24a0  mov     r12, [rbp+arg_18]
0x1800f24a4  lea     rdx, [rbp+var_18]; double *
0x1800f24a8  sub     r12, [rdi+1D8h]
0x1800f24af  xorps   xmm0, xmm0
0x1800f24b2  mov     rcx, r14; this
0x1800f24b5  movsd   [rbp+var_18], xmm0
0x1800f24ba  call    ?GetSamplesPerSecond@CAVIStreamSink@@AEAAJPEAN@Z; CAVIStreamSink::GetSamplesPerSecond(double *)
0x1800f24bf  mov     ebx, eax
0x1800f24c1  test    eax, eax
0x1800f24c3  jns     loc_1800F255E
0x1800f24c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f24d0  test    rcx, rcx
0x1800f24d3  jnz     short loc_1800F251C
0x1800f24d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f24dc  nop     dword ptr [rax+rax+00h]
0x1800f24e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f24e8  mov     rcx, rax
0x1800f24eb  test    rax, rax
0x1800f24ee  jz      short loc_1800F250E
0x1800f24f0  mov     rax, [rax]
0x1800f24f3  mov     edx, 7F0h
0x1800f24f8  mov     rax, [rax+8]
0x1800f24fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2501  test    eax, eax
0x1800f2503  jz      short loc_1800F250E
0x1800f2505  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f250c  jmp     short loc_1800F251C
0x1800f250e  lea     rcx, qword_1801B97E0; this
0x1800f2515  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f251c  cmp     [rcx+8], r13b
0x1800f2520  jz      short loc_1800F2547
0x1800f2522  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f2527  cmp     [rax+7CCh], ebx
0x1800f252d  jz      short loc_1800F2547
0x1800f252f  mov     r9d, ebx; int
0x1800f2532  lea     rdx, aCavistreamsink_3; "CAVIStreamSink::ProcessSample"
0x1800f2539  mov     r8d, 88h; int
0x1800f253f  mov     rcx, rax; this
0x1800f2542  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f2547  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f254e  jb      loc_1800F2240
0x1800f2554  mov     edx, 1Bh
0x1800f2559  jmp     loc_1800F2222
0x1800f255e  xorps   xmm0, xmm0
0x1800f2561  cvtsi2sd xmm0, r12
0x1800f2566  mulsd   xmm0, [rbp+var_18]
0x1800f256b  divsd   xmm0, cs:__real@416312d000000000
0x1800f2573  addsd   xmm0, cs:__real@3feccccccccccccd
0x1800f257b  cvttsd2si r12d, xmm0
0x1800f2580  test    r12d, r12d
0x1800f2583  jle     loc_1800F26F8
0x1800f2589  mov     rcx, [rdi+170h]
0x1800f2590  mov     r9d, r12d
0x1800f2593  xor     edx, edx
0x1800f2595  mov     r8d, 80000000h
0x1800f259b  mov     rax, [rcx]
0x1800f259e  mov     rax, [rax+20h]
0x1800f25a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f25a7  mov     ebx, eax
0x1800f25a9  test    eax, eax
0x1800f25ab  jns     loc_1800F2646
0x1800f25b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f25b8  test    rcx, rcx
0x1800f25bb  jnz     short loc_1800F2604
0x1800f25bd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f25c4  nop     dword ptr [rax+rax+00h]
0x1800f25c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f25d0  mov     rcx, rax
0x1800f25d3  test    rax, rax
0x1800f25d6  jz      short loc_1800F25F6
0x1800f25d8  mov     rax, [rax]
0x1800f25db  mov     edx, 7F0h
0x1800f25e0  mov     rax, [rax+8]
0x1800f25e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f25e9  test    eax, eax
0x1800f25eb  jz      short loc_1800F25F6
0x1800f25ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f25f4  jmp     short loc_1800F2604
0x1800f25f6  lea     rcx, qword_1801B97E0; this
0x1800f25fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f2604  cmp     [rcx+8], r13b
0x1800f2608  jz      short loc_1800F262F
0x1800f260a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f260f  cmp     [rax+7CCh], ebx
0x1800f2615  jz      short loc_1800F262F
0x1800f2617  mov     r9d, ebx; int
0x1800f261a  lea     rdx, aCavistreamsink_3; "CAVIStreamSink::ProcessSample"
0x1800f2621  mov     r8d, 8Ch; int
0x1800f2627  mov     rcx, rax; this
  ... truncated ...
```
