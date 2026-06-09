# CAVIMediaSink::OnByteStreamWritingCompleted(IMFAsyncResult *)

- ea: `0x1800e6824`
- end: `0x1800e7157`
- name: `?OnByteStreamWritingCompleted@CAVIMediaSink@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `2355`
- prototype: `void __fastcall(CAVIMediaSink *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180125ef0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800e6824`
- `0x180109590`
- `0x180115a1c`
- `0x180124670`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e68a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6a84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6fdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e7131`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e68a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6a84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6fdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e7131`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6869`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e68b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6a7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6869`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e68b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6a7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7038`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7038`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6a9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6b2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6bdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6cfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6d8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6e1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6eac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6f40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e7086`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6a9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6b2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6bdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6cfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6d8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6e1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6eac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6f40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e7086`
- `MFPlat!MFCreateAsyncResult` at `0x1800e6985`
- `MFPlat!MFCreateAsyncResult` at `0x1800e6985`
- `MFPlat!MFPutWorkItem` at `0x1800e706a`
- `MFPlat!MFPutWorkItem` at `0x1800e706a`

## string_xrefs

- `0x1800e6843`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6af2`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6b81`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6c33`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6cc2`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6d51`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6de5`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6e74`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6f03`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e6f97`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800e70dd`: `CAVIMediaSink::OnByteStreamWritingCompleted`

## pseudocode

```c
void __fastcall CAVIMediaSink::OnByteStreamWritingCompleted(CAVIMediaSink *this, struct IMFAsyncResult *a2)
{
  HRESULT v3; // edi
  int v4; // eax
  __int64 *v5; // r15
  __int64 *v6; // rdx
  __int64 v7; // rcx
  __int64 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  char v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  IMFAsyncCallback *v24; // rdx
  unsigned __int64 v25; // rax
  IUnknown *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  unsigned __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  unsigned int v41; // edx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
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
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v71; // rcx
  unsigned int v72; // edx
  int v73; // edi
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  unsigned __int64 v80; // [rsp+70h] [rbp+40h] BYREF
  struct IMFAsyncResult *v81; // [rsp+78h] [rbp+48h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+80h] [rbp+50h] BYREF

  v81 = a2;
  v3 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v81,
    "CAVIMediaSink::OnByteStreamWritingCompleted",
    1324);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
  while ( 1 )
  {
    v4 = *((_DWORD *)this + 314);
    v5 = 0;
    if ( !v4 )
      break;
    *((_DWORD *)this + 314) = v4 - 1;
    v6 = (__int64 *)*((_QWORD *)this + 158);
    v7 = *v6;
    v5 = v6 - 1;
    v8 = (__int64 *)v6[1];
    *v8 = *v6;
    *(_QWORD *)(v7 + 8) = v8;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1288));
    v80 = 0;
    LODWORD(v81) = 0;
    if ( !v5 )
    {
      v68 = (wchar_t *)CallStackTracing::s_wpInstance;
      v3 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
        CallStackTracing::s_wpInstance = v69;
        if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
        {
          v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v68 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CAVIMediaSink::OnByteStreamWritingCompleted",
            1338,
            -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_118;
      v45 = 174;
LABEL_117:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, &WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids, this, v3);
      goto LABEL_118;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 97) + 48LL))(
           *((_QWORD *)this + 97),
           &v80);
    if ( v3 < 0 )
    {
      v65 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
        if ( *((_DWORD *)v67 + 499) != v3 )
          CallStackContext::TraceFailure(v67, "CAVIMediaSink::OnByteStreamWritingCompleted", 1340, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_118;
      v45 = 175;
      goto LABEL_117;
    }
    v15 = v5[4];
    v16 = 0;
    if ( v15 )
    {
      v17 = *((_QWORD *)this + 97);
      ppAsyncResult = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, IMFAsyncResult **))(*(_QWORD *)v17 + 120LL))(
             v17,
             0,
             v15,
             0,
             &ppAsyncResult);
      if ( v3 < 0 )
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != v3 )
            CallStackContext::TraceFailure(v44, "CAVIMediaSink::OnByteStreamWritingCompleted", 1345, v3);
        }
        if ( g_wppLevels )
        {
          v45 = 176;
          goto LABEL_117;
        }
        goto LABEL_118;
      }
      v16 = 1;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct IMFAsyncResult **))(**((_QWORD **)this + 97) + 96LL))(
           *((_QWORD *)this + 97),
           v5[5],
           *((unsigned int *)v5 + 12),
           &v81);
    if ( v3 < 0 )
    {
      v62 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v62 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v62 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
        if ( *((_DWORD *)v64 + 499) != v3 )
          CallStackContext::TraceFailure(v64, "CAVIMediaSink::OnByteStreamWritingCompleted", 1350, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_118;
      v45 = 177;
      goto LABEL_117;
    }
    v24 = (IMFAsyncCallback *)v5[7];
    *((_DWORD *)v5 + 13) = (_DWORD)v81;
    v25 = v5[4];
    if ( !v25 )
      v25 = v80;
    v5[3] = v25;
    if ( v24 )
    {
      v26 = (IUnknown *)*((_QWORD *)this + 97);
      ppAsyncResult = 0;
      v3 = MFCreateAsyncResult(v26, v24, (IUnknown *)v5, &ppAsyncResult);
      if ( v3 < 0 )
      {
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
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
          if ( *((_DWORD *)v52 + 499) != v3 )
            CallStackContext::TraceFailure(v52, "CAVIMediaSink::OnByteStreamWritingCompleted", 1360, v3);
        }
        if ( g_wppLevels )
        {
          v49 = 178;
LABEL_45:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v49,
            &WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids,
            this,
            v3);
        }
LABEL_46:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppAsyncResult);
        goto LABEL_118;
      }
      v3 = (*(__int64 (__fastcall **)(__int64, IMFAsyncResult *))(*(_QWORD *)v5[7] + 32LL))(v5[7], ppAsyncResult);
      if ( v3 < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
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
          if ( *((_DWORD *)v48 + 499) != v3 )
            CallStackContext::TraceFailure(v48, "CAVIMediaSink::OnByteStreamWritingCompleted", 1361, v3);
        }
        if ( g_wppLevels )
        {
          v49 = 179;
          goto LABEL_45;
        }
        goto LABEL_46;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppAsyncResult);
      v33 = (unsigned int)v81;
    }
    else
    {
      v33 = (unsigned int)v81;
      if ( (_DWORD)v81 != *((_DWORD *)v5 + 12) )
      {
        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        v3 = -2147467259;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v22, v23);
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
          if ( *((_DWORD *)v61 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v61, "CAVIMediaSink::OnByteStreamWritingCompleted", 1366, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_118;
        v45 = 180;
        goto LABEL_117;
      }
    }
    if ( v16 )
    {
      v34 = v80;
      ppAsyncResult = 0;
      if ( v5[4] <= v80 && v5[4] + v33 > v80 )
      {
        if ( (unsigned __int8)byte_1801B110A >= 8u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 181, &WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids);
        v3 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 97) + 32LL))(
               *((_QWORD *)this + 97),
               &v80);
        if ( v3 < 0 )
        {
          v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
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
            if ( *((_DWORD *)v55 + 499) != v3 )
              CallStackContext::TraceFailure(v55, "CAVIMediaSink::OnByteStreamWritingCompleted", 1376, v3);
          }
          if ( g_wppLevels )
          {
            v45 = 182;
            goto LABEL_117;
          }
LABEL_118:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1288));
          goto LABEL_119;
        }
        v34 = v80;
      }
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, IMFAsyncResult **))(**((_QWORD **)this + 97)
                                                                                                  + 120LL))(
             *((_QWORD *)this + 97),
             0,
             v34,
             0,
             &ppAsyncResult);
      if ( v3 < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
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
          if ( *((_DWORD *)v58 + 499) != v3 )
            CallStackContext::TraceFailure(v58, "CAVIMediaSink::OnByteStreamWritingCompleted", 1378, v3);
        }
        if ( !g_wppLevels )
          goto LABEL_118;
        v45 = 183;
        goto LABEL_117;
      }
    }
    operator delete((void *)v5[5]);
    v5[5] = 0;
    CAVIMediaSink::ByteStreamQueueEntry::`scalar deleting destructor'((CAVIMediaSink::ByteStreamQueueEntry *)v5, v41);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1288));
  }
  while ( 1 )
  {
LABEL_119:
    if ( v3 < 0 )
    {
      v71 = *((_QWORD *)this + 98);
      if ( v71 )
        (*(void (__fastcall **)(__int64, __int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)(v71 + 16) + 48LL))(
          v71 + 16,
          1,
          &GUID_00000000_0000_0000_0000_000000000000,
          (unsigned int)v3,
          0);
    }
    if ( v5 )
    {
      operator delete((void *)v5[5]);
      v5[5] = 0;
      CAVIMediaSink::ByteStreamQueueEntry::`scalar deleting destructor'((CAVIMediaSink::ByteStreamQueueEntry *)v5, v72);
      v5 = 0;
    }
    v73 = *((_DWORD *)this + 336);
    if ( GetCurrentThreadId() == v73 )
      break;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
    if ( !*((_DWORD *)this + 314) )
      goto LABEL_138;
    v3 = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 171, 0);
    if ( v3 >= 0 )
      goto LABEL_138;
    v77 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74, v75, v76);
      CallStackTracing::s_wpInstance = v78;
      if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
      {
        v77 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v77 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v77 + 8) )
    {
      v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
      if ( *((_DWORD *)v79 + 499) != v3 )
        CallStackContext::TraceFailure(v79, "CAVIMediaSink::OnByteStreamWritingCompleted", 1406, v3);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids, this, v3);
  }
  *((_BYTE *)this + 1280) = 1;
LABEL_138:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
}

```

## disassembly

```asm
0x1800e6824  mov     [rsp-38h+arg_18], rbx
0x1800e6829  mov     [rsp-38h+arg_8], rdx
0x1800e682e  push    rbp
0x1800e682f  push    rsi
0x1800e6830  push    rdi
0x1800e6831  push    r12
0x1800e6833  push    r13
0x1800e6835  push    r14
0x1800e6837  push    r15
0x1800e6839  mov     rbp, rsp
0x1800e683c  sub     rsp, 30h
0x1800e6840  mov     rsi, rcx
0x1800e6843  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800e684a  xor     r13d, r13d
0x1800e684d  lea     rcx, [rbp+arg_8]; this
0x1800e6851  mov     r8d, 52Ch; int
0x1800e6857  mov     edi, r13d
0x1800e685a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e685f  lea     rbx, [rsi+530h]
0x1800e6866  mov     rcx, rbx; lpCriticalSection
0x1800e6869  call    cs:__imp_EnterCriticalSection
0x1800e686f  mov     eax, [rsi+4E8h]
0x1800e6875  mov     r15, r13
0x1800e6878  test    eax, eax
0x1800e687a  jz      loc_1800E6FE1
0x1800e6880  dec     eax
0x1800e6882  mov     [rsi+4E8h], eax
0x1800e6888  mov     rdx, [rsi+4F0h]
0x1800e688f  mov     rcx, [rdx]
0x1800e6892  lea     r15, [rdx-8]
0x1800e6896  mov     rax, [rdx+8]
0x1800e689a  mov     [rax], rcx
0x1800e689d  mov     [rcx+8], rax
0x1800e68a1  mov     rcx, rbx; lpCriticalSection
0x1800e68a4  call    cs:__imp_LeaveCriticalSection
0x1800e68aa  lea     r12, [rsi+508h]
0x1800e68b1  mov     rcx, r12; lpCriticalSection
0x1800e68b4  call    cs:__imp_EnterCriticalSection
0x1800e68ba  mov     [rbp+arg_0], r13
0x1800e68be  mov     dword ptr [rbp+arg_8], r13d
0x1800e68c2  test    r15, r15
0x1800e68c5  jz      loc_1800E6F2F
0x1800e68cb  mov     rcx, [rsi+308h]
0x1800e68d2  lea     rdx, [rbp+arg_0]
0x1800e68d6  mov     rax, [rcx]
0x1800e68d9  mov     rax, [rax+30h]
0x1800e68dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e68e2  mov     edi, eax
0x1800e68e4  test    eax, eax
0x1800e68e6  js      loc_1800E6EA0
0x1800e68ec  mov     r8, [r15+20h]
0x1800e68f0  mov     r14b, r13b
0x1800e68f3  test    r8, r8
0x1800e68f6  jz      short loc_1800E692A
0x1800e68f8  mov     rcx, [rsi+308h]
0x1800e68ff  lea     rdx, [rbp+ppAsyncResult]
0x1800e6903  mov     [rbp+ppAsyncResult], r13
0x1800e6907  xor     r9d, r9d
0x1800e690a  mov     [rsp+30h+var_10], rdx
0x1800e690f  xor     edx, edx
0x1800e6911  mov     rax, [rcx]
0x1800e6914  mov     rax, [rax+78h]
0x1800e6918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e691d  mov     edi, eax
0x1800e691f  test    eax, eax
0x1800e6921  js      loc_1800E6A8F
0x1800e6927  mov     r14b, 1
0x1800e692a  mov     rcx, [rsi+308h]
0x1800e6931  lea     r9, [rbp+arg_8]
0x1800e6935  mov     r8d, [r15+30h]
0x1800e6939  mov     rdx, [r15+28h]
0x1800e693d  mov     rax, [rcx]
0x1800e6940  mov     rax, [rax+60h]
0x1800e6944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6949  mov     edi, eax
0x1800e694b  test    eax, eax
0x1800e694d  js      loc_1800E6E11
0x1800e6953  mov     eax, dword ptr [rbp+arg_8]
0x1800e6956  mov     rdx, [r15+38h]; pCallback
0x1800e695a  mov     [r15+34h], eax
0x1800e695e  mov     rax, [r15+20h]
0x1800e6962  test    rax, rax
0x1800e6965  cmovz   rax, [rbp+arg_0]
0x1800e696a  mov     [r15+18h], rax
0x1800e696e  test    rdx, rdx
0x1800e6971  jz      short loc_1800E69C1
0x1800e6973  mov     rcx, [rsi+308h]; punkObject
0x1800e697a  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800e697e  mov     r8, r15; punkState
0x1800e6981  mov     [rbp+ppAsyncResult], r13
0x1800e6985  call    cs:__imp_MFCreateAsyncResult
0x1800e698b  mov     edi, eax
0x1800e698d  test    eax, eax
0x1800e698f  js      loc_1800E6BD0
0x1800e6995  mov     rcx, [r15+38h]
0x1800e6999  mov     rdx, [rbp+ppAsyncResult]
0x1800e699d  mov     rax, [rcx]
0x1800e69a0  mov     rax, [rax+20h]
0x1800e69a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e69a9  mov     edi, eax
0x1800e69ab  test    eax, eax
0x1800e69ad  js      loc_1800E6B1E
0x1800e69b3  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800e69b7  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e69bc  mov     eax, dword ptr [rbp+arg_8]
0x1800e69bf  jmp     short loc_1800E69CE
0x1800e69c1  mov     eax, dword ptr [rbp+arg_8]
0x1800e69c4  cmp     eax, [r15+30h]
0x1800e69c8  jnz     loc_1800E6D7D
0x1800e69ce  test    r14b, r14b
0x1800e69d1  jz      loc_1800E6A63
0x1800e69d7  mov     r8, [rbp+arg_0]
0x1800e69db  mov     [rbp+ppAsyncResult], r13
0x1800e69df  cmp     [r15+20h], r8
0x1800e69e3  ja      short loc_1800E6A38
0x1800e69e5  add     rax, [r15+20h]
0x1800e69e9  cmp     rax, r8
0x1800e69ec  jbe     short loc_1800E6A38
0x1800e69ee  cmp     cs:byte_1801B110A, 8
0x1800e69f5  jb      short loc_1800E6A13
0x1800e69f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e69fe  lea     r8, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids
0x1800e6a05  mov     edx, 0B5h
0x1800e6a0a  mov     rcx, [rcx+60h]
0x1800e6a0e  call    WPP_SF_
0x1800e6a13  mov     rcx, [rsi+308h]
0x1800e6a1a  lea     rdx, [rbp+arg_0]
0x1800e6a1e  mov     rax, [rcx]
0x1800e6a21  mov     rax, [rax+20h]
0x1800e6a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6a2a  mov     edi, eax
0x1800e6a2c  test    eax, eax
0x1800e6a2e  js      loc_1800E6C5F
0x1800e6a34  mov     r8, [rbp+arg_0]
0x1800e6a38  mov     rcx, [rsi+308h]
0x1800e6a3f  lea     rdx, [rbp+ppAsyncResult]
0x1800e6a43  mov     [rsp+30h+var_10], rdx
0x1800e6a48  xor     r9d, r9d
0x1800e6a4b  xor     edx, edx
0x1800e6a4d  mov     rax, [rcx]
0x1800e6a50  mov     rax, [rax+78h]
0x1800e6a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6a59  mov     edi, eax
0x1800e6a5b  test    eax, eax
0x1800e6a5d  js      loc_1800E6CEE
0x1800e6a63  mov     rcx, [r15+28h]; Block
0x1800e6a67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e6a6c  mov     rcx, r15; this
0x1800e6a6f  mov     [r15+28h], r13
0x1800e6a73  call    ??_GByteStreamQueueEntry@CAVIMediaSink@@QEAAPEAXI@Z; CAVIMediaSink::ByteStreamQueueEntry::`scalar deleting destructor'(uint)
0x1800e6a78  mov     rcx, rbx; lpCriticalSection
0x1800e6a7b  call    cs:__imp_EnterCriticalSection
0x1800e6a81  mov     rcx, r12; lpCriticalSection
0x1800e6a84  call    cs:__imp_LeaveCriticalSection
0x1800e6a8a  jmp     loc_1800E686F
0x1800e6a8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6a96  test    rcx, rcx
0x1800e6a99  jnz     short loc_1800E6ADC
0x1800e6a9b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e6aa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6aa8  mov     rcx, rax
0x1800e6aab  test    rax, rax
0x1800e6aae  jz      short loc_1800E6ACE
0x1800e6ab0  mov     rax, [rax]
0x1800e6ab3  mov     edx, 7F0h
0x1800e6ab8  mov     rax, [rax+8]
0x1800e6abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6ac1  test    eax, eax
0x1800e6ac3  jz      short loc_1800E6ACE
0x1800e6ac5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6acc  jmp     short loc_1800E6ADC
0x1800e6ace  lea     rcx, qword_1801B07E0; this
0x1800e6ad5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6adc  cmp     [rcx+8], r13b
0x1800e6ae0  jz      short loc_1800E6B07
0x1800e6ae2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e6ae7  cmp     [rax+7CCh], edi
0x1800e6aed  jz      short loc_1800E6B07
0x1800e6aef  mov     r9d, edi; int
0x1800e6af2  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800e6af9  mov     r8d, 541h; int
0x1800e6aff  mov     rcx, rax; this
0x1800e6b02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e6b07  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6b0e  jb      loc_1800E6FD8
0x1800e6b14  mov     edx, 0B0h
0x1800e6b19  jmp     loc_1800E6FBA
0x1800e6b1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6b25  test    rcx, rcx
0x1800e6b28  jnz     short loc_1800E6B6B
0x1800e6b2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e6b30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6b37  mov     rcx, rax
0x1800e6b3a  test    rax, rax
0x1800e6b3d  jz      short loc_1800E6B5D
0x1800e6b3f  mov     rax, [rax]
0x1800e6b42  mov     edx, 7F0h
0x1800e6b47  mov     rax, [rax+8]
0x1800e6b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6b50  test    eax, eax
0x1800e6b52  jz      short loc_1800E6B5D
0x1800e6b54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6b5b  jmp     short loc_1800E6B6B
0x1800e6b5d  lea     rcx, qword_1801B07E0; this
0x1800e6b64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6b6b  cmp     [rcx+8], r13b
0x1800e6b6f  jz      short loc_1800E6B96
0x1800e6b71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e6b76  cmp     [rax+7CCh], edi
0x1800e6b7c  jz      short loc_1800E6B96
0x1800e6b7e  mov     r9d, edi; int
0x1800e6b81  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800e6b88  mov     r8d, 551h; int
0x1800e6b8e  mov     rcx, rax; this
0x1800e6b91  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e6b96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6b9d  jb      short loc_1800E6BC2
0x1800e6b9f  mov     edx, 0B3h
0x1800e6ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6bab  lea     r8, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids
0x1800e6bb2  mov     r9, rsi
0x1800e6bb5  mov     dword ptr [rsp+30h+var_10], edi
0x1800e6bb9  mov     rcx, [rcx+10h]
0x1800e6bbd  call    WPP_SF_qD
0x1800e6bc2  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800e6bc6  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e6bcb  jmp     loc_1800E6FD8
0x1800e6bd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6bd7  test    rcx, rcx
0x1800e6bda  jnz     short loc_1800E6C1D
0x1800e6bdc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e6be2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6be9  mov     rcx, rax
0x1800e6bec  test    rax, rax
0x1800e6bef  jz      short loc_1800E6C0F
0x1800e6bf1  mov     rax, [rax]
0x1800e6bf4  mov     edx, 7F0h
0x1800e6bf9  mov     rax, [rax+8]
0x1800e6bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6c02  test    eax, eax
0x1800e6c04  jz      short loc_1800E6C0F
0x1800e6c06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6c0d  jmp     short loc_1800E6C1D
0x1800e6c0f  lea     rcx, qword_1801B07E0; this
0x1800e6c16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6c1d  cmp     [rcx+8], r13b
0x1800e6c21  jz      short loc_1800E6C48
0x1800e6c23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e6c28  cmp     [rax+7CCh], edi
0x1800e6c2e  jz      short loc_1800E6C48
0x1800e6c30  mov     r9d, edi; int
0x1800e6c33  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800e6c3a  mov     r8d, 550h; int
0x1800e6c40  mov     rcx, rax; this
0x1800e6c43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e6c48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6c4f  jb      loc_1800E6BC2
0x1800e6c55  mov     edx, 0B2h
0x1800e6c5a  jmp     loc_1800E6BA4
0x1800e6c5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6c66  test    rcx, rcx
0x1800e6c69  jnz     short loc_1800E6CAC
0x1800e6c6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e6c71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6c78  mov     rcx, rax
0x1800e6c7b  test    rax, rax
0x1800e6c7e  jz      short loc_1800E6C9E
0x1800e6c80  mov     rax, [rax]
0x1800e6c83  mov     edx, 7F0h
0x1800e6c88  mov     rax, [rax+8]
0x1800e6c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6c91  test    eax, eax
0x1800e6c93  jz      short loc_1800E6C9E
0x1800e6c95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6c9c  jmp     short loc_1800E6CAC
0x1800e6c9e  lea     rcx, qword_1801B07E0; this
0x1800e6ca5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6cac  cmp     [rcx+8], r13b
0x1800e6cb0  jz      short loc_1800E6CD7
0x1800e6cb2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e6cb7  cmp     [rax+7CCh], edi
0x1800e6cbd  jz      short loc_1800E6CD7
0x1800e6cbf  mov     r9d, edi; int
0x1800e6cc2  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800e6cc9  mov     r8d, 560h; int
0x1800e6ccf  mov     rcx, rax; this
0x1800e6cd2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e6cd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6cde  jb      loc_1800E6FD8
0x1800e6ce4  mov     edx, 0B6h
0x1800e6ce9  jmp     loc_1800E6FBA
0x1800e6cee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6cf5  test    rcx, rcx
0x1800e6cf8  jnz     short loc_1800E6D3B
0x1800e6cfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e6d00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6d07  mov     rcx, rax
0x1800e6d0a  test    rax, rax
0x1800e6d0d  jz      short loc_1800E6D2D
0x1800e6d0f  mov     rax, [rax]
  ... truncated ...
```
