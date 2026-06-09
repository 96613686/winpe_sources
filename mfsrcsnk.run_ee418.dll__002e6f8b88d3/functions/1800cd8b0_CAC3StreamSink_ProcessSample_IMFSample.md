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
  __int64 v7; // r8
  __int64 v8; // r9
  wchar_t *v9; // rsi
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  wchar_t *v17; // rsi
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  int v20; // r12d
  unsigned int i; // ecx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  _WORD *v38; // rcx
  int v39; // eax
  __int64 v40; // r8
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  HANDLE *p_LockSemaphore; // r9
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
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  HANDLE LockSemaphore; // rcx
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  int v73; // [rsp+30h] [rbp-28h]
  __int64 v74; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v75[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v76; // [rsp+A0h] [rbp+48h] BYREF
  struct IMFSample *v77; // [rsp+A8h] [rbp+50h]
  unsigned int v78; // [rsp+B0h] [rbp+58h] BYREF
  unsigned int v79; // [rsp+B8h] [rbp+60h] BYREF

  v77 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v76, "CAC3StreamSink::ProcessSample", 123);
  v75[0] = 0;
  v78 = 0;
  v79 = 0;
  EnterCriticalSection(this + 10);
  v6 = CBaseStreamSink::ProcessSample((CBaseStreamSink *)this, a2);
  if ( v6 < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAC3StreamSink::ProcessSample", 137, v6);
    }
    if ( g_wppLevels )
    {
      v12 = 20;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  v6 = ((__int64 (__fastcall *)(struct IMFSample *, unsigned int *))a2->lpVtbl->GetBufferCount)(a2, &v79);
  if ( v6 < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13, v15, v16);
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
      if ( *((_DWORD *)v19 + 499) != v6 )
        CallStackContext::TraceFailure(v19, "CAC3StreamSink::ProcessSample", 140, v6);
    }
    if ( g_wppLevels )
    {
      v12 = 21;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  v20 = 0;
  v73 = 0;
  for ( i = 0; ; i = v76 + 1 )
  {
    v76 = i;
    if ( i >= v79 )
      break;
    v74 = 0;
    v6 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))v77->lpVtbl->GetBufferByIndex)(v77, i, &v74);
    if ( v6 < 0 )
    {
      v62 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
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
        if ( *((_DWORD *)v64 + 499) != v6 )
          CallStackContext::TraceFailure(v64, "CAC3StreamSink::ProcessSample", 147, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_133;
      v42 = 22;
      goto LABEL_131;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, unsigned int *))(*(_QWORD *)v74 + 24LL))(
           v74,
           v75,
           0,
           &v78);
    if ( v6 < 0 )
    {
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
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
        if ( *((_DWORD *)v61 + 499) != v6 )
          CallStackContext::TraceFailure(v61, "CAC3StreamSink::ProcessSample", 150, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_133;
      v42 = 23;
      goto LABEL_131;
    }
    v28 = v78;
    if ( !v76 && v78 && *(_BYTE *)v75[0] == 119 )
    {
      v73 = 1;
      if ( (unsigned int)CAC3StreamSink::AllBuffersHaveEvenNumberBytes((CAC3StreamSink *)&this[-1].LockSemaphore, v77) )
      {
        v28 = v78;
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 32LL))(v74);
        if ( v6 < 0 )
        {
          v50 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
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
            if ( *((_DWORD *)v52 + 499) != v6 )
              CallStackContext::TraceFailure(v52, "CAC3StreamSink::ProcessSample", 167, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_133;
          v42 = 24;
          goto LABEL_131;
        }
        ComSmartPtr<IMFMediaBuffer>::operator=(&v74, 0);
        v6 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))v77->lpVtbl->ConvertToContiguousBuffer)(v77, &v74);
        if ( v6 < 0 )
        {
          v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
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
            if ( *((_DWORD *)v49 + 499) != v6 )
              CallStackContext::TraceFailure(v49, "CAC3StreamSink::ProcessSample", 170, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_133;
          v42 = 25;
          goto LABEL_131;
        }
        v79 = 1;
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, unsigned int *))(*(_QWORD *)v74 + 24LL))(
               v74,
               v75,
               0,
               &v78);
        if ( v6 < 0 )
        {
          v44 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v35, v27);
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
            if ( *((_DWORD *)v46 + 499) != v6 )
              CallStackContext::TraceFailure(v46, "CAC3StreamSink::ProcessSample", 173, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_133;
          v42 = 26;
          goto LABEL_131;
        }
        v28 = v78;
        if ( (v78 & 1) != 0 )
        {
          if ( (unsigned __int8)byte_1801B110C >= 4u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              27,
              &WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
              &this[-1].LockSemaphore,
              v78);
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          v6 = -1072875842;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v28, v27);
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
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v41 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v41, "CAC3StreamSink::ProcessSample", 180, -1072875842);
          }
          if ( g_wppLevels )
          {
            v42 = 28;
            p_LockSemaphore = &this[-1].LockSemaphore;
            goto LABEL_132;
          }
          goto LABEL_133;
        }
      }
    }
    else if ( !v73 )
    {
      goto LABEL_46;
    }
    v38 = (_WORD *)v75[0];
    if ( (unsigned int)v28 >= 2 )
    {
      do
      {
        LODWORD(v28) = v28 - 2;
        *v38 = __ROR2__(*v38, 8);
        ++v38;
      }
      while ( (unsigned int)v28 >= 2 );
      v28 = v78;
    }
LABEL_46:
    if ( !this[9].LockSemaphore && (_DWORD)v28 )
    {
      v39 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, __int64, HANDLE *, __int64))(*(_QWORD *)this[9].OwningThread
                                                                                  + 104LL))(
              this[9].OwningThread,
              v75[0],
              v28,
              &this[8].LockSemaphore,
              v74);
      v28 = v78;
      v20 = v39;
    }
    if ( v20 < 0 || this[9].LockSemaphore )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v74 + 32LL))(v74, v25, v28);
      if ( v6 < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v40, v27);
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
          if ( *((_DWORD *)v58 + 499) != v6 )
            CallStackContext::TraceFailure(v58, "CAC3StreamSink::ProcessSample", 213, v6);
        }
        if ( !g_wppLevels )
          goto LABEL_133;
        v42 = 29;
LABEL_131:
        p_LockSemaphore = &this[-1].LockSemaphore;
LABEL_132:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          &WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
          p_LockSemaphore,
          v6);
LABEL_133:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
        break;
      }
      v28 = v78;
    }
    v6 = v20;
    this[11].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)this[11].DebugInfo + (unsigned int)v28);
    if ( v20 < 0 )
    {
      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v28, v27);
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
        if ( *((_DWORD *)v55 + 499) != v20 )
          CallStackContext::TraceFailure(v55, "CAC3StreamSink::ProcessSample", 219, v20);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
          &this[-1].LockSemaphore,
          v20);
      goto LABEL_133;
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
  }
  LockSemaphore = this[9].LockSemaphore;
  if ( LockSemaphore )
  {
    v6 = (*(__int64 (__fastcall **)(HANDLE, struct IMFSample *, ULONG_PTR *, struct IMFSample *))(*(_QWORD *)LockSemaphore
                                                                                                + 24LL))(
           LockSemaphore,
           v77,
           &this[8].SpinCount,
           v77);
    if ( v6 < 0 )
    {
      v69 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
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
        if ( *((_DWORD *)v71 + 499) != v6 )
          CallStackContext::TraceFailure(v71, "CAC3StreamSink::ProcessSample", 225, v6);
      }
      if ( g_wppLevels )
      {
        v12 = 31;
LABEL_146:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          &WPP_7f4fecde50743bf3e33c60f973a92bf6_Traceguids,
          &this[-1].LockSemaphore,
          v6);
      }
    }
  }
LABEL_147:
  LeaveCriticalSection(this + 10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v76);
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
