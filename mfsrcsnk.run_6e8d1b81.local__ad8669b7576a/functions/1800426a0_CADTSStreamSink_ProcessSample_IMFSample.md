# CADTSStreamSink::ProcessSample(IMFSample *)

- ea: `0x1800426a0`
- end: `0x180043592`
- name: `?ProcessSample@CADTSStreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `3826`
- prototype: `__int64 __fastcall(CADTSStreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180034d10`
- `0x1800426a0`
- `0x180043c9c`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042884`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042884`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042720`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042720`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042bc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ddf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042bc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ddf`
- `MFPlat!MFCreateMemoryBuffer` at `0x180042759`
- `MFPlat!MFCreateMemoryBuffer` at `0x180042759`

## string_xrefs

- `0x1800426d0`: `CADTSStreamSink::ProcessSample`
- `0x180042e1f`: `CADTSStreamSink::ProcessSample`
- `0x180042e50`: `CADTSStreamSink::ProcessSample`
- `0x180042e7e`: `CADTSStreamSink::ProcessSample`
- `0x180042eaf`: `CADTSStreamSink::ProcessSample`
- `0x180042ee0`: `CADTSStreamSink::ProcessSample`
- `0x180042f11`: `CADTSStreamSink::ProcessSample`
- `0x180042f3f`: `CADTSStreamSink::ProcessSample`
- `0x180042f6d`: `CADTSStreamSink::ProcessSample`
- `0x180042f9b`: `CADTSStreamSink::ProcessSample`
- `0x180042fca`: `CADTSStreamSink::ProcessSample`
- `0x180042ff9`: `CADTSStreamSink::ProcessSample`
- `0x180043027`: `CADTSStreamSink::ProcessSample`
- `0x180043058`: `CADTSStreamSink::ProcessSample`
- `0x18004308a`: `CADTSStreamSink::ProcessSample`
- `0x1800430bb`: `CADTSStreamSink::ProcessSample`
- `0x1800430e9`: `CADTSStreamSink::ProcessSample`

## pseudocode

```c
__int64 __fastcall CADTSStreamSink::ProcessSample(struct _RTL_CRITICAL_SECTION *this, struct IMFSample *a2)
{
  int v3; // r12d
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  HANDLE *p_LockSemaphore; // r14
  HRESULT v10; // esi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // rcx
  CallStackTracing *v20; // rcx
  int v22; // eax
  unsigned int i; // edi
  bool v24; // zf
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rcx
  __int64 v31; // rdx
  CallStackTracing *v32; // rcx
  int v33; // eax
  CallStackTracing *v34; // rcx
  wchar_t *v35; // rdi
  CallStackTracing *v36; // rax
  wchar_t *v37; // rdi
  CallStackTracing *v38; // rax
  wchar_t *v39; // rdi
  CallStackTracing *v40; // rax
  wchar_t *v41; // rdi
  CallStackTracing *v42; // rax
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  wchar_t *v51; // rdi
  CallStackTracing *v52; // rax
  wchar_t *v53; // rdi
  CallStackTracing *v54; // rax
  wchar_t *v55; // rdi
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  struct CallStackContext *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  struct CallStackContext *v61; // rax
  struct CallStackContext *v62; // rax
  struct CallStackContext *v63; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *v69; // rax
  struct CallStackContext *v70; // rax
  struct CallStackContext *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rdx
  unsigned int j; // esi
  struct IMFSampleVtbl *v76; // rax
  __int64 v77; // rdx
  int v78; // r12d
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 v81; // rdx
  struct IMFSampleVtbl *v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rdx
  IMFMediaBuffer *ppBuffer; // [rsp+30h] [rbp-20h] BYREF
  __int64 v86; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v87[2]; // [rsp+40h] [rbp-10h] BYREF
  IMFMediaBuffer *v88; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v89; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v90; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
    v7 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v7 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v8 = 2 * v7;
      *((_QWORD *)ThreadRelativeContext + v8) = "CADTSStreamSink::ProcessSample";
      *((_DWORD *)ThreadRelativeContext + 2 * v8 + 2) = 131;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v86 = 0;
  v90 = 0;
  v89 = 0;
  EnterCriticalSection(this + 10);
  p_LockSemaphore = &this[-1].LockSemaphore;
  v10 = CBaseStreamSink::ProcessSample((CBaseStreamSink *)this, a2);
  if ( v10 >= 0 )
  {
    ppBuffer = 0;
    if ( *((_DWORD *)p_LockSemaphore + 167) )
    {
      v10 = MFCreateMemoryBuffer(7u, &ppBuffer);
      if ( v10 < 0 )
      {
        v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
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
          v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v58 + 499) != v10 )
            CallStackContext::TraceFailure(v58, "CADTSStreamSink::ProcessSample", 151, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v73 = 21;
        goto LABEL_138;
      }
      v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
              ppBuffer,
              &v86,
              0,
              0);
      if ( v10 < 0 )
      {
        v30 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v30 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext(v30);
          if ( *((_DWORD *)v59 + 499) != v10 )
            CallStackContext::TraceFailure(v59, "CADTSStreamSink::ProcessSample", 154, v10);
        }
        if ( g_wppLevels )
        {
          v31 = 22;
          goto LABEL_67;
        }
LABEL_19:
        if ( ppBuffer )
          ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Release)(ppBuffer);
        goto LABEL_21;
      }
      v13 = v86;
      *(_DWORD *)v86 = *((_DWORD *)p_LockSemaphore + 168);
      *(_WORD *)(v13 + 4) = *((_WORD *)p_LockSemaphore + 338);
      *(_BYTE *)(v13 + 6) = *((_BYTE *)p_LockSemaphore + 678);
      lpVtbl = a2->lpVtbl;
      LODWORD(v88) = 0;
      v10 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer **))lpVtbl->GetTotalLength)(a2, &v88);
      if ( v10 < 0 )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v60 + 499) != v10 )
            CallStackContext::TraceFailure(v60, "CADTSStreamSink::ProcessSample", 160, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v73 = 23;
        goto LABEL_138;
      }
      v17 = (int)v88;
      if ( (unsigned int)v88 > 0x1FF8 )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -2147467259;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference((unsigned int)v88, v15);
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
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v61 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v61, "CADTSStreamSink::ProcessSample", 165, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v73 = 24;
        goto LABEL_138;
      }
      LODWORD(v88) = (_DWORD)v88 + 7;
      *(_BYTE *)(v86 + 3) |= ((unsigned int)(v17 + 7) >> 11) & 3;
      *(_BYTE *)(v86 + 4) = (unsigned int)v88 >> 3;
      *(_BYTE *)(v86 + 5) |= 32 * (_BYTE)v88;
      v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, 7);
      if ( v10 < 0 )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v62 + 499) != v10 )
            CallStackContext::TraceFailure(v62, "CADTSStreamSink::ProcessSample", 176, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v73 = 25;
LABEL_138:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v73,
          WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
          &this[-1].LockSemaphore,
          v10);
LABEL_139:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
        goto LABEL_21;
      }
      v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v10 < 0 )
      {
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v20 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( *((_DWORD *)v63 + 499) != v10 )
            CallStackContext::TraceFailure(v63, "CADTSStreamSink::ProcessSample", 179, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_19;
        v31 = 26;
LABEL_67:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
          &this[-1].LockSemaphore,
          v10);
        goto LABEL_19;
      }
    }
    v10 = ((__int64 (__fastcall *)(struct IMFSample *, unsigned int *))a2->lpVtbl->GetBufferCount)(a2, &v89);
    if ( v10 >= 0 )
    {
      v22 = *((_DWORD *)p_LockSemaphore + 167);
      if ( v22 )
        ++v89;
      if ( !this[9].LockSemaphore )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v89 )
            goto LABEL_19;
          v24 = this[16].RecursionCount == 0;
          v88 = 0;
          if ( v24 )
            break;
          if ( i )
          {
            v25 = i - 1;
LABEL_31:
            v10 = ((__int64 (__fastcall *)(struct IMFSample *, __int64, IMFMediaBuffer **))a2->lpVtbl->GetBufferByIndex)(
                    a2,
                    v25,
                    &v88);
            goto LABEL_32;
          }
          if ( ppBuffer )
          {
            ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->AddRef)(ppBuffer);
            if ( v88 )
              ((void (__fastcall *)(IMFMediaBuffer *))v88->lpVtbl->Release)(v88);
            v88 = ppBuffer;
          }
LABEL_32:
          if ( v10 < 0 )
          {
            v32 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v32 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v32 + 8) )
            {
              v72 = CallStackTracing::GetThreadRelativeContext(v32);
              if ( *((_DWORD *)v72 + 499) != v10 )
                CallStackContext::TraceFailure(v72, "CADTSStreamSink::ProcessSample", 241, v10);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                32,
                WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
                &this[-1].LockSemaphore,
                v10);
            if ( v88 )
              ((void (__fastcall *)(IMFMediaBuffer *))v88->lpVtbl->Release)(v88);
            goto LABEL_19;
          }
          v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, unsigned int *))v88->lpVtbl->Lock)(
                  v88,
                  &v86,
                  0,
                  &v90);
          if ( v10 < 0 )
          {
            v55 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v26);
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
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
              v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
              if ( *((_DWORD *)v71 + 499) != v10 )
                CallStackContext::TraceFailure(v71, "CADTSStreamSink::ProcessSample", 244, v10);
            }
            if ( g_wppLevels )
            {
              v84 = 33;
LABEL_205:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v84,
                WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
                &this[-1].LockSemaphore,
                v10);
            }
LABEL_206:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v88);
            goto LABEL_19;
          }
          v28 = v90;
          if ( v90 )
          {
            v33 = (*(__int64 (__fastcall **)(HANDLE, __int64, _QWORD, HANDLE *, IMFMediaBuffer *))(*(_QWORD *)this[9].OwningThread
                                                                                                 + 104LL))(
                    this[9].OwningThread,
                    v86,
                    v90,
                    &this[8].LockSemaphore,
                    v88);
            v28 = v90;
            v3 = v33;
          }
          if ( v3 < 0 )
          {
            v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *))v88->lpVtbl->Unlock)(v88);
            if ( v10 < 0 )
            {
              v51 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v83);
                CallStackTracing::s_wpInstance = v52;
                if ( v52
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                {
                  v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v51 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v51 + 8) )
              {
                v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                if ( *((_DWORD *)v69 + 499) != v10 )
                  CallStackContext::TraceFailure(v69, "CADTSStreamSink::ProcessSample", 255, v10);
              }
              if ( g_wppLevels )
              {
                v84 = 34;
                goto LABEL_205;
              }
              goto LABEL_206;
            }
            v28 = v90;
          }
          v10 = v3;
          this[11].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)this[11].DebugInfo + (unsigned int)v28);
          if ( v3 < 0 )
          {
            v53 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v28);
              CallStackTracing::s_wpInstance = v54;
              if ( v54
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
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
              v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
              if ( *((_DWORD *)v70 + 499) != v3 )
                CallStackContext::TraceFailure(v70, "CADTSStreamSink::ProcessSample", 261, v3);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
                &this[-1].LockSemaphore,
                v3);
            goto LABEL_206;
          }
          if ( v88 )
            ((void (__fastcall *)(IMFMediaBuffer *))v88->lpVtbl->Release)(v88);
        }
        v25 = i;
        goto LABEL_31;
      }
      if ( v22 )
      {
        v10 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))a2->lpVtbl->AddBuffer)(a2, ppBuffer);
        if ( v10 >= 0 )
        {
          for ( j = 0; ; ++j )
          {
            if ( j >= v89 - 1 )
              goto LABEL_180;
            v76 = a2->lpVtbl;
            v87[0] = 0;
            v78 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, _QWORD *))v76->GetBufferByIndex)(a2, j, v87);
            if ( v78 < 0 )
              break;
            v78 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))a2->lpVtbl->RemoveBufferByIndex)(a2, j);
            if ( v78 < 0 )
            {
              v45 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v79);
                CallStackTracing::s_wpInstance = v46;
                if ( v46
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                {
                  v45 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v45 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v45 + 8) )
              {
                v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                if ( *((_DWORD *)v66 + 499) != v78 )
                  CallStackContext::TraceFailure(v66, "CADTSStreamSink::ProcessSample", 207, v78);
              }
              if ( g_wppLevels )
              {
                v80 = 30;
                goto LABEL_178;
              }
              goto LABEL_179;
            }
            ((void (__fastcall *)(struct IMFSample *, _QWORD))a2->lpVtbl->AddBuffer)(a2, v87[0]);
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v87);
          }
          v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77);
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
            v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
            if ( *((_DWORD *)v67 + 499) != v78 )
              CallStackContext::TraceFailure(v67, "CADTSStreamSink::ProcessSample", 204, v78);
          }
          if ( g_wppLevels )
          {
            v80 = 29;
LABEL_178:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v80,
              WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
              &this[-1].LockSemaphore,
              v78);
          }
LABEL_179:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v87);
          goto LABEL_180;
        }
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v65 + 499) != v10 )
            CallStackContext::TraceFailure(v65, "CADTSStreamSink::ProcessSample", 195, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v73 = 28;
      }
      else
      {
LABEL_180:
        v10 = (*(__int64 (__fastcall **)(HANDLE, struct IMFSample *, ULONG_PTR *, struct IMFSample *))(*(_QWORD *)this[9].LockSemaphore + 24LL))(
                this[9].LockSemaphore,
                a2,
                &this[8].SpinCount,
                a2);
        if ( v10 >= 0 )
        {
          v82 = a2->lpVtbl;
          LODWORD(v88) = 0;
          ((void (__fastcall *)(struct IMFSample *, IMFMediaBuffer **))v82->GetTotalLength)(a2, &v88);
          this[11].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)p_LockSemaphore[57] + (unsigned int)v88);
          goto LABEL_19;
        }
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v81);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v68 + 499) != v10 )
            CallStackContext::TraceFailure(v68, "CADTSStreamSink::ProcessSample", 214, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v73 = 31;
      }
      goto LABEL_138;
    }
    v34 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v34 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v64 = CallStackTracing::GetThreadRelativeContext(v34);
      if ( *((_DWORD *)v64 + 499) != v10 )
        CallStackContext::TraceFailure(v64, "CADTSStreamSink::ProcessSample", 183, v10);
    }
    if ( g_wppLevels )
    {
      v31 = 27;
      goto LABEL_67;
    }
    goto LABEL_19;
  }
  v29 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v29 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v29 + 8) )
  {
    v57 = CallStackTracing::GetThreadRelativeContext(v29);
    if ( *((_DWORD *)v57 + 499) != v10 )
      CallStackContext::TraceFailure(v57, "CADTSStreamSink::ProcessSample", 144, v10);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_16709ab217043d3ee1b4cf3563718313_Traceguids,
      &this[-1].LockSemaphore,
      v10);
LABEL_21:
  LeaveCriticalSection(this + 10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v88);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800426a0  mov     [rsp-38h+arg_8], rbx
0x1800426a5  push    rbp
0x1800426a6  push    rsi
0x1800426a7  push    rdi
0x1800426a8  push    r12
0x1800426aa  push    r13
0x1800426ac  push    r14
0x1800426ae  push    r15
0x1800426b0  mov     rbp, rsp
0x1800426b3  sub     rsp, 50h
0x1800426b7  mov     r13, rcx
0x1800426ba  xor     r12d, r12d
0x1800426bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800426c4  mov     r15, rdx
0x1800426c7  test    rcx, rcx
0x1800426ca  jz      loc_1800428AD
0x1800426d0  lea     rbx, aCadtsstreamsin_7; "CADTSStreamSink::ProcessSample"
0x1800426d7  mov     edi, 1
0x1800426dc  cmp     [rcx+8], r12b
0x1800426e0  jz      short loc_18004270A
0x1800426e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800426e7  mov     ecx, [rax+7C4h]
0x1800426ed  cmp     ecx, [rax+7C8h]
0x1800426f3  jnb     short loc_180042704
0x1800426f5  add     rcx, rcx
0x1800426f8  mov     [rax+rcx*8], rbx
0x1800426fc  mov     dword ptr [rax+rcx*8+8], 83h
0x180042704  add     [rax+7C4h], edi
0x18004270a  lea     rbx, [r13+190h]
0x180042711  mov     [rbp+var_18], r12
0x180042715  mov     rcx, rbx; lpCriticalSection
0x180042718  mov     [rbp+arg_18], r12d
0x18004271c  mov     [rbp+arg_10], r12d
0x180042720  call    cs:__imp_EnterCriticalSection
0x180042726  mov     rdx, r15; struct IMFSample *
0x180042729  mov     rcx, r13; this
0x18004272c  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x180042731  lea     r14, [r13-10h]
0x180042735  mov     esi, eax
0x180042737  test    eax, eax
0x180042739  js      loc_1800429AF
0x18004273f  mov     [rbp+ppBuffer], r12
0x180042743  cmp     [r14+29Ch], r12d
0x18004274a  jz      loc_1800428BE
0x180042750  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180042754  mov     ecx, 7; cbMaxLength
0x180042759  call    cs:__imp_MFCreateMemoryBuffer
0x18004275f  mov     esi, eax
0x180042761  test    eax, eax
0x180042763  js      loc_180042B7C
0x180042769  mov     rcx, [rbp+ppBuffer]
0x18004276d  lea     rdx, [rbp+var_18]
0x180042771  xor     r9d, r9d
0x180042774  xor     r8d, r8d
0x180042777  mov     rax, [rcx]
0x18004277a  mov     rax, [rax+18h]
0x18004277e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042783  mov     esi, eax
0x180042785  test    eax, eax
0x180042787  js      loc_1800429FE
0x18004278d  mov     eax, [r14+2A0h]
0x180042794  lea     rdx, [rbp+arg_0]
0x180042798  mov     rcx, [rbp+var_18]
0x18004279c  mov     [rcx], eax
0x18004279e  movzx   eax, word ptr [r14+2A4h]
0x1800427a6  mov     [rcx+4], ax
0x1800427aa  mov     al, [r14+2A6h]
0x1800427b1  mov     [rcx+6], al
0x1800427b4  mov     rcx, r15
0x1800427b7  mov     rax, [r15]
0x1800427ba  mov     dword ptr [rbp+arg_0], r12d
0x1800427be  mov     rax, [rax+168h]
0x1800427c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427ca  mov     esi, eax
0x1800427cc  test    eax, eax
0x1800427ce  js      loc_180042BB8
0x1800427d4  mov     ecx, dword ptr [rbp+arg_0]
0x1800427d7  cmp     ecx, 1FF8h
0x1800427dd  ja      loc_180042BF4
0x1800427e3  mov     rax, [rbp+var_18]
0x1800427e7  add     ecx, 7
0x1800427ea  mov     dword ptr [rbp+arg_0], ecx
0x1800427ed  mov     edx, 7
0x1800427f2  shr     ecx, 0Bh
0x1800427f5  and     cl, 3
0x1800427f8  or      [rax+3], cl
0x1800427fb  mov     rax, [rbp+var_18]
0x1800427ff  mov     ecx, dword ptr [rbp+arg_0]
0x180042802  shr     ecx, 3
0x180042805  mov     [rax+4], cl
0x180042808  mov     al, byte ptr [rbp+arg_0]
0x18004280b  mov     rcx, [rbp+var_18]
0x18004280f  shl     al, 5
0x180042812  or      [rcx+5], al
0x180042815  mov     rcx, [rbp+ppBuffer]
0x180042819  mov     rax, [rcx]
0x18004281c  mov     rax, [rax+30h]
0x180042820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042825  mov     esi, eax
0x180042827  test    eax, eax
0x180042829  js      loc_180042C35
0x18004282f  mov     rcx, [rbp+ppBuffer]
0x180042833  mov     rax, [rcx]
0x180042836  mov     rax, [rax+20h]
0x18004283a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004283f  mov     esi, eax
0x180042841  test    eax, eax
0x180042843  jns     short loc_1800428BE
0x180042845  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004284c  test    rcx, rcx
0x18004284f  jz      loc_180042A62
0x180042855  cmp     [rcx+8], r12b
0x180042859  jnz     loc_180042F2B
0x18004285f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180042866  jnb     loc_180043226
0x18004286c  mov     rcx, [rbp+ppBuffer]
0x180042870  test    rcx, rcx
0x180042873  jz      short loc_180042881
0x180042875  mov     rax, [rcx]
0x180042878  mov     rax, [rax+10h]
0x18004287c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042881  mov     rcx, rbx; lpCriticalSection
0x180042884  call    cs:__imp_LeaveCriticalSection
0x18004288a  lea     rcx, [rbp+arg_0]; this
0x18004288e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180042893  mov     rbx, [rsp+50h+arg_8]
0x18004289b  mov     eax, esi
0x18004289d  add     rsp, 50h
0x1800428a1  pop     r15
0x1800428a3  pop     r14
0x1800428a5  pop     r13
0x1800428a7  pop     r12
0x1800428a9  pop     rdi
0x1800428aa  pop     rsi
0x1800428ab  pop     rbp
0x1800428ac  retn
0x1800428ad  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800428b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800428b9  jmp     loc_1800426D0
0x1800428be  mov     rax, [r15]
0x1800428c1  lea     rdx, [rbp+arg_10]
0x1800428c5  mov     rcx, r15
0x1800428c8  mov     rax, [rax+138h]
0x1800428cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428d4  mov     esi, eax
0x1800428d6  test    eax, eax
0x1800428d8  js      loc_180042B23
0x1800428de  mov     eax, [r14+29Ch]
0x1800428e5  test    eax, eax
0x1800428e7  jz      short loc_1800428EC
0x1800428e9  add     [rbp+arg_10], edi
0x1800428ec  cmp     [r13+180h], r12
0x1800428f3  jnz     loc_180043230
0x1800428f9  xor     edi, edi
0x1800428fb  cmp     edi, [rbp+arg_10]
0x1800428fe  jnb     loc_18004286C
0x180042904  cmp     dword ptr [r13+28Ch], 0
0x18004290c  mov     [rbp+arg_0], 0
0x180042914  jz      loc_180043460
0x18004291a  test    edi, edi
0x18004291c  jz      loc_180042A2F
0x180042922  lea     edx, [rdi-1]
0x180042925  mov     rax, [r15]
0x180042928  lea     r8, [rbp+arg_0]
0x18004292c  mov     rcx, r15
0x18004292f  mov     rax, [rax+140h]
0x180042936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004293b  mov     esi, eax
0x18004293d  test    esi, esi
0x18004293f  js      loc_180042A73
0x180042945  mov     rcx, [rbp+arg_0]
0x180042949  lea     r9, [rbp+arg_18]
0x18004294d  xor     r8d, r8d
0x180042950  lea     rdx, [rbp+var_18]
0x180042954  mov     rax, [rcx]
0x180042957  mov     rax, [rax+18h]
0x18004295b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042960  mov     esi, eax
0x180042962  test    eax, eax
0x180042964  js      loc_180042DCC
0x18004296a  mov     edx, [rbp+arg_18]
0x18004296d  test    edx, edx
0x18004296f  jnz     loc_180042ADD
0x180042975  test    r12d, r12d
0x180042978  js      loc_180043467
0x18004297e  mov     eax, edx
0x180042980  mov     esi, r12d
0x180042983  add     [r13+1B8h], rax
0x18004298a  test    r12d, r12d
0x18004298d  js      loc_180042D90
0x180042993  mov     rcx, [rbp+arg_0]
0x180042997  test    rcx, rcx
0x18004299a  jz      short loc_1800429A8
0x18004299c  mov     rax, [rcx]
0x18004299f  mov     rax, [rax+10h]
0x1800429a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429a8  inc     edi
0x1800429aa  jmp     loc_1800428FB
0x1800429af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800429b6  test    rcx, rcx
0x1800429b9  jz      loc_180042ABB
0x1800429bf  cmp     [rcx+8], r12b
0x1800429c3  jnz     loc_180042E0B
0x1800429c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800429d0  jb      loc_180042881
0x1800429d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429dd  lea     r8, WPP_16709ab217043d3ee1b4cf3563718313_Traceguids
0x1800429e4  mov     edx, 14h
0x1800429e9  mov     dword ptr [rsp+50h+var_30], esi
0x1800429ed  mov     r9, r14
0x1800429f0  mov     rcx, [rcx+10h]
0x1800429f4  call    WPP_SF_qD
0x1800429f9  jmp     loc_180042881
0x1800429fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180042a05  test    rcx, rcx
0x180042a08  jz      loc_180042ACC
0x180042a0e  cmp     [rcx+8], r12b
0x180042a12  jnz     loc_180042E6A
0x180042a18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180042a1f  jb      loc_18004286C
0x180042a25  mov     edx, 16h
0x180042a2a  jmp     loc_180042B4B
0x180042a2f  mov     rcx, [rbp+ppBuffer]
0x180042a33  test    rcx, rcx
0x180042a36  jz      loc_18004293D
0x180042a3c  mov     rax, [rcx]
0x180042a3f  mov     rax, [rax+8]
0x180042a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a48  mov     rcx, [rbp+arg_0]
0x180042a4c  test    rcx, rcx
0x180042a4f  jnz     loc_18004344F
0x180042a55  mov     rax, [rbp+ppBuffer]
0x180042a59  mov     [rbp+arg_0], rax
0x180042a5d  jmp     loc_18004293D
0x180042a62  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042a67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042a6e  jmp     loc_180042855
0x180042a73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180042a7a  xor     r12d, r12d
0x180042a7d  test    rcx, rcx
0x180042a80  jz      loc_180042B12
0x180042a86  cmp     [rcx+8], r12b
0x180042a8a  jnz     loc_1800430D5
0x180042a90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042a97  jnb     loc_18004356A
0x180042a9d  mov     rcx, [rbp+arg_0]
0x180042aa1  test    rcx, rcx
0x180042aa4  jz      loc_18004286C
0x180042aaa  mov     rax, [rcx]
0x180042aad  mov     rax, [rax+10h]
0x180042ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ab6  jmp     loc_18004286C
0x180042abb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042ac0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ac7  jmp     loc_1800429BF
0x180042acc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042ad1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ad8  jmp     loc_180042A0E
0x180042add  mov     rcx, [r13+178h]
0x180042ae4  lea     r9, [r13+158h]
0x180042aeb  mov     r10, [rbp+arg_0]
0x180042aef  mov     r8d, edx
0x180042af2  mov     rdx, [rbp+var_18]
0x180042af6  mov     [rsp+50h+var_30], r10
0x180042afb  mov     rax, [rcx]
0x180042afe  mov     rax, [rax+68h]
0x180042b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b07  mov     edx, [rbp+arg_18]
0x180042b0a  mov     r12d, eax
0x180042b0d  jmp     loc_180042975
0x180042b12  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042b17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b1e  jmp     loc_180042A86
0x180042b23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180042b2a  test    rcx, rcx
0x180042b2d  jz      short loc_180042B6E
0x180042b2f  cmp     [rcx+8], r12b
0x180042b33  jnz     loc_180042F59
0x180042b39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180042b40  jb      loc_18004286C
0x180042b46  mov     edx, 1Bh
0x180042b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b52  lea     r8, WPP_16709ab217043d3ee1b4cf3563718313_Traceguids
0x180042b59  mov     r9, r14
0x180042b5c  mov     dword ptr [rsp+50h+var_30], esi
0x180042b60  mov     rcx, [rcx+10h]
0x180042b64  call    WPP_SF_qD
0x180042b69  jmp     loc_18004286C
0x180042b6e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042b73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b7a  jmp     short loc_180042B2F
0x180042b7c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b83  test    rdi, rdi
0x180042b86  jnz     loc_180043123
0x180042b8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042b92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b99  mov     rcx, rax
0x180042b9c  test    rax, rax
0x180042b9f  jnz     loc_180043103
0x180042ba5  lea     rdi, qword_1801B07E0
  ... truncated ...
```
