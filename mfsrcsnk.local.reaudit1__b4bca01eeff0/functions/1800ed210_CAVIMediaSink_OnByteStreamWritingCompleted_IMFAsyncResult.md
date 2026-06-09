# CAVIMediaSink::OnByteStreamWritingCompleted(IMFAsyncResult *)

- ea: `0x1800ed210`
- end: `0x1800edbc1`
- name: `?OnByteStreamWritingCompleted@CAVIMediaSink@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `2481`
- prototype: `void __fastcall(CAVIMediaSink *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18012cee0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x1800ed210`
- `0x180110a7c`
- `0x18011cbac`
- `0x18012b570`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed296`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eda21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800edb95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed296`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eda21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800edb95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed2ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed47f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eda9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed2ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed47f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eda9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eda84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eda84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed4ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed540`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed5f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed68d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed7bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed851`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed8e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed980`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800edae4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed4ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed540`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed5f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed68d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed7bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed851`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed8e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed980`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800edae4`
- `MFPlat!MFCreateAsyncResult` at `0x1800ed383`
- `MFPlat!MFCreateAsyncResult` at `0x1800ed383`
- `MFPlat!MFPutWorkItem` at `0x1800edac2`
- `MFPlat!MFPutWorkItem` at `0x1800edac2`

## string_xrefs

- `0x1800ed22f`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed508`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed59d`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed655`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed6ea`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed77f`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed819`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed8ae`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed943`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800ed9dd`: `CAVIMediaSink::OnByteStreamWritingCompleted`
- `0x1800edb41`: `CAVIMediaSink::OnByteStreamWritingCompleted`

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
  __int64 v10; // rdx
  __int64 v11; // r8
  char v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  IMFAsyncCallback *v16; // rdx
  unsigned __int64 v17; // rax
  IUnknown *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rdx
  unsigned int v25; // edx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v55; // rcx
  unsigned int v56; // edx
  int v57; // edi
  __int64 v58; // rdx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  unsigned __int64 v62; // [rsp+70h] [rbp+40h] BYREF
  struct IMFAsyncResult *v63; // [rsp+78h] [rbp+48h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+80h] [rbp+50h] BYREF

  v63 = a2;
  v3 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v63,
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
    v62 = 0;
    LODWORD(v63) = 0;
    if ( !v5 )
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      v3 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CAVIMediaSink::OnByteStreamWritingCompleted",
            1338,
            -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_118;
      v29 = 174;
LABEL_117:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids, this, v3);
      goto LABEL_118;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 97) + 48LL))(
           *((_QWORD *)this + 97),
           &v62);
    if ( v3 < 0 )
    {
      v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != v3 )
          CallStackContext::TraceFailure(v51, "CAVIMediaSink::OnByteStreamWritingCompleted", 1340, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_118;
      v29 = 175;
      goto LABEL_117;
    }
    v11 = v5[4];
    v12 = 0;
    if ( v11 )
    {
      v13 = *((_QWORD *)this + 97);
      ppAsyncResult = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, IMFAsyncResult **))(*(_QWORD *)v13 + 120LL))(
             v13,
             0,
             v11,
             0,
             &ppAsyncResult);
      if ( v3 < 0 )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
          if ( *((_DWORD *)v28 + 499) != v3 )
            CallStackContext::TraceFailure(v28, "CAVIMediaSink::OnByteStreamWritingCompleted", 1345, v3);
        }
        if ( g_wppLevels )
        {
          v29 = 176;
          goto LABEL_117;
        }
        goto LABEL_118;
      }
      v12 = 1;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct IMFAsyncResult **))(**((_QWORD **)this + 97) + 96LL))(
           *((_QWORD *)this + 97),
           v5[5],
           *((unsigned int *)v5 + 12),
           &v63);
    if ( v3 < 0 )
    {
      v46 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
        if ( *((_DWORD *)v48 + 499) != v3 )
          CallStackContext::TraceFailure(v48, "CAVIMediaSink::OnByteStreamWritingCompleted", 1350, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_118;
      v29 = 177;
      goto LABEL_117;
    }
    v16 = (IMFAsyncCallback *)v5[7];
    *((_DWORD *)v5 + 13) = (_DWORD)v63;
    v17 = v5[4];
    if ( !v17 )
      v17 = v62;
    v5[3] = v17;
    if ( v16 )
    {
      v18 = (IUnknown *)*((_QWORD *)this + 97);
      ppAsyncResult = 0;
      v3 = MFCreateAsyncResult(v18, v16, (IUnknown *)v5, &ppAsyncResult);
      if ( v3 < 0 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != v3 )
            CallStackContext::TraceFailure(v36, "CAVIMediaSink::OnByteStreamWritingCompleted", 1360, v3);
        }
        if ( g_wppLevels )
        {
          v33 = 178;
LABEL_45:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids, this, v3);
        }
LABEL_46:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppAsyncResult);
        goto LABEL_118;
      }
      v3 = (*(__int64 (__fastcall **)(__int64, IMFAsyncResult *))(*(_QWORD *)v5[7] + 32LL))(v5[7], ppAsyncResult);
      if ( v3 < 0 )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != v3 )
            CallStackContext::TraceFailure(v32, "CAVIMediaSink::OnByteStreamWritingCompleted", 1361, v3);
        }
        if ( g_wppLevels )
        {
          v33 = 179;
          goto LABEL_45;
        }
        goto LABEL_46;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppAsyncResult);
      v21 = (unsigned int)v63;
    }
    else
    {
      v21 = (unsigned int)v63;
      if ( (_DWORD)v63 != *((_DWORD *)v5 + 12) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
        v3 = -2147467259;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
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
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v45, "CAVIMediaSink::OnByteStreamWritingCompleted", 1366, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_118;
        v29 = 180;
        goto LABEL_117;
      }
    }
    if ( v12 )
    {
      v22 = v62;
      ppAsyncResult = 0;
      if ( v5[4] <= v62 && v5[4] + v21 > v62 )
      {
        if ( (unsigned __int8)byte_1801BA10A >= 8u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 181, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids);
        v3 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 97) + 32LL))(
               *((_QWORD *)this + 97),
               &v62);
        if ( v3 < 0 )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
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
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
            if ( *((_DWORD *)v39 + 499) != v3 )
              CallStackContext::TraceFailure(v39, "CAVIMediaSink::OnByteStreamWritingCompleted", 1376, v3);
          }
          if ( g_wppLevels )
          {
            v29 = 182;
            goto LABEL_117;
          }
LABEL_118:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1288));
          goto LABEL_119;
        }
        v22 = v62;
      }
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, IMFAsyncResult **))(**((_QWORD **)this + 97)
                                                                                                  + 120LL))(
             *((_QWORD *)this + 97),
             0,
             v22,
             0,
             &ppAsyncResult);
      if ( v3 < 0 )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
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
          if ( *((_DWORD *)v42 + 499) != v3 )
            CallStackContext::TraceFailure(v42, "CAVIMediaSink::OnByteStreamWritingCompleted", 1378, v3);
        }
        if ( !g_wppLevels )
          goto LABEL_118;
        v29 = 183;
        goto LABEL_117;
      }
    }
    operator delete((void *)v5[5]);
    v5[5] = 0;
    CAVIMediaSink::ByteStreamQueueEntry::`scalar deleting destructor'((CAVIMediaSink::ByteStreamQueueEntry *)v5, v25);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1288));
  }
  while ( 1 )
  {
LABEL_119:
    if ( v3 < 0 )
    {
      v55 = *((_QWORD *)this + 98);
      if ( v55 )
        (*(void (__fastcall **)(__int64, __int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)(v55 + 16) + 48LL))(
          v55 + 16,
          1,
          &GUID_00000000_0000_0000_0000_000000000000,
          (unsigned int)v3,
          0);
    }
    if ( v5 )
    {
      operator delete((void *)v5[5]);
      v5[5] = 0;
      CAVIMediaSink::ByteStreamQueueEntry::`scalar deleting destructor'((CAVIMediaSink::ByteStreamQueueEntry *)v5, v56);
      v5 = 0;
    }
    v57 = *((_DWORD *)this + 336);
    if ( GetCurrentThreadId() == v57 )
      break;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
    if ( !*((_DWORD *)this + 314) )
      goto LABEL_138;
    v3 = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 171, 0);
    if ( v3 >= 0 )
      goto LABEL_138;
    v59 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
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
      if ( *((_DWORD *)v61 + 499) != v3 )
        CallStackContext::TraceFailure(v61, "CAVIMediaSink::OnByteStreamWritingCompleted", 1406, v3);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids, this, v3);
  }
  *((_BYTE *)this + 1280) = 1;
LABEL_138:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1328));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v63);
}

```

## disassembly

```asm
0x1800ed210  mov     [rsp-38h+arg_18], rbx
0x1800ed215  mov     [rsp-38h+arg_8], rdx
0x1800ed21a  push    rbp
0x1800ed21b  push    rsi
0x1800ed21c  push    rdi
0x1800ed21d  push    r12
0x1800ed21f  push    r13
0x1800ed221  push    r14
0x1800ed223  push    r15
0x1800ed225  mov     rbp, rsp
0x1800ed228  sub     rsp, 30h
0x1800ed22c  mov     rsi, rcx
0x1800ed22f  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800ed236  xor     r13d, r13d
0x1800ed239  lea     rcx, [rbp+arg_8]; this
0x1800ed23d  mov     r8d, 52Ch; int
0x1800ed243  mov     edi, r13d
0x1800ed246  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ed24b  lea     rbx, [rsi+530h]
0x1800ed252  mov     rcx, rbx; lpCriticalSection
0x1800ed255  call    cs:__imp_EnterCriticalSection
0x1800ed25c  nop     dword ptr [rax+rax+00h]
0x1800ed261  mov     eax, [rsi+4E8h]
0x1800ed267  mov     r15, r13
0x1800ed26a  test    eax, eax
0x1800ed26c  jz      loc_1800EDA2D
0x1800ed272  dec     eax
0x1800ed274  mov     [rsi+4E8h], eax
0x1800ed27a  mov     rdx, [rsi+4F0h]
0x1800ed281  mov     rcx, [rdx]
0x1800ed284  lea     r15, [rdx-8]
0x1800ed288  mov     rax, [rdx+8]
0x1800ed28c  mov     [rax], rcx
0x1800ed28f  mov     [rcx+8], rax
0x1800ed293  mov     rcx, rbx; lpCriticalSection
0x1800ed296  call    cs:__imp_LeaveCriticalSection
0x1800ed29d  nop     dword ptr [rax+rax+00h]
0x1800ed2a2  lea     r12, [rsi+508h]
0x1800ed2a9  mov     rcx, r12; lpCriticalSection
0x1800ed2ac  call    cs:__imp_EnterCriticalSection
0x1800ed2b3  nop     dword ptr [rax+rax+00h]
0x1800ed2b8  mov     [rbp+arg_0], r13
0x1800ed2bc  mov     dword ptr [rbp+arg_8], r13d
0x1800ed2c0  test    r15, r15
0x1800ed2c3  jz      loc_1800ED96F
0x1800ed2c9  mov     rcx, [rsi+308h]
0x1800ed2d0  lea     rdx, [rbp+arg_0]
0x1800ed2d4  mov     rax, [rcx]
0x1800ed2d7  mov     rax, [rax+30h]
0x1800ed2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed2e0  mov     edi, eax
0x1800ed2e2  test    eax, eax
0x1800ed2e4  js      loc_1800ED8DA
0x1800ed2ea  mov     r8, [r15+20h]
0x1800ed2ee  mov     r14b, r13b
0x1800ed2f1  test    r8, r8
0x1800ed2f4  jz      short loc_1800ED328
0x1800ed2f6  mov     rcx, [rsi+308h]
0x1800ed2fd  lea     rdx, [rbp+ppAsyncResult]
0x1800ed301  mov     [rbp+ppAsyncResult], r13
0x1800ed305  xor     r9d, r9d
0x1800ed308  mov     [rsp+30h+var_10], rdx
0x1800ed30d  xor     edx, edx
0x1800ed30f  mov     rax, [rcx]
0x1800ed312  mov     rax, [rax+78h]
0x1800ed316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed31b  mov     edi, eax
0x1800ed31d  test    eax, eax
0x1800ed31f  js      loc_1800ED49F
0x1800ed325  mov     r14b, 1
0x1800ed328  mov     rcx, [rsi+308h]
0x1800ed32f  lea     r9, [rbp+arg_8]
0x1800ed333  mov     r8d, [r15+30h]
0x1800ed337  mov     rdx, [r15+28h]
0x1800ed33b  mov     rax, [rcx]
0x1800ed33e  mov     rax, [rax+60h]
0x1800ed342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed347  mov     edi, eax
0x1800ed349  test    eax, eax
0x1800ed34b  js      loc_1800ED845
0x1800ed351  mov     eax, dword ptr [rbp+arg_8]
0x1800ed354  mov     rdx, [r15+38h]; pCallback
0x1800ed358  mov     [r15+34h], eax
0x1800ed35c  mov     rax, [r15+20h]
0x1800ed360  test    rax, rax
0x1800ed363  cmovz   rax, [rbp+arg_0]
0x1800ed368  mov     [r15+18h], rax
0x1800ed36c  test    rdx, rdx
0x1800ed36f  jz      short loc_1800ED3C5
0x1800ed371  mov     rcx, [rsi+308h]; punkObject
0x1800ed378  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800ed37c  mov     r8, r15; punkState
0x1800ed37f  mov     [rbp+ppAsyncResult], r13
0x1800ed383  call    cs:__imp_MFCreateAsyncResult
0x1800ed38a  nop     dword ptr [rax+rax+00h]
0x1800ed38f  mov     edi, eax
0x1800ed391  test    eax, eax
0x1800ed393  js      loc_1800ED5EC
0x1800ed399  mov     rcx, [r15+38h]
0x1800ed39d  mov     rdx, [rbp+ppAsyncResult]
0x1800ed3a1  mov     rax, [rcx]
0x1800ed3a4  mov     rax, [rax+20h]
0x1800ed3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3ad  mov     edi, eax
0x1800ed3af  test    eax, eax
0x1800ed3b1  js      loc_1800ED534
0x1800ed3b7  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800ed3bb  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ed3c0  mov     eax, dword ptr [rbp+arg_8]
0x1800ed3c3  jmp     short loc_1800ED3D2
0x1800ed3c5  mov     eax, dword ptr [rbp+arg_8]
0x1800ed3c8  cmp     eax, [r15+30h]
0x1800ed3cc  jnz     loc_1800ED7AB
0x1800ed3d2  test    r14b, r14b
0x1800ed3d5  jz      loc_1800ED467
0x1800ed3db  mov     r8, [rbp+arg_0]
0x1800ed3df  mov     [rbp+ppAsyncResult], r13
0x1800ed3e3  cmp     [r15+20h], r8
0x1800ed3e7  ja      short loc_1800ED43C
0x1800ed3e9  add     rax, [r15+20h]
0x1800ed3ed  cmp     rax, r8
0x1800ed3f0  jbe     short loc_1800ED43C
0x1800ed3f2  cmp     cs:byte_1801BA10A, 8
0x1800ed3f9  jb      short loc_1800ED417
0x1800ed3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed402  lea     r8, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids
0x1800ed409  mov     edx, 0B5h
0x1800ed40e  mov     rcx, [rcx+60h]
0x1800ed412  call    WPP_SF_
0x1800ed417  mov     rcx, [rsi+308h]
0x1800ed41e  lea     rdx, [rbp+arg_0]
0x1800ed422  mov     rax, [rcx]
0x1800ed425  mov     rax, [rax+20h]
0x1800ed429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed42e  mov     edi, eax
0x1800ed430  test    eax, eax
0x1800ed432  js      loc_1800ED681
0x1800ed438  mov     r8, [rbp+arg_0]
0x1800ed43c  mov     rcx, [rsi+308h]
0x1800ed443  lea     rdx, [rbp+ppAsyncResult]
0x1800ed447  mov     [rsp+30h+var_10], rdx
0x1800ed44c  xor     r9d, r9d
0x1800ed44f  xor     edx, edx
0x1800ed451  mov     rax, [rcx]
0x1800ed454  mov     rax, [rax+78h]
0x1800ed458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed45d  mov     edi, eax
0x1800ed45f  test    eax, eax
0x1800ed461  js      loc_1800ED716
0x1800ed467  mov     rcx, [r15+28h]; Block
0x1800ed46b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ed470  mov     rcx, r15; this
0x1800ed473  mov     [r15+28h], r13
0x1800ed477  call    ??_GByteStreamQueueEntry@CAVIMediaSink@@QEAAPEAXI@Z; CAVIMediaSink::ByteStreamQueueEntry::`scalar deleting destructor'(uint)
0x1800ed47c  mov     rcx, rbx; lpCriticalSection
0x1800ed47f  call    cs:__imp_EnterCriticalSection
0x1800ed486  nop     dword ptr [rax+rax+00h]
0x1800ed48b  mov     rcx, r12; lpCriticalSection
0x1800ed48e  call    cs:__imp_LeaveCriticalSection
0x1800ed495  nop     dword ptr [rax+rax+00h]
0x1800ed49a  jmp     loc_1800ED261
0x1800ed49f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed4a6  test    rcx, rcx
0x1800ed4a9  jnz     short loc_1800ED4F2
0x1800ed4ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed4b2  nop     dword ptr [rax+rax+00h]
0x1800ed4b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed4be  mov     rcx, rax
0x1800ed4c1  test    rax, rax
0x1800ed4c4  jz      short loc_1800ED4E4
0x1800ed4c6  mov     rax, [rax]
0x1800ed4c9  mov     edx, 7F0h
0x1800ed4ce  mov     rax, [rax+8]
0x1800ed4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed4d7  test    eax, eax
0x1800ed4d9  jz      short loc_1800ED4E4
0x1800ed4db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed4e2  jmp     short loc_1800ED4F2
0x1800ed4e4  lea     rcx, qword_1801B97E0; this
0x1800ed4eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed4f2  cmp     [rcx+8], r13b
0x1800ed4f6  jz      short loc_1800ED51D
0x1800ed4f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed4fd  cmp     [rax+7CCh], edi
0x1800ed503  jz      short loc_1800ED51D
0x1800ed505  mov     r9d, edi; int
0x1800ed508  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800ed50f  mov     r8d, 541h; int
0x1800ed515  mov     rcx, rax; this
0x1800ed518  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed51d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed524  jb      loc_1800EDA1E
0x1800ed52a  mov     edx, 0B0h
0x1800ed52f  jmp     loc_1800EDA00
0x1800ed534  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed53b  test    rcx, rcx
0x1800ed53e  jnz     short loc_1800ED587
0x1800ed540  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed547  nop     dword ptr [rax+rax+00h]
0x1800ed54c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed553  mov     rcx, rax
0x1800ed556  test    rax, rax
0x1800ed559  jz      short loc_1800ED579
0x1800ed55b  mov     rax, [rax]
0x1800ed55e  mov     edx, 7F0h
0x1800ed563  mov     rax, [rax+8]
0x1800ed567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed56c  test    eax, eax
0x1800ed56e  jz      short loc_1800ED579
0x1800ed570  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed577  jmp     short loc_1800ED587
0x1800ed579  lea     rcx, qword_1801B97E0; this
0x1800ed580  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed587  cmp     [rcx+8], r13b
0x1800ed58b  jz      short loc_1800ED5B2
0x1800ed58d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed592  cmp     [rax+7CCh], edi
0x1800ed598  jz      short loc_1800ED5B2
0x1800ed59a  mov     r9d, edi; int
0x1800ed59d  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800ed5a4  mov     r8d, 551h; int
0x1800ed5aa  mov     rcx, rax; this
0x1800ed5ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed5b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed5b9  jb      short loc_1800ED5DE
0x1800ed5bb  mov     edx, 0B3h
0x1800ed5c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed5c7  lea     r8, WPP_fb46bf01c505322dd09fb1a1691febf9_Traceguids
0x1800ed5ce  mov     r9, rsi
0x1800ed5d1  mov     dword ptr [rsp+30h+var_10], edi
0x1800ed5d5  mov     rcx, [rcx+10h]
0x1800ed5d9  call    WPP_SF_qD
0x1800ed5de  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800ed5e2  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ed5e7  jmp     loc_1800EDA1E
0x1800ed5ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed5f3  test    rcx, rcx
0x1800ed5f6  jnz     short loc_1800ED63F
0x1800ed5f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed5ff  nop     dword ptr [rax+rax+00h]
0x1800ed604  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed60b  mov     rcx, rax
0x1800ed60e  test    rax, rax
0x1800ed611  jz      short loc_1800ED631
0x1800ed613  mov     rax, [rax]
0x1800ed616  mov     edx, 7F0h
0x1800ed61b  mov     rax, [rax+8]
0x1800ed61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed624  test    eax, eax
0x1800ed626  jz      short loc_1800ED631
0x1800ed628  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed62f  jmp     short loc_1800ED63F
0x1800ed631  lea     rcx, qword_1801B97E0; this
0x1800ed638  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed63f  cmp     [rcx+8], r13b
0x1800ed643  jz      short loc_1800ED66A
0x1800ed645  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed64a  cmp     [rax+7CCh], edi
0x1800ed650  jz      short loc_1800ED66A
0x1800ed652  mov     r9d, edi; int
0x1800ed655  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800ed65c  mov     r8d, 550h; int
0x1800ed662  mov     rcx, rax; this
0x1800ed665  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed66a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed671  jb      loc_1800ED5DE
0x1800ed677  mov     edx, 0B2h
0x1800ed67c  jmp     loc_1800ED5C0
0x1800ed681  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed688  test    rcx, rcx
0x1800ed68b  jnz     short loc_1800ED6D4
0x1800ed68d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed694  nop     dword ptr [rax+rax+00h]
0x1800ed699  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed6a0  mov     rcx, rax
0x1800ed6a3  test    rax, rax
0x1800ed6a6  jz      short loc_1800ED6C6
0x1800ed6a8  mov     rax, [rax]
0x1800ed6ab  mov     edx, 7F0h
0x1800ed6b0  mov     rax, [rax+8]
0x1800ed6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed6b9  test    eax, eax
0x1800ed6bb  jz      short loc_1800ED6C6
0x1800ed6bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed6c4  jmp     short loc_1800ED6D4
0x1800ed6c6  lea     rcx, qword_1801B97E0; this
0x1800ed6cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed6d4  cmp     [rcx+8], r13b
0x1800ed6d8  jz      short loc_1800ED6FF
0x1800ed6da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed6df  cmp     [rax+7CCh], edi
0x1800ed6e5  jz      short loc_1800ED6FF
0x1800ed6e7  mov     r9d, edi; int
0x1800ed6ea  lea     rdx, aCavimediasinkO_2; "CAVIMediaSink::OnByteStreamWritingCompl"...
0x1800ed6f1  mov     r8d, 560h; int
0x1800ed6f7  mov     rcx, rax; this
0x1800ed6fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed6ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed706  jb      loc_1800EDA1E
0x1800ed70c  mov     edx, 0B6h
  ... truncated ...
```
