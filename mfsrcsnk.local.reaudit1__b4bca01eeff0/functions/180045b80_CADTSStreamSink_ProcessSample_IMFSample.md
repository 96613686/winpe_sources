# CADTSStreamSink::ProcessSample(IMFSample *)

- ea: `0x180045b80`
- end: `0x180046acb`
- name: `?ProcessSample@CADTSStreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `3915`
- prototype: `__int64 __fastcall(CADTSStreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180036c30`
- `0x180045b80`
- `0x18004720c`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046083`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800460c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004610c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004614e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046190`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800461ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004620c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004624a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004628b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800462cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046312`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046083`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800460c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004610c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004614e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046190`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800461ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004620c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004624a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004628b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800462cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046312`
- `MFPlat!MFCreateMemoryBuffer` at `0x180045c3f`
- `MFPlat!MFCreateMemoryBuffer` at `0x180045c3f`

## string_xrefs

- `0x180045bb0`: `CADTSStreamSink::ProcessSample`
- `0x180046358`: `CADTSStreamSink::ProcessSample`
- `0x180046389`: `CADTSStreamSink::ProcessSample`
- `0x1800463b7`: `CADTSStreamSink::ProcessSample`
- `0x1800463e8`: `CADTSStreamSink::ProcessSample`
- `0x180046419`: `CADTSStreamSink::ProcessSample`
- `0x18004644a`: `CADTSStreamSink::ProcessSample`
- `0x180046478`: `CADTSStreamSink::ProcessSample`
- `0x1800464a6`: `CADTSStreamSink::ProcessSample`
- `0x1800464d4`: `CADTSStreamSink::ProcessSample`
- `0x180046503`: `CADTSStreamSink::ProcessSample`
- `0x180046532`: `CADTSStreamSink::ProcessSample`
- `0x180046560`: `CADTSStreamSink::ProcessSample`
- `0x180046591`: `CADTSStreamSink::ProcessSample`
- `0x1800465c3`: `CADTSStreamSink::ProcessSample`
- `0x1800465f4`: `CADTSStreamSink::ProcessSample`
- `0x180046622`: `CADTSStreamSink::ProcessSample`

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
            v35 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v37 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v39 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v41 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v55 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v51 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v53 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v45 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v47 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v43 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v49 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180045b80  mov     [rsp-38h+arg_8], rbx
0x180045b85  push    rbp
0x180045b86  push    rsi
0x180045b87  push    rdi
0x180045b88  push    r12
0x180045b8a  push    r13
0x180045b8c  push    r14
0x180045b8e  push    r15
0x180045b90  mov     rbp, rsp
0x180045b93  sub     rsp, 50h
0x180045b97  mov     r13, rcx
0x180045b9a  xor     r12d, r12d
0x180045b9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180045ba4  mov     r15, rdx
0x180045ba7  test    rcx, rcx
0x180045baa  jz      loc_180045DA4
0x180045bb0  lea     rbx, aCadtsstreamsin_7; "CADTSStreamSink::ProcessSample"
0x180045bb7  mov     edi, 1
0x180045bbc  cmp     [rcx+8], r12b
0x180045bc0  jz      short loc_180045BEA
0x180045bc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045bc7  mov     ecx, [rax+7C4h]
0x180045bcd  cmp     ecx, [rax+7C8h]
0x180045bd3  jnb     short loc_180045BE4
0x180045bd5  add     rcx, rcx
0x180045bd8  mov     [rax+rcx*8], rbx
0x180045bdc  mov     dword ptr [rax+rcx*8+8], 83h
0x180045be4  add     [rax+7C4h], edi
0x180045bea  lea     rbx, [r13+190h]
0x180045bf1  mov     [rbp+var_18], r12
0x180045bf5  mov     rcx, rbx; lpCriticalSection
0x180045bf8  mov     [rbp+arg_18], r12d
0x180045bfc  mov     [rbp+arg_10], r12d
0x180045c00  call    cs:__imp_EnterCriticalSection
0x180045c07  nop     dword ptr [rax+rax+00h]
0x180045c0c  mov     rdx, r15; struct IMFSample *
0x180045c0f  mov     rcx, r13; this
0x180045c12  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x180045c17  lea     r14, [r13-10h]
0x180045c1b  mov     esi, eax
0x180045c1d  test    eax, eax
0x180045c1f  js      loc_180045EA6
0x180045c25  mov     [rbp+ppBuffer], r12
0x180045c29  cmp     [r14+29Ch], r12d
0x180045c30  jz      loc_180045DB5
0x180045c36  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180045c3a  mov     ecx, 7; cbMaxLength
0x180045c3f  call    cs:__imp_MFCreateMemoryBuffer
0x180045c46  nop     dword ptr [rax+rax+00h]
0x180045c4b  mov     esi, eax
0x180045c4d  test    eax, eax
0x180045c4f  js      loc_180046073
0x180045c55  mov     rcx, [rbp+ppBuffer]
0x180045c59  lea     rdx, [rbp+var_18]
0x180045c5d  xor     r9d, r9d
0x180045c60  xor     r8d, r8d
0x180045c63  mov     rax, [rcx]
0x180045c66  mov     rax, [rax+18h]
0x180045c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c6f  mov     esi, eax
0x180045c71  test    eax, eax
0x180045c73  js      loc_180045EF5
0x180045c79  mov     eax, [r14+2A0h]
0x180045c80  lea     rdx, [rbp+arg_0]
0x180045c84  mov     rcx, [rbp+var_18]
0x180045c88  mov     [rcx], eax
0x180045c8a  movzx   eax, word ptr [r14+2A4h]
0x180045c92  mov     [rcx+4], ax
0x180045c96  mov     al, [r14+2A6h]
0x180045c9d  mov     [rcx+6], al
0x180045ca0  mov     rcx, r15
0x180045ca3  mov     rax, [r15]
0x180045ca6  mov     dword ptr [rbp+arg_0], r12d
0x180045caa  mov     rax, [rax+168h]
0x180045cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cb6  mov     esi, eax
0x180045cb8  test    eax, eax
0x180045cba  js      loc_1800460B5
0x180045cc0  mov     ecx, dword ptr [rbp+arg_0]
0x180045cc3  cmp     ecx, 1FF8h
0x180045cc9  ja      loc_1800460F7
0x180045ccf  mov     rax, [rbp+var_18]
0x180045cd3  add     ecx, 7
0x180045cd6  mov     dword ptr [rbp+arg_0], ecx
0x180045cd9  mov     edx, 7
0x180045cde  shr     ecx, 0Bh
0x180045ce1  and     cl, 3
0x180045ce4  or      [rax+3], cl
0x180045ce7  mov     rax, [rbp+var_18]
0x180045ceb  mov     ecx, dword ptr [rbp+arg_0]
0x180045cee  shr     ecx, 3
0x180045cf1  mov     [rax+4], cl
0x180045cf4  mov     al, byte ptr [rbp+arg_0]
0x180045cf7  mov     rcx, [rbp+var_18]
0x180045cfb  shl     al, 5
0x180045cfe  or      [rcx+5], al
0x180045d01  mov     rcx, [rbp+ppBuffer]
0x180045d05  mov     rax, [rcx]
0x180045d08  mov     rax, [rax+30h]
0x180045d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d11  mov     esi, eax
0x180045d13  test    eax, eax
0x180045d15  js      loc_18004613E
0x180045d1b  mov     rcx, [rbp+ppBuffer]
0x180045d1f  mov     rax, [rcx]
0x180045d22  mov     rax, [rax+20h]
0x180045d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d2b  mov     esi, eax
0x180045d2d  test    eax, eax
0x180045d2f  jns     loc_180045DB5
0x180045d35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180045d3c  test    rcx, rcx
0x180045d3f  jz      loc_180045F59
0x180045d45  cmp     [rcx+8], r12b
0x180045d49  jnz     loc_180046464
0x180045d4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180045d56  jnb     loc_18004675F
0x180045d5c  mov     rcx, [rbp+ppBuffer]
0x180045d60  test    rcx, rcx
0x180045d63  jz      short loc_180045D71
0x180045d65  mov     rax, [rcx]
0x180045d68  mov     rax, [rax+10h]
0x180045d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d71  mov     rcx, rbx; lpCriticalSection
0x180045d74  call    cs:__imp_LeaveCriticalSection
0x180045d7b  nop     dword ptr [rax+rax+00h]
0x180045d80  lea     rcx, [rbp+arg_0]; this
0x180045d84  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045d89  mov     rbx, [rsp+50h+arg_8]
0x180045d91  mov     eax, esi
0x180045d93  add     rsp, 50h
0x180045d97  pop     r15
0x180045d99  pop     r14
0x180045d9b  pop     r13
0x180045d9d  pop     r12
0x180045d9f  pop     rdi
0x180045da0  pop     rsi
0x180045da1  pop     rbp
0x180045da2  retn
0x180045da4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180045da9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045db0  jmp     loc_180045BB0
0x180045db5  mov     rax, [r15]
0x180045db8  lea     rdx, [rbp+arg_10]
0x180045dbc  mov     rcx, r15
0x180045dbf  mov     rax, [rax+138h]
0x180045dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045dcb  mov     esi, eax
0x180045dcd  test    eax, eax
0x180045dcf  js      loc_18004601A
0x180045dd5  mov     eax, [r14+29Ch]
0x180045ddc  test    eax, eax
0x180045dde  jz      short loc_180045DE3
0x180045de0  add     [rbp+arg_10], edi
0x180045de3  cmp     [r13+180h], r12
0x180045dea  jnz     loc_180046769
0x180045df0  xor     edi, edi
0x180045df2  cmp     edi, [rbp+arg_10]
0x180045df5  jnb     loc_180045D5C
0x180045dfb  cmp     dword ptr [r13+28Ch], 0
0x180045e03  mov     [rbp+arg_0], 0
0x180045e0b  jz      loc_180046999
0x180045e11  test    edi, edi
0x180045e13  jz      loc_180045F26
0x180045e19  lea     edx, [rdi-1]
0x180045e1c  mov     rax, [r15]
0x180045e1f  lea     r8, [rbp+arg_0]
0x180045e23  mov     rcx, r15
0x180045e26  mov     rax, [rax+140h]
0x180045e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e32  mov     esi, eax
0x180045e34  test    esi, esi
0x180045e36  js      loc_180045F6A
0x180045e3c  mov     rcx, [rbp+arg_0]
0x180045e40  lea     r9, [rbp+arg_18]
0x180045e44  xor     r8d, r8d
0x180045e47  lea     rdx, [rbp+var_18]
0x180045e4b  mov     rax, [rcx]
0x180045e4e  mov     rax, [rax+18h]
0x180045e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e57  mov     esi, eax
0x180045e59  test    eax, eax
0x180045e5b  js      loc_1800462FF
0x180045e61  mov     edx, [rbp+arg_18]
0x180045e64  test    edx, edx
0x180045e66  jnz     loc_180045FD4
0x180045e6c  test    r12d, r12d
0x180045e6f  js      loc_1800469A0
0x180045e75  mov     eax, edx
0x180045e77  mov     esi, r12d
0x180045e7a  add     [r13+1B8h], rax
0x180045e81  test    r12d, r12d
0x180045e84  js      loc_1800462BD
0x180045e8a  mov     rcx, [rbp+arg_0]
0x180045e8e  test    rcx, rcx
0x180045e91  jz      short loc_180045E9F
0x180045e93  mov     rax, [rcx]
0x180045e96  mov     rax, [rax+10h]
0x180045e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e9f  inc     edi
0x180045ea1  jmp     loc_180045DF2
0x180045ea6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180045ead  test    rcx, rcx
0x180045eb0  jz      loc_180045FB2
0x180045eb6  cmp     [rcx+8], r12b
0x180045eba  jnz     loc_180046344
0x180045ec0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180045ec7  jb      loc_180045D71
0x180045ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ed4  lea     r8, WPP_16709ab217043d3ee1b4cf3563718313_Traceguids
0x180045edb  mov     edx, 14h
0x180045ee0  mov     dword ptr [rsp+50h+var_30], esi
0x180045ee4  mov     r9, r14
0x180045ee7  mov     rcx, [rcx+10h]
0x180045eeb  call    WPP_SF_qD
0x180045ef0  jmp     loc_180045D71
0x180045ef5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180045efc  test    rcx, rcx
0x180045eff  jz      loc_180045FC3
0x180045f05  cmp     [rcx+8], r12b
0x180045f09  jnz     loc_1800463A3
0x180045f0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180045f16  jb      loc_180045D5C
0x180045f1c  mov     edx, 16h
0x180045f21  jmp     loc_180046042
0x180045f26  mov     rcx, [rbp+ppBuffer]
0x180045f2a  test    rcx, rcx
0x180045f2d  jz      loc_180045E34
0x180045f33  mov     rax, [rcx]
0x180045f36  mov     rax, [rax+8]
0x180045f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f3f  mov     rcx, [rbp+arg_0]
0x180045f43  test    rcx, rcx
0x180045f46  jnz     loc_180046988
0x180045f4c  mov     rax, [rbp+ppBuffer]
0x180045f50  mov     [rbp+arg_0], rax
0x180045f54  jmp     loc_180045E34
0x180045f59  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180045f5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f65  jmp     loc_180045D45
0x180045f6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180045f71  xor     r12d, r12d
0x180045f74  test    rcx, rcx
0x180045f77  jz      loc_180046009
0x180045f7d  cmp     [rcx+8], r12b
0x180045f81  jnz     loc_18004660E
0x180045f87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045f8e  jnb     loc_180046AA3
0x180045f94  mov     rcx, [rbp+arg_0]
0x180045f98  test    rcx, rcx
0x180045f9b  jz      loc_180045D5C
0x180045fa1  mov     rax, [rcx]
0x180045fa4  mov     rax, [rax+10h]
0x180045fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fad  jmp     loc_180045D5C
0x180045fb2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180045fb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fbe  jmp     loc_180045EB6
0x180045fc3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180045fc8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fcf  jmp     loc_180045F05
0x180045fd4  mov     rcx, [r13+178h]
0x180045fdb  lea     r9, [r13+158h]
0x180045fe2  mov     r10, [rbp+arg_0]
0x180045fe6  mov     r8d, edx
0x180045fe9  mov     rdx, [rbp+var_18]
0x180045fed  mov     [rsp+50h+var_30], r10
0x180045ff2  mov     rax, [rcx]
0x180045ff5  mov     rax, [rax+68h]
0x180045ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ffe  mov     edx, [rbp+arg_18]
0x180046001  mov     r12d, eax
0x180046004  jmp     loc_180045E6C
0x180046009  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004600e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046015  jmp     loc_180045F7D
0x18004601a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180046021  test    rcx, rcx
0x180046024  jz      short loc_180046065
0x180046026  cmp     [rcx+8], r12b
0x18004602a  jnz     loc_180046492
0x180046030  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180046037  jb      loc_180045D5C
0x18004603d  mov     edx, 1Bh
0x180046042  mov     rcx, cs:WPP_GLOBAL_Control
0x180046049  lea     r8, WPP_16709ab217043d3ee1b4cf3563718313_Traceguids
0x180046050  mov     r9, r14
0x180046053  mov     dword ptr [rsp+50h+var_30], esi
0x180046057  mov     rcx, [rcx+10h]
0x18004605b  call    WPP_SF_qD
0x180046060  jmp     loc_180045D5C
0x180046065  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004606a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046071  jmp     short loc_180046026
0x180046073  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004607a  test    rdi, rdi
0x18004607d  jnz     loc_18004665C
0x180046083  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004608a  nop     dword ptr [rax+rax+00h]
0x18004608f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
