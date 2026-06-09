# CMFSourceBuffer::ProcessSampleRequestsIfNecessary(void)

- ea: `0x18004ff50`
- end: `0x1800506f7`
- name: `?ProcessSampleRequestsIfNecessary@CMFSourceBuffer@@AEAAJXZ`
- size: `1959`
- prototype: `__int64 __fastcall(CMFSourceBuffer *__hidden this)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1800058e0`
- `0x18004de30`
- `0x18004ea60`
- `0x180255800`
- `0x18025ae10`
- `0x18026b2b0`
- `0x1802d9020`

## callees

- `0x180019da0`
- `0x18001be0c`
- `0x18004ff50`
- `0x1800f6b10`
- `0x18012d828`
- `0x180458010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ffad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800500e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050214`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050584`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ffad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800500e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050214`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ff8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800500c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800503cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005047c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ff8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800500c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800503cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005047c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050532`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050159`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050176`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800502c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800502e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050159`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050176`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800502c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800502e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050168`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005018a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800501b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050168`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005018a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800501b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004ff99`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005005d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800500d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800501ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050523`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004ff99`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005005d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800500d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800501ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800502a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050341`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800502a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050341`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005038e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800503e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005043e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050496`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800504e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050548`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005038e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800503e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005043e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050496`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800504e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050548`
- `MFPlat!MFPutWorkItem` at `0x180050250`
- `MFPlat!MFPutWorkItem` at `0x180050250`

## pseudocode

```c
__int64 __fastcall CMFSourceBuffer::ProcessSampleRequestsIfNecessary(IMFAsyncCallback *this)
{
  CallStackTracing *v1; // rdi
  char *v3; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  HRESULT v8; // ebp
  CTraceBase *v9; // rdi
  CallStackTracing *v10; // rdi
  GUID *v11; // rbx
  DWORD v12; // esi
  GUID *v13; // rax
  int v14; // eax
  int v15; // eax
  CallStackTracing *v17; // rbp
  char *v18; // rbx
  DWORD v19; // r14d
  char *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 i; // rbp
  __int64 v24; // r15
  char v25; // bl
  struct _RTL_CRITICAL_SECTION *p_GetParameters; // rcx
  char v27; // r13
  __int64 j; // rbp
  struct IMFAsyncCallbackVtbl *lpVtbl; // r14
  CallStackTracing *v30; // rbp
  GUID *v31; // rbx
  DWORD v32; // r14d
  GUID *v33; // rax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  char v39; // bl
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  CallStackTracing *v43; // rcx
  CallStackTracing *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  CallStackTracing *v61; // rcx
  CallStackTracing *v62; // rax
  __int64 v63; // rax
  CallStackTracing *v64; // rbx
  CallStackTracing *v65; // rax
  CallStackContext *v66; // rsi
  DWORD v67; // r14d
  CallStackContext *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // r9
  CallStackTracing *v72; // rcx
  CallStackTracing *v73; // rax
  __int64 v74; // rax
  PVOID v75; // rcx

  v1 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v1 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v1 + 8) )
  {
    v3 = (char *)v1 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v1 + 3));
    if ( Value )
    {
      v3 = Value;
    }
    else if ( !GetLastError() )
    {
      v43 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = (CallStackTracing *)&qword_1804E58E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1804E58E0;
        }
      }
      v45 = (**(__int64 (__fastcall ***)(CallStackTracing *))v43)(v43);
      if ( v45 )
        v3 = (char *)v45;
    }
    SetLastError(LastError);
    v6 = *((unsigned int *)v3 + 497);
    if ( (unsigned int)v6 < *((_DWORD *)v3 + 498) )
    {
      v7 = 2 * v6;
      *(_QWORD *)&v3[8 * v7] = "CMFSourceBuffer::ProcessSampleRequestsIfNecessary";
      *(_DWORD *)&v3[8 * v7 + 8] = 4499;
    }
    ++*((_DWORD *)v3 + 497);
  }
  v8 = 0;
  v9 = (CTraceBase *)&this[10];
  if ( !this )
    v9 = 0;
  CTraceBase::OutputMsg(v9, 0, 0xFu, "=>%s", "CMFSourceBuffer::ProcessSampleRequestsIfNecessary");
  if ( !BYTE6(this[72].lpVtbl) )
  {
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v17 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v18 = (char *)v17 + 208;
      v19 = GetLastError();
      v20 = (char *)TlsGetValue(*((_DWORD *)v17 + 3));
      if ( v20 )
      {
        v18 = v20;
      }
      else if ( !GetLastError() )
      {
        v49 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = (CallStackTracing *)&qword_1804E58E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1804E58E0;
          }
        }
        v51 = (**(__int64 (__fastcall ***)(CallStackTracing *))v49)(v49);
        if ( v51 )
          v18 = (char *)v51;
      }
      SetLastError(v19);
      v21 = *((unsigned int *)v18 + 497);
      if ( (unsigned int)v21 < *((_DWORD *)v18 + 498) )
      {
        v22 = 2 * v21;
        *(_QWORD *)&v18[8 * v22] = "CMFSourceBuffer::HasOutstandingSampleRequests";
        *(_DWORD *)&v18[8 * v22 + 8] = 4455;
      }
      ++*((_DWORD *)v18 + 497);
    }
    CTraceBase::OutputMsg(v9, 0, 0xFu, "=>%s", "CMFSourceBuffer::HasOutstandingSampleRequests");
    for ( i = 0; (unsigned int)i < LODWORD(this[67].lpVtbl); i = (unsigned int)(i + 1) )
    {
      v24 = (__int64)this[66].lpVtbl + 768 * i;
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
      v25 = *(_BYTE *)(v24 + 62);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
      if ( v25 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
        p_GetParameters = (struct _RTL_CRITICAL_SECTION *)(v24 + 8);
        if ( *(_DWORD *)(v24 + 708) )
        {
LABEL_37:
          LeaveCriticalSection(p_GetParameters);
          v27 = 1;
          goto LABEL_38;
        }
        LeaveCriticalSection(p_GetParameters);
      }
    }
    v27 = 0;
    for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
    {
      lpVtbl = this[j + 69].lpVtbl;
      if ( lpVtbl )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)&lpVtbl->GetParameters);
        v39 = BYTE6(lpVtbl[1].Invoke);
        LeaveCriticalSection((LPCRITICAL_SECTION)&lpVtbl->GetParameters);
        if ( v39 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)&lpVtbl->GetParameters);
          p_GetParameters = (struct _RTL_CRITICAL_SECTION *)&lpVtbl->GetParameters;
          if ( HIDWORD(lpVtbl[18].QueryInterface) )
            goto LABEL_37;
          LeaveCriticalSection(p_GetParameters);
        }
      }
    }
LABEL_38:
    CTraceBase::OutputMsg(v9, 0, 0xFu, "<=%s", "CMFSourceBuffer::HasOutstandingSampleRequests");
    v30 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v31 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
      v32 = GetLastError();
      v33 = (GUID *)TlsGetValue(*((_DWORD *)v30 + 3));
      if ( v33 )
      {
        v31 = v33;
      }
      else if ( !GetLastError() )
      {
        v55 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
          CallStackTracing::s_wpInstance = v56;
          if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
          {
            v55 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v55 = (CallStackTracing *)&qword_1804E58E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1804E58E0;
          }
        }
        v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
        if ( v57 )
          v31 = (GUID *)v57;
      }
      SetLastError(v32);
      v34 = *(_DWORD *)&v31[124].Data2;
      if ( v34 )
      {
        v35 = v34 - 1;
        *(_DWORD *)&v31[124].Data2 = v35;
        if ( !v35 )
        {
          *(_DWORD *)&v31[124].Data2 = 0;
          *(_QWORD *)&v31[126].Data1 = 0;
          *(_DWORD *)&v31[124].Data4[4] = 0;
          v31[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v31[126].Data4 = 0;
          v31[124].Data1 = GetCurrentThreadId();
        }
      }
    }
    if ( v27 )
    {
      BYTE6(this[72].lpVtbl) = 1;
      v8 = MFPutWorkItem(5u, this + 15, 0);
      if ( v8 < 0 )
      {
        BYTE6(this[72].lpVtbl) = 0;
        v75 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            324,
            &WPP_63d1e47216e537a03ffe8f00b99272d3_Traceguids,
            LODWORD(this[10].lpVtbl),
            v8);
        }
        v64 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v75, v36, v37, v38);
          CallStackTracing::s_wpInstance = v65;
          if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
          {
            v64 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v64 = (CallStackTracing *)&qword_1804E58E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1804E58E0;
          }
        }
        if ( *((_BYTE *)v64 + 8) )
        {
          v66 = (CallStackTracing *)((char *)v64 + 208);
          v67 = GetLastError();
          v68 = (CallStackContext *)TlsGetValue(*((_DWORD *)v64 + 3));
          if ( v68 )
          {
            v66 = v68;
          }
          else if ( !GetLastError() )
          {
            v72 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v69, v70, v71);
              CallStackTracing::s_wpInstance = v73;
              if ( v73
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
              {
                v72 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v72 = (CallStackTracing *)&qword_1804E58E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1804E58E0;
              }
            }
            v74 = (**(__int64 (__fastcall ***)(CallStackTracing *))v72)(v72);
            if ( v74 )
              v66 = (CallStackContext *)v74;
          }
          SetLastError(v67);
          if ( *((_DWORD *)v66 + 499) != v8 )
            CallStackContext::TraceFailure(v66, "CMFSourceBuffer::ProcessSampleRequestsIfNecessary", 4517, v8);
        }
      }
    }
    else
    {
      v8 = 0;
    }
  }
  CTraceBase::OutputMsg(v9, 0, 0xFu, "<=%s", "CMFSourceBuffer::ProcessSampleRequestsIfNecessary");
  v10 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v11 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v12 = GetLastError();
    v13 = (GUID *)TlsGetValue(*((_DWORD *)v10 + 3));
    if ( v13 )
    {
      v11 = v13;
    }
    else if ( !GetLastError() )
    {
      v61 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
        CallStackTracing::s_wpInstance = v62;
        if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        {
          v61 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v61 = (CallStackTracing *)&qword_1804E58E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1804E58E0;
        }
      }
      v63 = (**(__int64 (__fastcall ***)(CallStackTracing *))v61)(v61);
      if ( v63 )
        v11 = (GUID *)v63;
    }
    SetLastError(v12);
    v14 = *(_DWORD *)&v11[124].Data2;
    if ( v14 )
    {
      v15 = v14 - 1;
      *(_DWORD *)&v11[124].Data2 = v15;
      if ( !v15 )
      {
        *(_DWORD *)&v11[124].Data2 = 0;
        *(_QWORD *)&v11[126].Data1 = 0;
        *(_DWORD *)&v11[124].Data4[4] = 0;
        v11[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v11[126].Data4 = 0;
        v11[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004ff50  push    rbp
0x18004ff52  push    rsi
0x18004ff53  push    rdi
0x18004ff54  sub     rsp, 40h
0x18004ff58  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff5f  mov     rsi, rcx
0x18004ff62  mov     [rsp+58h+arg_8], r12
0x18004ff67  mov     [rsp+58h+var_28], r15
0x18004ff6c  test    rdi, rdi
0x18004ff6f  jz      loc_180050352
0x18004ff75  cmp     byte ptr [rdi+8], 0
0x18004ff79  lea     r15, aCmfsourcebuffe_56; "CMFSourceBuffer::ProcessSampleRequestsI"...
0x18004ff80  mov     [rsp+58h+arg_0], rbx
0x18004ff85  jz      short loc_18004FFD6
0x18004ff87  lea     rbx, [rdi+0D0h]
0x18004ff8e  call    cs:__imp_GetLastError
0x18004ff94  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18004ff97  mov     ebp, eax
0x18004ff99  call    cs:__imp_TlsGetValue
0x18004ff9f  test    rax, rax
0x18004ffa2  jz      loc_180050374
0x18004ffa8  mov     rbx, rax
0x18004ffab  mov     ecx, ebp; dwErrCode
0x18004ffad  call    cs:__imp_SetLastError
0x18004ffb3  mov     eax, [rbx+7C4h]
0x18004ffb9  cmp     eax, [rbx+7C8h]
0x18004ffbf  jnb     short loc_18004FFD0
0x18004ffc1  add     rax, rax
0x18004ffc4  mov     [rbx+rax*8], r15
0x18004ffc8  mov     dword ptr [rbx+rax*8+8], 1193h
0x18004ffd0  inc     dword ptr [rbx+7C4h]
0x18004ffd6  xor     eax, eax
0x18004ffd8  mov     [rsp+58h+var_20], r14
0x18004ffdd  xor     ebp, ebp
0x18004ffdf  mov     [rsp+58h+var_38], r15
0x18004ffe4  test    rsi, rsi
0x18004ffe7  lea     rdi, [rsi+50h]
0x18004ffeb  lea     r9, ?_szEntering@@3QBDB; "=>%s"
0x18004fff2  mov     r8d, 0Fh; unsigned int
0x18004fff8  cmovz   rdi, rax
0x18004fffc  xor     edx, edx; unsigned int
0x18004fffe  mov     rcx, rdi; this
0x180050001  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x180050006  cmp     [rsi+246h], bpl
0x18005000d  jz      loc_18005009F
0x180050013  lea     r9, ?_szLeaving@@3QBDB; "<=%s"
0x18005001a  mov     [rsp+58h+var_38], r15
0x18005001f  xor     edx, edx; unsigned int
0x180050021  mov     r8d, 0Fh; unsigned int
0x180050027  mov     rcx, rdi; this
0x18005002a  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x18005002f  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050036  mov     r15, [rsp+58h+var_28]
0x18005003b  mov     r14, [rsp+58h+var_20]
0x180050040  mov     r12, [rsp+58h+arg_8]
0x180050045  cmp     byte ptr [rdi+8], 0
0x180050049  jz      short loc_180050090
0x18005004b  lea     rbx, [rdi+0D0h]
0x180050052  call    cs:__imp_GetLastError
0x180050058  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18005005b  mov     esi, eax
0x18005005d  call    cs:__imp_TlsGetValue
0x180050063  test    rax, rax
0x180050066  jz      loc_18005047C
0x18005006c  mov     rbx, rax
0x18005006f  mov     ecx, esi; dwErrCode
0x180050071  call    cs:__imp_SetLastError
0x180050077  mov     eax, [rbx+7C4h]
0x18005007d  test    eax, eax
0x18005007f  jz      short loc_180050090
0x180050081  sub     eax, 1
0x180050084  mov     [rbx+7C4h], eax
0x18005008a  jz      loc_18005026C
0x180050090  mov     rbx, [rsp+58h+arg_0]
0x180050095  mov     eax, ebp
0x180050097  add     rsp, 40h
0x18005009b  pop     rdi
0x18005009c  pop     rsi
0x18005009d  pop     rbp
0x18005009e  retn
0x18005009f  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500a6  mov     [rsp+58h+arg_10], r13
0x1800500ab  test    rbp, rbp
0x1800500ae  jz      loc_180050363
0x1800500b4  cmp     byte ptr [rbp+8], 0
0x1800500b8  lea     rcx, aCmfsourcebuffe_177; "CMFSourceBuffer::HasOutstandingSampleRe"...
0x1800500bf  jz      short loc_180050119
0x1800500c1  lea     rbx, [rbp+0D0h]
0x1800500c8  call    cs:__imp_GetLastError
0x1800500ce  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x1800500d1  mov     r14d, eax
0x1800500d4  call    cs:__imp_TlsGetValue
0x1800500da  test    rax, rax
0x1800500dd  jz      loc_1800503CC
0x1800500e3  mov     rbx, rax
0x1800500e6  mov     ecx, r14d; dwErrCode
0x1800500e9  call    cs:__imp_SetLastError
0x1800500ef  mov     eax, [rbx+7C4h]
0x1800500f5  lea     rcx, aCmfsourcebuffe_177; "CMFSourceBuffer::HasOutstandingSampleRe"...
0x1800500fc  cmp     eax, [rbx+7C8h]
0x180050102  jnb     short loc_180050113
0x180050104  add     rax, rax
0x180050107  mov     [rbx+rax*8], rcx
0x18005010b  mov     dword ptr [rbx+rax*8+8], 1167h
0x180050113  inc     dword ptr [rbx+7C4h]
0x180050119  mov     [rsp+58h+var_38], rcx
0x18005011e  lea     r9, ?_szEntering@@3QBDB; "=>%s"
0x180050125  mov     rcx, rdi; this
0x180050128  xor     edx, edx; unsigned int
0x18005012a  mov     r8d, 0Fh; unsigned int
0x180050130  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x180050135  xor     ebp, ebp
0x180050137  cmp     ebp, [rsi+218h]
0x18005013d  jnb     short loc_180050194
0x18005013f  lea     r15, ds:0[rbp*2]
0x180050147  add     r15, rbp
0x18005014a  shl     r15, 8
0x18005014e  add     r15, [rsi+210h]
0x180050155  lea     rcx, [r15+8]; lpCriticalSection
0x180050159  call    cs:__imp_EnterCriticalSection
0x18005015f  movzx   ebx, byte ptr [r15+3Eh]
0x180050164  lea     rcx, [r15+8]; lpCriticalSection
0x180050168  call    cs:__imp_LeaveCriticalSection
0x18005016e  test    bl, bl
0x180050170  jz      short loc_180050190
0x180050172  lea     rcx, [r15+8]; lpCriticalSection
0x180050176  call    cs:__imp_EnterCriticalSection
0x18005017c  cmp     dword ptr [r15+2C4h], 0
0x180050184  lea     rcx, [r15+8]; lpCriticalSection
0x180050188  jnz     short loc_1800501B3
0x18005018a  call    cs:__imp_LeaveCriticalSection
0x180050190  inc     ebp
0x180050192  jmp     short loc_180050137
0x180050194  xor     r13b, r13b
0x180050197  xor     ebp, ebp
0x180050199  cmp     ebp, 2
0x18005019c  jnb     short loc_1800501BC
0x18005019e  mov     r14, [rsi+rbp*8+228h]
0x1800501a6  test    r14, r14
0x1800501a9  jnz     loc_1800502C2
0x1800501af  inc     ebp
0x1800501b1  jmp     short loc_180050199
0x1800501b3  call    cs:__imp_LeaveCriticalSection
0x1800501b9  mov     r13b, 1
0x1800501bc  lea     rax, aCmfsourcebuffe_177; "CMFSourceBuffer::HasOutstandingSampleRe"...
0x1800501c3  xor     edx, edx; unsigned int
0x1800501c5  lea     r9, ?_szLeaving@@3QBDB; "<=%s"
0x1800501cc  mov     [rsp+58h+var_38], rax
0x1800501d1  mov     r8d, 0Fh; unsigned int
0x1800501d7  mov     rcx, rdi; this
0x1800501da  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x1800501df  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800501e6  cmp     byte ptr [rbp+8], 0
0x1800501ea  jz      short loc_180050233
0x1800501ec  lea     rbx, [rbp+0D0h]
0x1800501f3  call    cs:__imp_GetLastError
0x1800501f9  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x1800501fc  mov     r14d, eax
0x1800501ff  call    cs:__imp_TlsGetValue
0x180050205  test    rax, rax
0x180050208  jz      loc_180050424
0x18005020e  mov     rbx, rax
0x180050211  mov     ecx, r14d; dwErrCode
0x180050214  call    cs:__imp_SetLastError
0x18005021a  mov     eax, [rbx+7C4h]
0x180050220  test    eax, eax
0x180050222  jz      short loc_180050233
0x180050224  sub     eax, 1
0x180050227  mov     [rbx+7C4h], eax
0x18005022d  jz      loc_18005030A
0x180050233  test    r13b, r13b
0x180050236  mov     r13, [rsp+58h+arg_10]
0x18005023b  jz      short loc_1800502B4
0x18005023d  lea     rdx, [rsi+78h]; pCallback
0x180050241  mov     byte ptr [rsi+246h], 1
0x180050248  xor     r8d, r8d; pState
0x18005024b  mov     ecx, 5; dwQueue
0x180050250  call    cs:__imp_MFPutWorkItem
0x180050256  mov     ebp, eax
0x180050258  test    eax, eax
0x18005025a  js      loc_18005062A
0x180050260  lea     r15, aCmfsourcebuffe_56; "CMFSourceBuffer::ProcessSampleRequestsI"...
0x180050267  jmp     loc_180050013
0x18005026c  mov     dword ptr [rbx+7C4h], 0
0x180050276  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005027d  mov     qword ptr [rbx+7E0h], 0
0x180050288  mov     dword ptr [rbx+7CCh], 0
0x180050292  movups  xmmword ptr [rbx+7D0h], xmm0
0x180050299  mov     dword ptr [rbx+7E8h], 0
0x1800502a3  call    cs:__imp_GetCurrentThreadId
0x1800502a9  mov     [rbx+7C0h], eax
0x1800502af  jmp     loc_180050090
0x1800502b4  xor     ebp, ebp
0x1800502b6  lea     r15, aCmfsourcebuffe_56; "CMFSourceBuffer::ProcessSampleRequestsI"...
0x1800502bd  jmp     loc_180050013
0x1800502c2  lea     rcx, [r14+18h]; lpCriticalSection
0x1800502c6  call    cs:__imp_EnterCriticalSection
0x1800502cc  movzx   ebx, byte ptr [r14+4Eh]
0x1800502d1  lea     rcx, [r14+18h]; lpCriticalSection
0x1800502d5  call    cs:__imp_LeaveCriticalSection
0x1800502db  test    bl, bl
0x1800502dd  jz      loc_1800501AF
0x1800502e3  lea     rcx, [r14+18h]; lpCriticalSection
0x1800502e7  call    cs:__imp_EnterCriticalSection
0x1800502ed  cmp     dword ptr [r14+2D4h], 0
0x1800502f5  lea     rcx, [r14+18h]; lpCriticalSection
0x1800502f9  jnz     loc_1800501B3
0x1800502ff  call    cs:__imp_LeaveCriticalSection
0x180050305  jmp     loc_1800501AF
0x18005030a  mov     dword ptr [rbx+7C4h], 0
0x180050314  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005031b  mov     qword ptr [rbx+7E0h], 0
0x180050326  mov     dword ptr [rbx+7CCh], 0
0x180050330  movups  xmmword ptr [rbx+7D0h], xmm0
0x180050337  mov     dword ptr [rbx+7E8h], 0
0x180050341  call    cs:__imp_GetCurrentThreadId
0x180050347  mov     [rbx+7C0h], eax
0x18005034d  jmp     loc_180050233
0x180050352  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180050357  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005035e  jmp     loc_18004FF75
0x180050363  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180050368  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005036f  jmp     loc_1800500B4
0x180050374  call    cs:__imp_GetLastError
0x18005037a  test    eax, eax
0x18005037c  jnz     loc_18004FFAB
0x180050382  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050389  test    rcx, rcx
0x18005038c  jnz     short loc_1800503B5
0x18005038e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050394  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005039b  mov     rcx, rax
0x18005039e  test    rax, rax
0x1800503a1  jnz     loc_1800505BB
0x1800503a7  lea     rcx, qword_1804E58E0
0x1800503ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503b5  mov     rax, [rcx]
0x1800503b8  mov     rax, [rax]
0x1800503bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503c0  test    rax, rax
0x1800503c3  cmovnz  rbx, rax
0x1800503c7  jmp     loc_18004FFAB
0x1800503cc  call    cs:__imp_GetLastError
0x1800503d2  test    eax, eax
0x1800503d4  jnz     loc_1800500E6
0x1800503da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503e1  test    rcx, rcx
0x1800503e4  jnz     short loc_18005040D
0x1800503e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800503ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503f3  mov     rcx, rax
0x1800503f6  test    rax, rax
0x1800503f9  jnz     loc_1800505E0
0x1800503ff  lea     rcx, qword_1804E58E0
0x180050406  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005040d  mov     rax, [rcx]
0x180050410  mov     rax, [rax]
0x180050413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050418  test    rax, rax
0x18005041b  cmovnz  rbx, rax
0x18005041f  jmp     loc_1800500E6
0x180050424  call    cs:__imp_GetLastError
0x18005042a  test    eax, eax
0x18005042c  jnz     loc_180050211
0x180050432  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050439  test    rcx, rcx
0x18005043c  jnz     short loc_180050465
0x18005043e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050444  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005044b  mov     rcx, rax
0x18005044e  test    rax, rax
0x180050451  jnz     loc_180050605
0x180050457  lea     rcx, qword_1804E58E0
0x18005045e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050465  mov     rax, [rcx]
0x180050468  mov     rax, [rax]
0x18005046b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050470  test    rax, rax
0x180050473  cmovnz  rbx, rax
0x180050477  jmp     loc_180050211
0x18005047c  call    cs:__imp_GetLastError
0x180050482  test    eax, eax
0x180050484  jnz     loc_18005006F
0x18005048a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050491  test    rcx, rcx
0x180050494  jnz     short loc_1800504BD
0x180050496  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005049c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800504a3  mov     rcx, rax
0x1800504a6  test    rax, rax
0x1800504a9  jnz     loc_1800506D2
0x1800504af  lea     rcx, qword_1804E58E0
0x1800504b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800504bd  mov     rax, [rcx]
0x1800504c0  mov     rax, [rax]
0x1800504c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504c8  test    rax, rax
0x1800504cb  cmovnz  rbx, rax
0x1800504cf  jmp     loc_18005006F
  ... truncated ...
```
