# CCacheReaderBufferList::Get(MFBUFFER::CBuffer const &)

- ea: `0x18002d580`
- end: `0x18002debf`
- name: `?Get@CCacheReaderBufferList@@QEAAJAEBVCBuffer@MFBUFFER@@@Z`
- size: `2367`
- prototype: `__int64 __fastcall(CCacheReaderBufferList *__hidden this, const struct MFBUFFER::CBuffer *)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x18002cad8`
- `0x18002cb00`
- `0x18002cb50`
- `0x1800e5510`
- `0x18016978c`
- `0x18016be04`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x18002d580`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d7d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d8ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d7d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d8ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d814`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d9e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d814`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d9e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d671`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d7bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d8ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d982`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d671`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d7bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d8ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d982`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002da05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dbff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dc39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002da05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dbff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dc39`

## string_xrefs

- `0x18002d5ac`: `CCacheReaderBufferList::Get`
- `0x18002dcde`: `CCacheReaderBufferList::Get`
- `0x18002dd0f`: `CCacheReaderBufferList::Get`
- `0x18002d6a5`: `CCacheReaderBufferList::GetLockedBufferPointer`
- `0x18002dc7c`: `CCacheReaderBufferList::GetLockedBufferPointer`
- `0x18002d8e5`: `CCacheReaderBufferList::UnlockBuffer`
- `0x18002dcad`: `CCacheReaderBufferList::UnlockBuffer`

## pseudocode

```c
__int64 __fastcall CCacheReaderBufferList::Get(CCacheReaderBufferList *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // r15
  CCacheReaderBufferList *v3; // r14
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int64 v7; // rax
  const struct MFBUFFER::CBuffer *v8; // rsi
  unsigned __int64 v9; // rcx
  int v10; // ebp
  unsigned int v11; // r13d
  unsigned __int64 v12; // r12
  unsigned int v13; // ecx
  CallStackTracing *v14; // rbx
  char *v15; // rdi
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // r14d
  unsigned int v21; // ebx
  __int64 *v22; // rcx
  __int64 v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned __int64 v27; // rax
  CallStackTracing *v28; // rbx
  GUID *v29; // rdi
  DWORD v30; // r14d
  GUID *v31; // rax
  int v32; // eax
  int v33; // eax
  const struct MFBUFFER::CBuffer *v34; // r8
  unsigned __int64 v35; // r9
  unsigned __int64 i; // rcx
  char v37; // r10
  CallStackTracing *v38; // rbx
  char *v39; // rdi
  DWORD v40; // ebp
  char *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  CallStackTracing *v44; // rcx
  __int64 v45; // r9
  CallStackTracing *v46; // rbx
  GUID *v47; // rdi
  DWORD v48; // r14d
  GUID *v49; // rax
  int v50; // eax
  int v51; // eax
  CallStackTracing *v52; // rax
  CCacheReaderBufferList *v54; // r9
  __int64 v55; // rdx
  CallStackTracing *v56; // rcx
  __int64 v57; // rax
  CallStackTracing *v58; // rcx
  __int64 v59; // rax
  CallStackTracing *v60; // rcx
  __int64 v61; // rax
  CallStackTracing *v62; // rcx
  __int64 v63; // rax
  CallStackTracing *v64; // rax
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rdx
  CCacheReaderBufferList *v72; // r9
  __int64 v73; // rdx
  __int64 v74; // [rsp+30h] [rbp-58h]
  CCacheReaderBufferList *v75; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v76; // [rsp+98h] [rbp+10h]
  unsigned int v77; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v78; // [rsp+A8h] [rbp+20h] BYREF

  v75 = this;
  v2 = a2;
  v3 = this;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v5 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v6 = 2 * v5;
      *((_QWORD *)ThreadRelativeContext + v6) = "CCacheReaderBufferList::Get";
      *((_DWORD *)ThreadRelativeContext + 2 * v6 + 2) = 681;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v7 = *((unsigned int *)v3 + 115);
  v8 = *(const struct MFBUFFER::CBuffer **)v2;
  v9 = *(_QWORD *)v2 + v7;
  if ( v9 < v7 )
  {
    v10 = -1072875845;
    if ( !g_wppLevels )
      goto LABEL_72;
    v70 = 43;
LABEL_119:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v70, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, v3, v10);
    goto LABEL_72;
  }
  if ( *((unsigned int *)v3 + 116) < v9 )
  {
    v10 = -1072875829;
    if ( !g_wppLevels )
      goto LABEL_72;
    v70 = 44;
    goto LABEL_119;
  }
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    if ( (unsigned __int64)v11 >= *(_QWORD *)v2 )
    {
      *((_DWORD *)v3 + 115) += *(_DWORD *)v2;
      goto LABEL_72;
    }
    v12 = 0;
    v13 = v11 + *((_DWORD *)v3 + 115);
    v74 = 0;
    v10 = -1072875829;
    v76 = v13;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v13 = v76;
    }
    v14 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v15 = (char *)CallStackTracing::s_wpInstance + 208;
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v14 + 3));
      if ( Value )
      {
        v15 = Value;
      }
      else if ( !GetLastError() )
      {
        v56 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v56 = CallStackTracing::s_wpInstance;
        }
        v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v56)(v56);
        if ( v57 )
          v15 = (char *)v57;
      }
      SetLastError(LastError);
      v18 = *((unsigned int *)v15 + 497);
      v3 = v75;
      if ( (unsigned int)v18 < *((_DWORD *)v15 + 498) )
      {
        v19 = 2 * v18;
        *(_QWORD *)&v15[8 * v19] = "CCacheReaderBufferList::GetLockedBufferPointer";
        *(_DWORD *)&v15[8 * v19 + 8] = 814;
      }
      ++*((_DWORD *)v15 + 497);
      v13 = v76;
    }
    if ( v13 >= *((_DWORD *)v3 + 116) )
    {
      if ( g_wppLevels )
      {
        v71 = 53;
        v72 = v3;
LABEL_124:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v71, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, v72, v10);
      }
    }
    else
    {
      v20 = v13 + *((_DWORD *)v3 + 114);
      v21 = 0;
      v22 = (__int64 *)*((_QWORD *)v75 + 54);
      while ( v22 )
      {
        v23 = *v22;
        v22 = (__int64 *)v22[1];
        v21 += *(_DWORD *)(v23 + 32);
        if ( v20 < v21 )
        {
          v24 = *(_QWORD *)(v23 + 16);
          v77 = 0;
          v78 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v24 + 24LL))(
                  v24,
                  &v78,
                  0,
                  &v77);
          if ( v10 < 0 )
          {
            if ( !CallStackTracing::s_wpInstance )
            {
              v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, a2);
              CallStackTracing::s_wpInstance = v64;
              if ( !v64
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v66 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v66 + 499) != v10 )
                CallStackContext::TraceFailure(v66, "CCacheReaderBufferList::GetLockedBufferPointer", 843, v10);
            }
            if ( g_wppLevels )
            {
              v72 = v75;
              v71 = 54;
              goto LABEL_124;
            }
          }
          else
          {
            v26 = v77;
            a2 = v20 - v21 + *(_DWORD *)(v23 + 32);
            if ( a2 <= v77 )
              v26 = (unsigned int)a2;
            v12 = v77 - v26;
            v74 = v26 + v78;
            v27 = *((_DWORD *)v75 + 116) - v76;
            if ( (unsigned int)v27 >= v77 - (unsigned int)a2 )
              v27 = v77 - (unsigned int)a2;
            if ( v27 <= v12 )
              v12 = v27;
          }
          break;
        }
      }
    }
    v28 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v29 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
      v30 = GetLastError();
      v31 = (GUID *)TlsGetValue(*((_DWORD *)v28 + 3));
      if ( v31 )
      {
        v29 = v31;
      }
      else if ( !GetLastError() )
      {
        v58 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v58 = CallStackTracing::s_wpInstance;
        }
        v59 = (**(__int64 (__fastcall ***)(CallStackTracing *))v58)(v58);
        if ( v59 )
          v29 = (GUID *)v59;
      }
      SetLastError(v30);
      v32 = *(_DWORD *)&v29[124].Data2;
      if ( v32 )
      {
        v33 = v32 - 1;
        *(_DWORD *)&v29[124].Data2 = v33;
        if ( !v33 )
        {
          *(_DWORD *)&v29[124].Data2 = 0;
          *(_QWORD *)&v29[126].Data1 = 0;
          *(_DWORD *)&v29[124].Data4[4] = 0;
          v29[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v29[126].Data4 = 0;
          v29[124].Data1 = GetCurrentThreadId();
        }
      }
    }
    if ( v10 < 0 )
      break;
    v34 = *(const struct MFBUFFER::CBuffer **)v2;
    v35 = *(_QWORD *)v2 - v11;
    if ( v35 >= v12 )
      v35 = v12;
    if ( v35 )
    {
      for ( i = 0; i < v35; ++i )
      {
        v8 = (const struct MFBUFFER::CBuffer *)((char *)v8 - 1);
        a2 = (unsigned __int64)v34;
        if ( v8 <= v34 )
          a2 = (unsigned __int64)v8;
        if ( i >= v12 )
          v37 = 0;
        else
          v37 = *(_BYTE *)(v74 + i);
        if ( v34 != (const struct MFBUFFER::CBuffer *)a2 )
        {
          *(_BYTE *)(a2 + *(_QWORD *)(v2 + 8)) = v37;
          v34 = *(const struct MFBUFFER::CBuffer **)v2;
        }
        ++v11;
      }
    }
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    v38 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v39 = (char *)CallStackTracing::s_wpInstance + 208;
      v40 = GetLastError();
      v41 = (char *)TlsGetValue(*((_DWORD *)v38 + 3));
      if ( v41 )
      {
        v39 = v41;
      }
      else if ( !GetLastError() )
      {
        v60 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v60 = CallStackTracing::s_wpInstance;
        }
        v61 = (**(__int64 (__fastcall ***)(CallStackTracing *))v60)(v60);
        if ( v61 )
          v39 = (char *)v61;
      }
      SetLastError(v40);
      v42 = *((unsigned int *)v39 + 497);
      if ( (unsigned int)v42 < *((_DWORD *)v39 + 498) )
      {
        v43 = 2 * v42;
        *(_QWORD *)&v39[8 * v43] = "CCacheReaderBufferList::UnlockBuffer";
        *(_DWORD *)&v39[8 * v43 + 8] = 867;
      }
      ++*((_DWORD *)v39 + 497);
    }
    v3 = v75;
    v44 = (CallStackTracing *)v76;
    if ( v76 > *((_DWORD *)v75 + 116) )
    {
      v10 = -1072875829;
      if ( g_wppLevels )
      {
        v73 = 56;
LABEL_136:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v73, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, v3, v10);
      }
    }
    else
    {
      v10 = 0;
      v44 = (CallStackTracing *)*((_QWORD *)v75 + 54);
      a2 = 0;
      while ( v44 )
      {
        v45 = *(_QWORD *)v44;
        v44 = (CallStackTracing *)*((_QWORD *)v44 + 1);
        a2 = (unsigned int)(*(_DWORD *)(v45 + 32) + a2);
        if ( v76 + *((_DWORD *)v75 + 114) < (unsigned int)a2 )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v45 + 16) + 32LL))(*(_QWORD *)(v45 + 16));
          if ( v10 < 0 )
          {
            if ( !CallStackTracing::s_wpInstance )
            {
              v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v44, a2);
              CallStackTracing::s_wpInstance = v65;
              v44 = v65;
              if ( !v65
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v67 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v67 + 499) != v10 )
                CallStackContext::TraceFailure(v67, "CCacheReaderBufferList::UnlockBuffer", 893, v10);
            }
            if ( g_wppLevels )
            {
              v73 = 57;
              goto LABEL_136;
            }
          }
          break;
        }
      }
    }
    v46 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v47 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
      v48 = GetLastError();
      v49 = (GUID *)TlsGetValue(*((_DWORD *)v46 + 3));
      if ( v49 )
      {
        v47 = v49;
      }
      else if ( !GetLastError() )
      {
        v62 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v62 = CallStackTracing::s_wpInstance;
        }
        v63 = (**(__int64 (__fastcall ***)(CallStackTracing *))v62)(v62);
        if ( v63 )
          v47 = (GUID *)v63;
      }
      SetLastError(v48);
      v50 = *(_DWORD *)&v47[124].Data2;
      v3 = v75;
      if ( v50 )
      {
        v51 = v50 - 1;
        *(_DWORD *)&v47[124].Data2 = v51;
        if ( !v51 )
        {
          *(_DWORD *)&v47[124].Data2 = 0;
          *(_QWORD *)&v47[126].Data1 = 0;
          *(_DWORD *)&v47[124].Data4[4] = 0;
          v47[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v47[126].Data4 = 0;
          v47[124].Data1 = GetCurrentThreadId();
        }
      }
    }
    if ( v10 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v44, a2);
        CallStackTracing::s_wpInstance = v52;
        if ( !v52 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v68 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v68 + 499) != v10 )
          CallStackContext::TraceFailure(v68, "CCacheReaderBufferList::Get", 720, v10);
      }
      if ( g_wppLevels )
      {
        v55 = 46;
        v54 = v3;
        goto LABEL_78;
      }
      goto LABEL_72;
    }
  }
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v69 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v69 + 499) != v10 )
      CallStackContext::TraceFailure(v69, "CCacheReaderBufferList::Get", 709, v10);
  }
  if ( g_wppLevels )
  {
    v54 = v75;
    v55 = 45;
LABEL_78:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, v54, v10);
  }
LABEL_72:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v75);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002d580  mov     [rsp+arg_0], rcx
0x18002d585  push    rbx
0x18002d586  push    rbp
0x18002d587  push    rsi
0x18002d588  push    rdi
0x18002d589  push    r14
0x18002d58b  push    r15
0x18002d58d  sub     rsp, 58h
0x18002d591  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d599  mov     r15, rdx
0x18002d59c  mov     r14, rcx
0x18002d59f  jz      loc_18002DA7C
0x18002d5a5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d5ac  lea     rdi, aCcachereaderbu_2; "CCacheReaderBufferList::Get"
0x18002d5b3  cmp     byte ptr [rbx+8], 0
0x18002d5b7  jz      short loc_18002D5E4
0x18002d5b9  mov     rcx, rbx; this
0x18002d5bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d5c1  mov     ecx, [rax+7C4h]
0x18002d5c7  cmp     ecx, [rax+7C8h]
0x18002d5cd  jnb     short loc_18002D5DE
0x18002d5cf  add     rcx, rcx
0x18002d5d2  mov     [rax+rcx*8], rdi
0x18002d5d6  mov     dword ptr [rax+rcx*8+8], 2A9h
0x18002d5de  inc     dword ptr [rax+7C4h]
0x18002d5e4  mov     eax, [r14+1CCh]
0x18002d5eb  mov     rsi, [r15]
0x18002d5ee  lea     rcx, [rsi+rax]
0x18002d5f2  cmp     rcx, rax
0x18002d5f5  jb      loc_18002DD29
0x18002d5fb  mov     eax, [r14+1D0h]
0x18002d602  cmp     rax, rcx
0x18002d605  jb      loc_18002DD6A
0x18002d60b  mov     [rsp+88h+var_38], r12
0x18002d610  xor     ebp, ebp
0x18002d612  mov     [rsp+88h+var_40], r13
0x18002d617  xor     r13d, r13d
0x18002d61a  mov     eax, r13d
0x18002d61d  cmp     rax, [r15]
0x18002d620  jnb     loc_18002DA31
0x18002d626  mov     ecx, [r14+1CCh]
0x18002d62d  xor     r12d, r12d
0x18002d630  add     ecx, r13d
0x18002d633  mov     [rsp+88h+var_58], r12
0x18002d638  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d63f  mov     ebp, 0C00D36CBh
0x18002d644  mov     [rsp+88h+arg_8], ecx
0x18002d64b  jz      loc_18002DA61
0x18002d651  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d658  cmp     [rbx+8], r12b
0x18002d65c  jz      short loc_18002D6C5
0x18002d65e  lea     rdi, [rbx+0D0h]
0x18002d665  call    cs:__imp_GetLastError
0x18002d66b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d66e  mov     r14d, eax
0x18002d671  call    cs:__imp_TlsGetValue
0x18002d677  test    rax, rax
0x18002d67a  jz      loc_18002DADB
0x18002d680  mov     rdi, rax
0x18002d683  mov     ecx, r14d; dwErrCode
0x18002d686  call    cs:__imp_SetLastError
0x18002d68c  mov     eax, [rdi+7C4h]
0x18002d692  mov     r14, [rsp+88h+arg_0]
0x18002d69a  cmp     eax, [rdi+7C8h]
0x18002d6a0  jnb     short loc_18002D6B8
0x18002d6a2  add     rax, rax
0x18002d6a5  lea     rcx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18002d6ac  mov     [rdi+rax*8], rcx
0x18002d6b0  mov     dword ptr [rdi+rax*8+8], 32Eh
0x18002d6b8  inc     dword ptr [rdi+7C4h]
0x18002d6be  mov     ecx, [rsp+88h+arg_8]
0x18002d6c5  cmp     ecx, [r14+1D0h]
0x18002d6cc  jnb     loc_18002DD7E
0x18002d6d2  mov     r14d, [r14+1C8h]
0x18002d6d9  add     r14d, ecx
0x18002d6dc  mov     rcx, [rsp+88h+arg_0]
0x18002d6e4  xor     ebx, ebx
0x18002d6e6  mov     rcx, [rcx+1B0h]
0x18002d6ed  test    rcx, rcx
0x18002d6f0  jz      loc_18002D79B
0x18002d6f6  mov     rdi, [rcx]
0x18002d6f9  mov     rcx, [rcx+8]
0x18002d6fd  add     ebx, [rdi+20h]
0x18002d700  cmp     r14d, ebx
0x18002d703  jnb     short loc_18002D6ED
0x18002d705  mov     rcx, [rdi+10h]
0x18002d709  lea     r9, [rsp+88h+arg_10]
0x18002d711  xor     eax, eax
0x18002d713  lea     rdx, [rsp+88h+arg_18]
0x18002d71b  mov     [rsp+88h+arg_10], eax
0x18002d722  xor     r8d, r8d
0x18002d725  mov     [rsp+88h+arg_18], rax
0x18002d72d  mov     rax, [rcx]
0x18002d730  mov     rax, [rax+18h]
0x18002d734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d739  mov     ebp, eax
0x18002d73b  test    eax, eax
0x18002d73d  js      loc_18002DBF2
0x18002d743  mov     r8d, [rsp+88h+arg_10]
0x18002d74b  sub     r14d, ebx
0x18002d74e  mov     edx, [rdi+20h]
0x18002d751  mov     ecx, r8d
0x18002d754  add     edx, r14d
0x18002d757  mov     r12d, r8d
0x18002d75a  mov     eax, edx
0x18002d75c  cmp     rax, r8
0x18002d75f  cmovbe  ecx, eax
0x18002d762  mov     rax, [rsp+88h+arg_18]
0x18002d76a  add     rax, rcx
0x18002d76d  sub     r12, rcx
0x18002d770  mov     [rsp+88h+var_58], rax
0x18002d775  sub     r8d, edx
0x18002d778  mov     rax, [rsp+88h+arg_0]
0x18002d780  mov     eax, [rax+1D0h]
0x18002d786  sub     eax, [rsp+88h+arg_8]
0x18002d78d  cmp     eax, r8d
0x18002d790  cmovnb  eax, r8d
0x18002d794  cmp     rax, r12
0x18002d797  cmovbe  r12, rax
0x18002d79b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d7a2  cmp     byte ptr [rbx+8], 0
0x18002d7a6  jz      short loc_18002D820
0x18002d7a8  lea     rdi, [rbx+0D0h]
0x18002d7af  call    cs:__imp_GetLastError
0x18002d7b5  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d7b8  mov     r14d, eax
0x18002d7bb  call    cs:__imp_TlsGetValue
0x18002d7c1  test    rax, rax
0x18002d7c4  jz      loc_18002DB10
0x18002d7ca  mov     rdi, rax
0x18002d7cd  mov     ecx, r14d; dwErrCode
0x18002d7d0  call    cs:__imp_SetLastError
0x18002d7d6  mov     eax, [rdi+7C4h]
0x18002d7dc  test    eax, eax
0x18002d7de  jz      short loc_18002D820
0x18002d7e0  sub     eax, 1
0x18002d7e3  mov     [rdi+7C4h], eax
0x18002d7e9  jnz     short loc_18002D820
0x18002d7eb  xor     eax, eax
0x18002d7ed  mov     [rdi+7C4h], eax
0x18002d7f3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002d7fa  mov     [rdi+7E0h], rax
0x18002d801  mov     [rdi+7CCh], eax
0x18002d807  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002d80e  mov     [rdi+7E8h], eax
0x18002d814  call    cs:__imp_GetCurrentThreadId
0x18002d81a  mov     [rdi+7C0h], eax
0x18002d820  test    ebp, ebp
0x18002d822  js      loc_18002DA86
0x18002d828  mov     r8, [r15]
0x18002d82b  mov     r9, r8
0x18002d82e  mov     eax, r13d
0x18002d831  sub     r9, rax
0x18002d834  cmp     r9, r12
0x18002d837  jb      short loc_18002D83C
0x18002d839  mov     r9, r12
0x18002d83c  test    r9, r9
0x18002d83f  jz      short loc_18002D88D
0x18002d841  mov     r11, [rsp+88h+var_58]
0x18002d846  xor     ecx, ecx
0x18002d848  nop     dword ptr [rax+rax+00000000h]
0x18002d850  dec     rsi
0x18002d853  mov     rdx, r8
0x18002d856  cmp     rsi, r8
0x18002d859  cmovbe  rdx, rsi
0x18002d85d  cmp     rcx, r12
0x18002d860  jnb     loc_18002DDFB
0x18002d866  movzx   r10d, byte ptr [r11+rcx]
0x18002d86b  mov     rax, r8
0x18002d86e  sub     rax, rdx
0x18002d871  cmp     rax, 1
0x18002d875  jb      short loc_18002D882
0x18002d877  mov     rax, [r15+8]
0x18002d87b  mov     [rdx+rax], r10b
0x18002d87f  mov     r8, [r15]
0x18002d882  inc     r13d
0x18002d885  inc     rcx
0x18002d888  cmp     rcx, r9
0x18002d88b  jb      short loc_18002D850
0x18002d88d  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d895  jz      loc_18002DA72
0x18002d89b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d8a2  cmp     byte ptr [rbx+8], 0
0x18002d8a6  jz      short loc_18002D8FE
0x18002d8a8  lea     rdi, [rbx+0D0h]
0x18002d8af  call    cs:__imp_GetLastError
0x18002d8b5  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d8b8  mov     ebp, eax
0x18002d8ba  call    cs:__imp_TlsGetValue
0x18002d8c0  test    rax, rax
0x18002d8c3  jz      loc_18002DB45
0x18002d8c9  mov     rdi, rax
0x18002d8cc  mov     ecx, ebp; dwErrCode
0x18002d8ce  call    cs:__imp_SetLastError
0x18002d8d4  mov     eax, [rdi+7C4h]
0x18002d8da  cmp     eax, [rdi+7C8h]
0x18002d8e0  jnb     short loc_18002D8F8
0x18002d8e2  add     rax, rax
0x18002d8e5  lea     rcx, aCcachereaderbu_0; "CCacheReaderBufferList::UnlockBuffer"
0x18002d8ec  mov     [rdi+rax*8], rcx
0x18002d8f0  mov     dword ptr [rdi+rax*8+8], 363h
0x18002d8f8  inc     dword ptr [rdi+7C4h]
0x18002d8fe  mov     r14, [rsp+88h+arg_0]
0x18002d906  mov     ecx, [rsp+88h+arg_8]
0x18002d90d  cmp     ecx, [r14+1D0h]
0x18002d914  ja      loc_18002DE03
0x18002d91a  mov     r8d, [r14+1C8h]
0x18002d921  xor     ebp, ebp
0x18002d923  add     r8d, ecx
0x18002d926  mov     rcx, [r14+1B0h]
0x18002d92d  xor     edx, edx
0x18002d92f  test    rcx, rcx
0x18002d932  jz      short loc_18002D95E
0x18002d934  mov     r9, [rcx]
0x18002d937  mov     rcx, [rcx+8]
0x18002d93b  add     edx, [r9+20h]
0x18002d93f  cmp     r8d, edx
0x18002d942  jnb     short loc_18002D92F
0x18002d944  mov     rcx, [r9+10h]
0x18002d948  mov     rax, [rcx]
0x18002d94b  mov     rax, [rax+20h]
0x18002d94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d954  mov     ebp, eax
0x18002d956  test    eax, eax
0x18002d958  js      loc_18002DC2B
0x18002d95e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d965  cmp     byte ptr [rbx+8], 0
0x18002d969  jz      loc_18002D9EF
0x18002d96f  lea     rdi, [rbx+0D0h]
0x18002d976  call    cs:__imp_GetLastError
0x18002d97c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d97f  mov     r14d, eax
0x18002d982  call    cs:__imp_TlsGetValue
0x18002d988  test    rax, rax
0x18002d98b  jz      loc_18002DB76
0x18002d991  mov     rdi, rax
0x18002d994  mov     ecx, r14d; dwErrCode
0x18002d997  call    cs:__imp_SetLastError
0x18002d99d  mov     eax, [rdi+7C4h]
0x18002d9a3  mov     r14, [rsp+88h+arg_0]
0x18002d9ab  test    eax, eax
0x18002d9ad  jz      short loc_18002D9EF
0x18002d9af  sub     eax, 1
0x18002d9b2  mov     [rdi+7C4h], eax
0x18002d9b8  jnz     short loc_18002D9EF
0x18002d9ba  xor     eax, eax
0x18002d9bc  mov     [rdi+7C4h], eax
0x18002d9c2  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002d9c9  mov     [rdi+7E0h], rax
0x18002d9d0  mov     [rdi+7CCh], eax
0x18002d9d6  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002d9dd  mov     [rdi+7E8h], eax
0x18002d9e3  call    cs:__imp_GetCurrentThreadId
0x18002d9e9  mov     [rdi+7C0h], eax
0x18002d9ef  test    ebp, ebp
0x18002d9f1  jns     loc_18002D61A
0x18002d9f7  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d9ff  jnz     loc_18002DE94
0x18002da05  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002da0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da12  mov     rcx, rax
0x18002da15  test    rax, rax
0x18002da18  jnz     loc_18002DE7B
0x18002da1e  lea     rax, qword_1801B07E0
0x18002da25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da2c  jmp     loc_18002DE94
0x18002da31  mov     ecx, [r15]
0x18002da34  add     [r14+1CCh], ecx
0x18002da3b  mov     r13, [rsp+88h+var_40]
0x18002da40  mov     r12, [rsp+88h+var_38]
0x18002da45  lea     rcx, [rsp+88h+arg_0]; this
0x18002da4d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002da52  mov     eax, ebp
0x18002da54  add     rsp, 58h
0x18002da58  pop     r15
0x18002da5a  pop     r14
0x18002da5c  pop     rdi
0x18002da5d  pop     rsi
0x18002da5e  pop     rbp
0x18002da5f  pop     rbx
0x18002da60  retn
0x18002da61  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002da66  mov     ecx, [rsp+88h+arg_8]
0x18002da6d  jmp     loc_18002D651
0x18002da72  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002da77  jmp     loc_18002D89B
0x18002da7c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002da81  jmp     loc_18002D5A5
0x18002da86  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da8e  jz      loc_18002DBA7
0x18002da94  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da9b  cmp     byte ptr [rbx+8], 0
0x18002da9f  jnz     loc_18002DCF8
0x18002daa5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002daac  jb      short loc_18002DA3B
0x18002daae  mov     r9, [rsp+88h+arg_0]
0x18002dab6  mov     edx, 2Dh ; '-'
0x18002dabb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dac2  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x18002dac9  mov     [rsp+88h+var_68], ebp
  ... truncated ...
```
