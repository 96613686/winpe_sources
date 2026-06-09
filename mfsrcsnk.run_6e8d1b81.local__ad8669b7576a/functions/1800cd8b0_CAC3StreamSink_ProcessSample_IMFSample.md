# CAC3StreamSink::ProcessSample(IMFSample *)

- ea: `0x1800cd8b0`
- end: `0x1800ce21e`
- name: `?ProcessSample@CAC3StreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `2414`
- prototype: `__int64 __fastcall(CAC3StreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180043c9c`
- `0x180055890`
- `0x180073b14`
- `0x1800c9cf8`
- `0x1800cd8b0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce1fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce1fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd900`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd900`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cd927`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cd9e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdbe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdd42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cddcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cde58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdee3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdf78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce003`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce08e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce168`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cd927`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cd9e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdbe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdd42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cddcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cde58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdee3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdf78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce003`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce08e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce168`

## string_xrefs

- `0x1800cd8cb`: `CAC3StreamSink::ProcessSample`
- `0x1800cdd07`: `CAC3StreamSink::ProcessSample`
- `0x1800cdd95`: `CAC3StreamSink::ProcessSample`
- `0x1800cde20`: `CAC3StreamSink::ProcessSample`
- `0x1800cdeab`: `CAC3StreamSink::ProcessSample`
- `0x1800cdf37`: `CAC3StreamSink::ProcessSample`
- `0x1800cdfcb`: `CAC3StreamSink::ProcessSample`
- `0x1800ce056`: `CAC3StreamSink::ProcessSample`
- `0x1800ce0e1`: `CAC3StreamSink::ProcessSample`
- `0x1800ce1bb`: `CAC3StreamSink::ProcessSample`

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
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v48 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v45 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v36 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v33 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v30 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          if ( (unsigned __int8)byte_1801B110C >= 4u )
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
              v23 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v42 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v39 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v53 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800cd8b0  mov     [rsp-40h+arg_8], rdx
0x1800cd8b5  push    rbp
0x1800cd8b6  push    rbx
0x1800cd8b7  push    rsi
0x1800cd8b8  push    rdi
0x1800cd8b9  push    r12
0x1800cd8bb  push    r13
0x1800cd8bd  push    r14
0x1800cd8bf  push    r15
0x1800cd8c1  mov     rbp, rsp
0x1800cd8c4  sub     rsp, 58h
0x1800cd8c8  mov     rsi, rdx
0x1800cd8cb  lea     r15, aCac3streamsink_5; "CAC3StreamSink::ProcessSample"
0x1800cd8d2  mov     r13, rcx
0x1800cd8d5  mov     rdx, r15; char *
0x1800cd8d8  mov     r8d, 7Bh ; '{'; int
0x1800cd8de  lea     rcx, [rbp+arg_0]; this
0x1800cd8e2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cd8e7  xor     r14d, r14d
0x1800cd8ea  lea     rbx, [r13+190h]
0x1800cd8f1  mov     rcx, rbx; lpCriticalSection
0x1800cd8f4  mov     [rbp+var_18], r14
0x1800cd8f8  mov     [rbp+arg_10], r14d
0x1800cd8fc  mov     [rbp+arg_18], r14d
0x1800cd900  call    cs:__imp_EnterCriticalSection
0x1800cd906  mov     rdx, rsi; struct IMFSample *
0x1800cd909  mov     rcx, r13; this
0x1800cd90c  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x1800cd911  mov     edi, eax
0x1800cd913  test    eax, eax
0x1800cd915  jns     loc_1800CD9B5
0x1800cd91b  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd922  test    rsi, rsi
0x1800cd925  jnz     short loc_1800CD968
0x1800cd927  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cd92d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd934  mov     rcx, rax
0x1800cd937  test    rax, rax
0x1800cd93a  jz      short loc_1800CD95A
0x1800cd93c  mov     rax, [rax]
0x1800cd93f  mov     edx, 7F0h
0x1800cd944  mov     rax, [rax+8]
0x1800cd948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd94d  test    eax, eax
0x1800cd94f  jz      short loc_1800CD95A
0x1800cd951  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd958  jmp     short loc_1800CD968
0x1800cd95a  lea     rsi, qword_1801B07E0
0x1800cd961  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd968  cmp     [rsi+8], r14b
0x1800cd96c  jz      short loc_1800CD992
0x1800cd96e  mov     rcx, rsi; this
0x1800cd971  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd976  cmp     [rax+7CCh], edi
0x1800cd97c  jz      short loc_1800CD992
0x1800cd97e  mov     r9d, edi; int
0x1800cd981  mov     r8d, 89h; int
0x1800cd987  mov     rdx, r15; char *
0x1800cd98a  mov     rcx, rax; this
0x1800cd98d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd992  mov     r14d, 1
0x1800cd998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800cd99f  jb      loc_1800CE1F9
0x1800cd9a5  lea     edx, [r14+13h]
0x1800cd9a9  lea     r8, WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids
0x1800cd9b0  jmp     loc_1800CE1E1
0x1800cd9b5  mov     rax, [rsi]
0x1800cd9b8  lea     rdx, [rbp+arg_18]
0x1800cd9bc  mov     rcx, rsi
0x1800cd9bf  mov     rax, [rax+138h]
0x1800cd9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd9cb  mov     edi, eax
0x1800cd9cd  test    eax, eax
0x1800cd9cf  jns     loc_1800CDA68
0x1800cd9d5  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd9dc  test    rsi, rsi
0x1800cd9df  jnz     short loc_1800CDA22
0x1800cd9e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cd9e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd9ee  mov     rcx, rax
0x1800cd9f1  test    rax, rax
0x1800cd9f4  jz      short loc_1800CDA14
0x1800cd9f6  mov     rax, [rax]
0x1800cd9f9  mov     edx, 7F0h
0x1800cd9fe  mov     rax, [rax+8]
0x1800cda02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cda07  test    eax, eax
0x1800cda09  jz      short loc_1800CDA14
0x1800cda0b  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cda12  jmp     short loc_1800CDA22
0x1800cda14  lea     rsi, qword_1801B07E0
0x1800cda1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cda22  cmp     [rsi+8], r14b
0x1800cda26  jz      short loc_1800CDA4C
0x1800cda28  mov     rcx, rsi; this
0x1800cda2b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cda30  cmp     [rax+7CCh], edi
0x1800cda36  jz      short loc_1800CDA4C
0x1800cda38  mov     r9d, edi; int
0x1800cda3b  mov     r8d, 8Ch; int
0x1800cda41  mov     rdx, r15; char *
0x1800cda44  mov     rcx, rax; this
0x1800cda47  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cda4c  mov     r14d, 1
0x1800cda52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800cda59  jb      loc_1800CE1F9
0x1800cda5f  lea     edx, [r14+14h]
0x1800cda63  jmp     loc_1800CD9A9
0x1800cda68  mov     r12d, r14d
0x1800cda6b  mov     [rbp+var_28], r14d
0x1800cda6f  mov     ecx, r14d
0x1800cda72  mov     r14d, 1
0x1800cda78  lea     rsi, qword_1801B07E0
0x1800cda7f  mov     [rbp+arg_0], ecx
0x1800cda82  lea     r15, WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids
0x1800cda89  cmp     ecx, [rbp+arg_18]
0x1800cda8c  jnb     loc_1800CE128
0x1800cda92  mov     r9, [rbp+arg_8]
0x1800cda96  lea     r8, [rbp+var_20]
0x1800cda9a  mov     edx, ecx
0x1800cda9c  mov     [rbp+var_20], 0
0x1800cdaa4  mov     rcx, r9
0x1800cdaa7  mov     rax, [r9]
0x1800cdaaa  mov     rax, [rax+140h]
0x1800cdab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdab6  mov     edi, eax
0x1800cdab8  test    eax, eax
0x1800cdaba  js      loc_1800CE082
0x1800cdac0  mov     rcx, [rbp+var_20]
0x1800cdac4  lea     r9, [rbp+arg_10]
0x1800cdac8  xor     r8d, r8d
0x1800cdacb  lea     rdx, [rbp+var_18]
0x1800cdacf  mov     rax, [rcx]
0x1800cdad2  mov     rax, [rax+18h]
0x1800cdad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdadb  mov     edi, eax
0x1800cdadd  test    eax, eax
0x1800cdadf  js      loc_1800CDFF7
0x1800cdae5  cmp     [rbp+arg_0], 0
0x1800cdae9  mov     r8d, [rbp+arg_10]
0x1800cdaed  jnz     loc_1800CDC27
0x1800cdaf3  test    r8d, r8d
0x1800cdaf6  jz      loc_1800CDC27
0x1800cdafc  mov     rax, [rbp+var_18]
0x1800cdb00  cmp     byte ptr [rax], 77h ; 'w'
0x1800cdb03  jnz     loc_1800CDC27
0x1800cdb09  mov     rdx, [rbp+arg_8]; struct IMFSample *
0x1800cdb0d  lea     rcx, [r13-10h]; this
0x1800cdb11  mov     [rbp+var_28], r14d
0x1800cdb15  call    ?AllBuffersHaveEvenNumberBytes@CAC3StreamSink@@AEAAHPEAUIMFSample@@@Z; CAC3StreamSink::AllBuffersHaveEvenNumberBytes(IMFSample *)
0x1800cdb1a  test    eax, eax
0x1800cdb1c  jnz     loc_1800CDC21
0x1800cdb22  mov     rcx, [rbp+var_20]
0x1800cdb26  mov     rax, [rcx]
0x1800cdb29  mov     rax, [rax+20h]
0x1800cdb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdb32  mov     edi, eax
0x1800cdb34  test    eax, eax
0x1800cdb36  js      loc_1800CDE4C
0x1800cdb3c  xor     edx, edx
0x1800cdb3e  lea     rcx, [rbp+var_20]
0x1800cdb42  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@PEAU1@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(IMFMediaBuffer *)
0x1800cdb47  mov     rcx, [rbp+arg_8]
0x1800cdb4b  lea     rdx, [rbp+var_20]
0x1800cdb4f  mov     rax, [rcx]
0x1800cdb52  mov     rax, [rax+148h]
0x1800cdb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdb5e  mov     edi, eax
0x1800cdb60  test    eax, eax
0x1800cdb62  js      loc_1800CDDC1
0x1800cdb68  mov     rcx, [rbp+var_20]
0x1800cdb6c  lea     r9, [rbp+arg_10]
0x1800cdb70  mov     [rbp+arg_18], r14d
0x1800cdb74  lea     rdx, [rbp+var_18]
0x1800cdb78  xor     r8d, r8d
0x1800cdb7b  mov     rax, [rcx]
0x1800cdb7e  mov     rax, [rax+18h]
0x1800cdb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdb87  mov     edi, eax
0x1800cdb89  test    eax, eax
0x1800cdb8b  js      loc_1800CDD36
0x1800cdb91  mov     r8d, [rbp+arg_10]
0x1800cdb95  test    r14b, r8b
0x1800cdb98  jz      loc_1800CDC2D
0x1800cdb9e  cmp     cs:byte_1801B110C, 4
0x1800cdba5  lea     r12, [r13-10h]
0x1800cdba9  jb      short loc_1800CDBCE
0x1800cdbab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdbb2  mov     edx, 1Bh
0x1800cdbb7  mov     dword ptr [rsp+58h+var_38], r8d
0x1800cdbbc  mov     r9, r12
0x1800cdbbf  mov     r8, r15
0x1800cdbc2  mov     rcx, [rcx+0B0h]
0x1800cdbc9  call    WPP_SF_qD
0x1800cdbce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdbd5  mov     edi, 0C00D36BEh
0x1800cdbda  test    rcx, rcx
0x1800cdbdd  jnz     loc_1800CDCF1
0x1800cdbe3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cdbe9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdbf0  mov     rcx, rax
0x1800cdbf3  test    rax, rax
0x1800cdbf6  jz      loc_1800CDCE7
0x1800cdbfc  mov     rax, [rax]
0x1800cdbff  mov     edx, 7F0h
0x1800cdc04  mov     rax, [rax+8]
0x1800cdc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdc0d  test    eax, eax
0x1800cdc0f  jz      loc_1800CDCE7
0x1800cdc15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdc1c  jmp     loc_1800CDCF1
0x1800cdc21  mov     r8d, [rbp+arg_10]
0x1800cdc25  jmp     short loc_1800CDC2D
0x1800cdc27  cmp     [rbp+var_28], 0
0x1800cdc2b  jz      short loc_1800CDC53
0x1800cdc2d  mov     rcx, [rbp+var_18]
0x1800cdc31  cmp     r8d, 2
0x1800cdc35  jb      short loc_1800CDC53
0x1800cdc37  movzx   eax, word ptr [rcx]
0x1800cdc3a  add     r8d, 0FFFFFFFEh
0x1800cdc3e  ror     ax, 8
0x1800cdc42  mov     [rcx], ax
0x1800cdc45  lea     rcx, [rcx+2]
0x1800cdc49  cmp     r8d, 2
0x1800cdc4d  jnb     short loc_1800CDC37
0x1800cdc4f  mov     r8d, [rbp+arg_10]
0x1800cdc53  cmp     qword ptr [r13+180h], 0
0x1800cdc5b  jnz     short loc_1800CDC90
0x1800cdc5d  test    r8d, r8d
0x1800cdc60  jz      short loc_1800CDC90
0x1800cdc62  mov     rcx, [r13+178h]
0x1800cdc69  lea     r9, [r13+158h]
0x1800cdc70  mov     r10, [rbp+var_20]
0x1800cdc74  mov     rdx, [rbp+var_18]
0x1800cdc78  mov     [rsp+58h+var_38], r10
0x1800cdc7d  mov     rax, [rcx]
0x1800cdc80  mov     rax, [rax+68h]
0x1800cdc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdc89  mov     r8d, [rbp+arg_10]
0x1800cdc8d  mov     r12d, eax
0x1800cdc90  test    r12d, r12d
0x1800cdc93  js      short loc_1800CDC9F
0x1800cdc95  cmp     qword ptr [r13+180h], 0
0x1800cdc9d  jz      short loc_1800CDCBD
0x1800cdc9f  mov     rcx, [rbp+var_20]
0x1800cdca3  mov     rax, [rcx]
0x1800cdca6  mov     rax, [rax+20h]
0x1800cdcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdcaf  mov     edi, eax
0x1800cdcb1  test    eax, eax
0x1800cdcb3  js      loc_1800CDF6C
0x1800cdcb9  mov     r8d, [rbp+arg_10]
0x1800cdcbd  mov     eax, r8d
0x1800cdcc0  mov     edi, r12d
0x1800cdcc3  add     [r13+1B8h], rax
0x1800cdcca  test    r12d, r12d
0x1800cdccd  js      loc_1800CDED7
0x1800cdcd3  lea     rcx, [rbp+var_20]; void *
0x1800cdcd7  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800cdcdc  mov     ecx, [rbp+arg_0]
0x1800cdcdf  add     ecx, r14d
0x1800cdce2  jmp     loc_1800CDA78
0x1800cdce7  mov     rcx, rsi; this
0x1800cdcea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdcf1  cmp     byte ptr [rcx+8], 0
0x1800cdcf5  jz      short loc_1800CDD1C
0x1800cdcf7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cdcfc  cmp     [rax+7CCh], edi
0x1800cdd02  jz      short loc_1800CDD1C
0x1800cdd04  mov     r9d, edi; int
0x1800cdd07  lea     rdx, aCac3streamsink_5; "CAC3StreamSink::ProcessSample"
0x1800cdd0e  mov     r8d, 0B4h; int
0x1800cdd14  mov     rcx, rax; this
0x1800cdd17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cdd1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800cdd23  jb      loc_1800CE11F
0x1800cdd29  mov     edx, 1Ch
0x1800cdd2e  mov     r9, r12
0x1800cdd31  jmp     loc_1800CE108
0x1800cdd36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd3d  test    rcx, rcx
0x1800cdd40  jnz     short loc_1800CDD7F
0x1800cdd42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cdd48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd4f  mov     rcx, rax
0x1800cdd52  test    rax, rax
0x1800cdd55  jz      short loc_1800CDD75
0x1800cdd57  mov     rax, [rax]
0x1800cdd5a  mov     edx, 7F0h
0x1800cdd5f  mov     rax, [rax+8]
0x1800cdd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdd68  test    eax, eax
0x1800cdd6a  jz      short loc_1800CDD75
0x1800cdd6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd73  jmp     short loc_1800CDD7F
0x1800cdd75  mov     rcx, rsi; this
0x1800cdd78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd7f  cmp     byte ptr [rcx+8], 0
0x1800cdd83  jz      short loc_1800CDDAA
0x1800cdd85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
