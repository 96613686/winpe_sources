# CAC3StreamSink::ProcessSample(IMFSample *)

- ea: `0x1800d3650`
- end: `0x1800d400d`
- name: `?ProcessSample@CAC3StreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `2493`
- prototype: `__int64 __fastcall(CAC3StreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18004720c`
- `0x180058af4`
- `0x180079680`
- `0x1800cf8a8`
- `0x1800d3650`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d3fe4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d3fe4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d36a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d36a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d36cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d378d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3995`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3afa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3b8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3c1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3cad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3d48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3dd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3e6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3f4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d36cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d378d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3995`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3afa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3b8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3c1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3cad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3d48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3dd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3e6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d3f4a`

## string_xrefs

- `0x1800d366b`: `CAC3StreamSink::ProcessSample`
- `0x1800d3abf`: `CAC3StreamSink::ProcessSample`
- `0x1800d3b53`: `CAC3StreamSink::ProcessSample`
- `0x1800d3be4`: `CAC3StreamSink::ProcessSample`
- `0x1800d3c75`: `CAC3StreamSink::ProcessSample`
- `0x1800d3d07`: `CAC3StreamSink::ProcessSample`
- `0x1800d3da1`: `CAC3StreamSink::ProcessSample`
- `0x1800d3e32`: `CAC3StreamSink::ProcessSample`
- `0x1800d3ec3`: `CAC3StreamSink::ProcessSample`
- `0x1800d3fa3`: `CAC3StreamSink::ProcessSample`

## pseudocode

```c
__int64 __fastcall CAC3StreamSink::ProcessSample(struct _RTL_CRITICAL_SECTION *this, struct IMFSample *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // edi
  wchar_t *v7; // rsi
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  wchar_t *v13; // rsi
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  int v16; // r12d
  unsigned int i; // ecx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  _WORD *v25; // rcx
  int v26; // eax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  HANDLE *p_LockSemaphore; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  HANDLE LockSemaphore; // rcx
  __int64 v52; // rdx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  int v57; // [rsp+30h] [rbp-28h]
  __int64 v58; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v59[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v60; // [rsp+A0h] [rbp+48h] BYREF
  struct IMFSample *v61; // [rsp+A8h] [rbp+50h]
  unsigned int v62; // [rsp+B0h] [rbp+58h] BYREF
  unsigned int v63; // [rsp+B8h] [rbp+60h] BYREF

  v61 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CAC3StreamSink::ProcessSample", 123);
  v59[0] = 0;
  v62 = 0;
  v63 = 0;
  EnterCriticalSection(this + 10);
  v6 = CBaseStreamSink::ProcessSample((CBaseStreamSink *)this, a2);
  if ( v6 < 0 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAC3StreamSink::ProcessSample", 137, v6);
    }
    if ( g_wppLevels )
    {
      v10 = 20;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  v6 = ((__int64 (__fastcall *)(struct IMFSample *, unsigned int *))a2->lpVtbl->GetBufferCount)(a2, &v63);
  if ( v6 < 0 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
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
      if ( *((_DWORD *)v15 + 499) != v6 )
        CallStackContext::TraceFailure(v15, "CAC3StreamSink::ProcessSample", 140, v6);
    }
    if ( g_wppLevels )
    {
      v10 = 21;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  v16 = 0;
  v57 = 0;
  for ( i = 0; ; i = v60 + 1 )
  {
    v60 = i;
    if ( i >= v63 )
      break;
    v58 = 0;
    v6 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))v61->lpVtbl->GetBufferByIndex)(v61, i, &v58);
    if ( v6 < 0 )
    {
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
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
        if ( *((_DWORD *)v50 + 499) != v6 )
          CallStackContext::TraceFailure(v50, "CAC3StreamSink::ProcessSample", 147, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_133;
      v28 = 22;
      goto LABEL_131;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, unsigned int *))(*(_QWORD *)v58 + 24LL))(
           v58,
           v59,
           0,
           &v62);
    if ( v6 < 0 )
    {
      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
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
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != v6 )
          CallStackContext::TraceFailure(v47, "CAC3StreamSink::ProcessSample", 150, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_133;
      v28 = 23;
      goto LABEL_131;
    }
    v20 = v62;
    if ( !v60 && v62 && *(_BYTE *)v59[0] == 119 )
    {
      v57 = 1;
      if ( (unsigned int)CAC3StreamSink::AllBuffersHaveEvenNumberBytes((CAC3StreamSink *)&this[-1].LockSemaphore, v61) )
      {
        v20 = v62;
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v58 + 32LL))(v58);
        if ( v6 < 0 )
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
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
              CallStackContext::TraceFailure(v38, "CAC3StreamSink::ProcessSample", 167, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_133;
          v28 = 24;
          goto LABEL_131;
        }
        ComSmartPtr<IMFMediaBuffer>::operator=(&v58, 0);
        v6 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))v61->lpVtbl->ConvertToContiguousBuffer)(v61, &v58);
        if ( v6 < 0 )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != v6 )
              CallStackContext::TraceFailure(v35, "CAC3StreamSink::ProcessSample", 170, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_133;
          v28 = 25;
          goto LABEL_131;
        }
        v63 = 1;
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, unsigned int *))(*(_QWORD *)v58 + 24LL))(
               v58,
               v59,
               0,
               &v62);
        if ( v6 < 0 )
        {
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
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
            if ( *((_DWORD *)v32 + 499) != v6 )
              CallStackContext::TraceFailure(v32, "CAC3StreamSink::ProcessSample", 173, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_133;
          v28 = 26;
          goto LABEL_131;
        }
        v20 = v62;
        if ( (v62 & 1) != 0 )
        {
          if ( (unsigned __int8)byte_1801BA10C >= 4u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              27,
              WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
              &this[-1].LockSemaphore,
              v62);
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          v6 = -1072875842;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v27 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v27, "CAC3StreamSink::ProcessSample", 180, -1072875842);
          }
          if ( g_wppLevels )
          {
            v28 = 28;
            p_LockSemaphore = &this[-1].LockSemaphore;
            goto LABEL_132;
          }
          goto LABEL_133;
        }
      }
    }
    else if ( !v57 )
    {
      goto LABEL_46;
    }
    v25 = (_WORD *)v59[0];
    if ( (unsigned int)v20 >= 2 )
    {
      do
      {
        LODWORD(v20) = v20 - 2;
        *v25 = __ROR2__(*v25, 8);
        ++v25;
      }
      while ( (unsigned int)v20 >= 2 );
      v20 = v62;
    }
LABEL_46:
    if ( !this[9].LockSemaphore && (_DWORD)v20 )
    {
      v26 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, __int64, HANDLE *, __int64))(*(_QWORD *)this[9].OwningThread
                                                                                  + 104LL))(
              this[9].OwningThread,
              v59[0],
              v20,
              &this[8].LockSemaphore,
              v58);
      v20 = v62;
      v16 = v26;
    }
    if ( v16 < 0 || this[9].LockSemaphore )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v58 + 32LL))(v58, v19, v20);
      if ( v6 < 0 )
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != v6 )
            CallStackContext::TraceFailure(v44, "CAC3StreamSink::ProcessSample", 213, v6);
        }
        if ( !g_wppLevels )
          goto LABEL_133;
        v28 = 29;
LABEL_131:
        p_LockSemaphore = &this[-1].LockSemaphore;
LABEL_132:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v28,
          WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
          p_LockSemaphore,
          v6);
LABEL_133:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v58);
        break;
      }
      LODWORD(v20) = v62;
    }
    v6 = v16;
    this[11].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)this[11].DebugInfo + (unsigned int)v20);
    if ( v16 < 0 )
    {
      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
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
        if ( *((_DWORD *)v41 + 499) != v16 )
          CallStackContext::TraceFailure(v41, "CAC3StreamSink::ProcessSample", 219, v16);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
          &this[-1].LockSemaphore,
          v16);
      goto LABEL_133;
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v58);
  }
  LockSemaphore = this[9].LockSemaphore;
  if ( LockSemaphore )
  {
    v6 = (*(__int64 (__fastcall **)(HANDLE, struct IMFSample *, ULONG_PTR *, struct IMFSample *))(*(_QWORD *)LockSemaphore
                                                                                                + 24LL))(
           LockSemaphore,
           v61,
           &this[8].SpinCount,
           v61);
    if ( v6 < 0 )
    {
      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
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
        if ( *((_DWORD *)v55 + 499) != v6 )
          CallStackContext::TraceFailure(v55, "CAC3StreamSink::ProcessSample", 225, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 31;
LABEL_146:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
          &this[-1].LockSemaphore,
          v6);
      }
    }
  }
LABEL_147:
  LeaveCriticalSection(this + 10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d3650  mov     [rsp-40h+arg_8], rdx
0x1800d3655  push    rbp
0x1800d3656  push    rbx
0x1800d3657  push    rsi
0x1800d3658  push    rdi
0x1800d3659  push    r12
0x1800d365b  push    r13
0x1800d365d  push    r14
0x1800d365f  push    r15
0x1800d3661  mov     rbp, rsp
0x1800d3664  sub     rsp, 58h
0x1800d3668  mov     rsi, rdx
0x1800d366b  lea     r15, aCac3streamsink_5; "CAC3StreamSink::ProcessSample"
0x1800d3672  mov     r13, rcx
0x1800d3675  mov     rdx, r15; char *
0x1800d3678  mov     r8d, 7Bh ; '{'; int
0x1800d367e  lea     rcx, [rbp+arg_0]; this
0x1800d3682  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d3687  xor     r14d, r14d
0x1800d368a  lea     rbx, [r13+190h]
0x1800d3691  mov     rcx, rbx; lpCriticalSection
0x1800d3694  mov     [rbp+var_18], r14
0x1800d3698  mov     [rbp+arg_10], r14d
0x1800d369c  mov     [rbp+arg_18], r14d
0x1800d36a0  call    cs:__imp_EnterCriticalSection
0x1800d36a7  nop     dword ptr [rax+rax+00h]
0x1800d36ac  mov     rdx, rsi; struct IMFSample *
0x1800d36af  mov     rcx, r13; this
0x1800d36b2  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x1800d36b7  mov     edi, eax
0x1800d36b9  test    eax, eax
0x1800d36bb  jns     loc_1800D3761
0x1800d36c1  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d36c8  test    rsi, rsi
0x1800d36cb  jnz     short loc_1800D3714
0x1800d36cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d36d4  nop     dword ptr [rax+rax+00h]
0x1800d36d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d36e0  mov     rcx, rax
0x1800d36e3  test    rax, rax
0x1800d36e6  jz      short loc_1800D3706
0x1800d36e8  mov     rax, [rax]
0x1800d36eb  mov     edx, 7F0h
0x1800d36f0  mov     rax, [rax+8]
0x1800d36f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d36f9  test    eax, eax
0x1800d36fb  jz      short loc_1800D3706
0x1800d36fd  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3704  jmp     short loc_1800D3714
0x1800d3706  lea     rsi, qword_1801B97E0
0x1800d370d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3714  cmp     [rsi+8], r14b
0x1800d3718  jz      short loc_1800D373E
0x1800d371a  mov     rcx, rsi; this
0x1800d371d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d3722  cmp     [rax+7CCh], edi
0x1800d3728  jz      short loc_1800D373E
0x1800d372a  mov     r9d, edi; int
0x1800d372d  mov     r8d, 89h; int
0x1800d3733  mov     rdx, r15; char *
0x1800d3736  mov     rcx, rax; this
0x1800d3739  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d373e  mov     r14d, 1
0x1800d3744  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d374b  jb      loc_1800D3FE1
0x1800d3751  lea     edx, [r14+13h]
0x1800d3755  lea     r8, WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids
0x1800d375c  jmp     loc_1800D3FC9
0x1800d3761  mov     rax, [rsi]
0x1800d3764  lea     rdx, [rbp+arg_18]
0x1800d3768  mov     rcx, rsi
0x1800d376b  mov     rax, [rax+138h]
0x1800d3772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3777  mov     edi, eax
0x1800d3779  test    eax, eax
0x1800d377b  jns     loc_1800D381A
0x1800d3781  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3788  test    rsi, rsi
0x1800d378b  jnz     short loc_1800D37D4
0x1800d378d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d3794  nop     dword ptr [rax+rax+00h]
0x1800d3799  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d37a0  mov     rcx, rax
0x1800d37a3  test    rax, rax
0x1800d37a6  jz      short loc_1800D37C6
0x1800d37a8  mov     rax, [rax]
0x1800d37ab  mov     edx, 7F0h
0x1800d37b0  mov     rax, [rax+8]
0x1800d37b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d37b9  test    eax, eax
0x1800d37bb  jz      short loc_1800D37C6
0x1800d37bd  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d37c4  jmp     short loc_1800D37D4
0x1800d37c6  lea     rsi, qword_1801B97E0
0x1800d37cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d37d4  cmp     [rsi+8], r14b
0x1800d37d8  jz      short loc_1800D37FE
0x1800d37da  mov     rcx, rsi; this
0x1800d37dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d37e2  cmp     [rax+7CCh], edi
0x1800d37e8  jz      short loc_1800D37FE
0x1800d37ea  mov     r9d, edi; int
0x1800d37ed  mov     r8d, 8Ch; int
0x1800d37f3  mov     rdx, r15; char *
0x1800d37f6  mov     rcx, rax; this
0x1800d37f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d37fe  mov     r14d, 1
0x1800d3804  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d380b  jb      loc_1800D3FE1
0x1800d3811  lea     edx, [r14+14h]
0x1800d3815  jmp     loc_1800D3755
0x1800d381a  mov     r12d, r14d
0x1800d381d  mov     [rbp+var_28], r14d
0x1800d3821  mov     ecx, r14d
0x1800d3824  mov     r14d, 1
0x1800d382a  lea     rsi, qword_1801B97E0
0x1800d3831  mov     [rbp+arg_0], ecx
0x1800d3834  lea     r15, WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids
0x1800d383b  cmp     ecx, [rbp+arg_18]
0x1800d383e  jnb     loc_1800D3F0A
0x1800d3844  mov     r9, [rbp+arg_8]
0x1800d3848  lea     r8, [rbp+var_20]
0x1800d384c  mov     edx, ecx
0x1800d384e  mov     [rbp+var_20], 0
0x1800d3856  mov     rcx, r9
0x1800d3859  mov     rax, [r9]
0x1800d385c  mov     rax, [rax+140h]
0x1800d3863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3868  mov     edi, eax
0x1800d386a  test    eax, eax
0x1800d386c  js      loc_1800D3E5E
0x1800d3872  mov     rcx, [rbp+var_20]
0x1800d3876  lea     r9, [rbp+arg_10]
0x1800d387a  xor     r8d, r8d
0x1800d387d  lea     rdx, [rbp+var_18]
0x1800d3881  mov     rax, [rcx]
0x1800d3884  mov     rax, [rax+18h]
0x1800d3888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d388d  mov     edi, eax
0x1800d388f  test    eax, eax
0x1800d3891  js      loc_1800D3DCD
0x1800d3897  cmp     [rbp+arg_0], 0
0x1800d389b  mov     r8d, [rbp+arg_10]
0x1800d389f  jnz     loc_1800D39DF
0x1800d38a5  test    r8d, r8d
0x1800d38a8  jz      loc_1800D39DF
0x1800d38ae  mov     rax, [rbp+var_18]
0x1800d38b2  cmp     byte ptr [rax], 77h ; 'w'
0x1800d38b5  jnz     loc_1800D39DF
0x1800d38bb  mov     rdx, [rbp+arg_8]; struct IMFSample *
0x1800d38bf  lea     rcx, [r13-10h]; this
0x1800d38c3  mov     [rbp+var_28], r14d
0x1800d38c7  call    ?AllBuffersHaveEvenNumberBytes@CAC3StreamSink@@AEAAHPEAUIMFSample@@@Z; CAC3StreamSink::AllBuffersHaveEvenNumberBytes(IMFSample *)
0x1800d38cc  test    eax, eax
0x1800d38ce  jnz     loc_1800D39D9
0x1800d38d4  mov     rcx, [rbp+var_20]
0x1800d38d8  mov     rax, [rcx]
0x1800d38db  mov     rax, [rax+20h]
0x1800d38df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d38e4  mov     edi, eax
0x1800d38e6  test    eax, eax
0x1800d38e8  js      loc_1800D3C10
0x1800d38ee  xor     edx, edx
0x1800d38f0  lea     rcx, [rbp+var_20]
0x1800d38f4  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@PEAU1@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(IMFMediaBuffer *)
0x1800d38f9  mov     rcx, [rbp+arg_8]
0x1800d38fd  lea     rdx, [rbp+var_20]
0x1800d3901  mov     rax, [rcx]
0x1800d3904  mov     rax, [rax+148h]
0x1800d390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3910  mov     edi, eax
0x1800d3912  test    eax, eax
0x1800d3914  js      loc_1800D3B7F
0x1800d391a  mov     rcx, [rbp+var_20]
0x1800d391e  lea     r9, [rbp+arg_10]
0x1800d3922  mov     [rbp+arg_18], r14d
0x1800d3926  lea     rdx, [rbp+var_18]
0x1800d392a  xor     r8d, r8d
0x1800d392d  mov     rax, [rcx]
0x1800d3930  mov     rax, [rax+18h]
0x1800d3934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3939  mov     edi, eax
0x1800d393b  test    eax, eax
0x1800d393d  js      loc_1800D3AEE
0x1800d3943  mov     r8d, [rbp+arg_10]
0x1800d3947  test    r14b, r8b
0x1800d394a  jz      loc_1800D39E5
0x1800d3950  cmp     cs:byte_1801BA10C, 4
0x1800d3957  lea     r12, [r13-10h]
0x1800d395b  jb      short loc_1800D3980
0x1800d395d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3964  mov     edx, 1Bh
0x1800d3969  mov     dword ptr [rsp+58h+var_38], r8d
0x1800d396e  mov     r9, r12
0x1800d3971  mov     r8, r15
0x1800d3974  mov     rcx, [rcx+0B0h]
0x1800d397b  call    WPP_SF_qD
0x1800d3980  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3987  mov     edi, 0C00D36BEh
0x1800d398c  test    rcx, rcx
0x1800d398f  jnz     loc_1800D3AA9
0x1800d3995  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d399c  nop     dword ptr [rax+rax+00h]
0x1800d39a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d39a8  mov     rcx, rax
0x1800d39ab  test    rax, rax
0x1800d39ae  jz      loc_1800D3A9F
0x1800d39b4  mov     rax, [rax]
0x1800d39b7  mov     edx, 7F0h
0x1800d39bc  mov     rax, [rax+8]
0x1800d39c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d39c5  test    eax, eax
0x1800d39c7  jz      loc_1800D3A9F
0x1800d39cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d39d4  jmp     loc_1800D3AA9
0x1800d39d9  mov     r8d, [rbp+arg_10]
0x1800d39dd  jmp     short loc_1800D39E5
0x1800d39df  cmp     [rbp+var_28], 0
0x1800d39e3  jz      short loc_1800D3A0B
0x1800d39e5  mov     rcx, [rbp+var_18]
0x1800d39e9  cmp     r8d, 2
0x1800d39ed  jb      short loc_1800D3A0B
0x1800d39ef  movzx   eax, word ptr [rcx]
0x1800d39f2  add     r8d, 0FFFFFFFEh
0x1800d39f6  ror     ax, 8
0x1800d39fa  mov     [rcx], ax
0x1800d39fd  lea     rcx, [rcx+2]
0x1800d3a01  cmp     r8d, 2
0x1800d3a05  jnb     short loc_1800D39EF
0x1800d3a07  mov     r8d, [rbp+arg_10]
0x1800d3a0b  cmp     qword ptr [r13+180h], 0
0x1800d3a13  jnz     short loc_1800D3A48
0x1800d3a15  test    r8d, r8d
0x1800d3a18  jz      short loc_1800D3A48
0x1800d3a1a  mov     rcx, [r13+178h]
0x1800d3a21  lea     r9, [r13+158h]
0x1800d3a28  mov     r10, [rbp+var_20]
0x1800d3a2c  mov     rdx, [rbp+var_18]
0x1800d3a30  mov     [rsp+58h+var_38], r10
0x1800d3a35  mov     rax, [rcx]
0x1800d3a38  mov     rax, [rax+68h]
0x1800d3a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3a41  mov     r8d, [rbp+arg_10]
0x1800d3a45  mov     r12d, eax
0x1800d3a48  test    r12d, r12d
0x1800d3a4b  js      short loc_1800D3A57
0x1800d3a4d  cmp     qword ptr [r13+180h], 0
0x1800d3a55  jz      short loc_1800D3A75
0x1800d3a57  mov     rcx, [rbp+var_20]
0x1800d3a5b  mov     rax, [rcx]
0x1800d3a5e  mov     rax, [rax+20h]
0x1800d3a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3a67  mov     edi, eax
0x1800d3a69  test    eax, eax
0x1800d3a6b  js      loc_1800D3D3C
0x1800d3a71  mov     r8d, [rbp+arg_10]
0x1800d3a75  mov     eax, r8d
0x1800d3a78  mov     edi, r12d
0x1800d3a7b  add     [r13+1B8h], rax
0x1800d3a82  test    r12d, r12d
0x1800d3a85  js      loc_1800D3CA1
0x1800d3a8b  lea     rcx, [rbp+var_20]; void *
0x1800d3a8f  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800d3a94  mov     ecx, [rbp+arg_0]
0x1800d3a97  add     ecx, r14d
0x1800d3a9a  jmp     loc_1800D382A
0x1800d3a9f  mov     rcx, rsi; this
0x1800d3aa2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3aa9  cmp     byte ptr [rcx+8], 0
0x1800d3aad  jz      short loc_1800D3AD4
0x1800d3aaf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d3ab4  cmp     [rax+7CCh], edi
0x1800d3aba  jz      short loc_1800D3AD4
0x1800d3abc  mov     r9d, edi; int
0x1800d3abf  lea     rdx, aCac3streamsink_5; "CAC3StreamSink::ProcessSample"
0x1800d3ac6  mov     r8d, 0B4h; int
0x1800d3acc  mov     rcx, rax; this
0x1800d3acf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d3ad4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d3adb  jb      loc_1800D3F01
0x1800d3ae1  mov     edx, 1Ch
0x1800d3ae6  mov     r9, r12
0x1800d3ae9  jmp     loc_1800D3EEA
0x1800d3aee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3af5  test    rcx, rcx
0x1800d3af8  jnz     short loc_1800D3B3D
0x1800d3afa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d3b01  nop     dword ptr [rax+rax+00h]
0x1800d3b06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3b0d  mov     rcx, rax
0x1800d3b10  test    rax, rax
0x1800d3b13  jz      short loc_1800D3B33
0x1800d3b15  mov     rax, [rax]
0x1800d3b18  mov     edx, 7F0h
0x1800d3b1d  mov     rax, [rax+8]
0x1800d3b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3b26  test    eax, eax
0x1800d3b28  jz      short loc_1800D3B33
0x1800d3b2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d3b31  jmp     short loc_1800D3B3D
  ... truncated ...
```
