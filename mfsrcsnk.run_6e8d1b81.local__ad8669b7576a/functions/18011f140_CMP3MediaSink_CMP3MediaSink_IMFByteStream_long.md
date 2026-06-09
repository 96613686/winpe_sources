# CMP3MediaSink::CMP3MediaSink(IMFByteStream *,long *)

- ea: `0x18011f140`
- end: `0x18011f85c`
- name: `??0CMP3MediaSink@@QEAA@PEAUIMFByteStream@@PEAJ@Z`
- size: `1820`
- prototype: `CMP3MediaSink *__fastcall(CMP3MediaSink *__hidden this, struct IMFByteStream *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1800edb9c`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x18009e480`
- `0x1800ca15c`
- `0x1801095a8`
- `0x1801099f0`
- `0x18011f140`
- `0x18011f864`
- `0x18011f878`
- `0x18011f88c`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f6d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011f6bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011f6bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18011f1c9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18011f1f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18011f1c9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18011f1f2`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18011f32d`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18011f32d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f37c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f44b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f519`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f5bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f6fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f797`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f37c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f44b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f519`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f5bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f6fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011f797`

## pseudocode

```c
CMP3MediaSink *__fastcall CMP3MediaSink::CMP3MediaSink(CMP3MediaSink *this, struct IMFByteStream *a2, int *a3)
{
  __int64 v6; // rcx
  char *v7; // rax
  char *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rax
  wchar_t *v11; // rcx
  int v12; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  CMP3MediaStream *v22; // rax
  __int64 v23; // rdx
  CMP3MediaStream *v24; // rax
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  _BYTE v44[4]; // [rsp+30h] [rbp-58h] BYREF
  int v45; // [rsp+34h] [rbp-54h] BYREF
  struct tagPROPVARIANT v46; // [rsp+38h] [rbp-50h] BYREF

  _InterlockedIncrement(&dword_1801B079C);
  *(_QWORD *)this = &CMP3MediaSink::`vftable'{for `IMFFinalizableMediaSink'};
  *((_QWORD *)this + 1) = &CMP3MediaSink::`vftable'{for `IMFClockStateSink'};
  *((_QWORD *)this + 2) = &CMP3MediaSink::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 3) = &CMP3MediaSink::`vftable'{for `IMFMetadataProvider'};
  *((_QWORD *)this + 4) = &CMP3MediaSink::`vftable'{for `IMFStreamingSinkConfig'};
  CMP3MediaSink::OnWriteSampleAsyncCallback::OnWriteSampleAsyncCallback((CMP3MediaSink *)((char *)this + 40));
  CMP3MediaSink::DoFinalizeAsyncCallback::DoFinalizeAsyncCallback((CMP3MediaSink *)((char *)this + 48));
  CMP3MediaSink::OnWriteMetadataAsyncCallback::OnWriteMetadataAsyncCallback((CMP3MediaSink *)((char *)this + 56));
  *((_DWORD *)this + 16) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  *((_QWORD *)this + 16) = a2;
  *((_DWORD *)this + 28) = 3;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 15) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  *((_QWORD *)this + 23) = &CTFifo<IMFSample *>::`vftable';
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 58) = -1;
  *((_QWORD *)this + 59) = -1;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_WORD *)this + 208) = 0;
  *((_QWORD *)this + 60) = 0;
  *(_OWORD *)((char *)this + 424) = 0;
  v46.bstrblobVal.pData = 0;
  *(_OWORD *)((char *)this + 440) = 0;
  *((_QWORD *)this + 57) = 0;
  v6 = *((_QWORD *)this + 16);
  *(_OWORD *)&v46.vt = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 16))(
    *((_QWORD *)this + 16),
    &GUID_8feed468_6f7e_440d_869a_49bdd283ad0d,
    (char *)this + 136);
  v7 = (char *)operator new(0x128u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 4) = 0;
    *(_QWORD *)v7 = &CID3Writer::`vftable'{for `IMFMetadataProvider'};
    *((_QWORD *)v7 + 1) = &CID3Writer::`vftable'{for `IMFMetadata'};
    *((_QWORD *)v7 + 3) = 0;
    *(_QWORD *)(v7 + 36) = 0;
    *((_DWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *(_QWORD *)(v7 + 60) = 0;
    *((_DWORD *)v7 + 14) = 0;
    *((_QWORD *)v7 + 9) = 0;
    *(_QWORD *)(v7 + 84) = 0;
    *((_DWORD *)v7 + 20) = 0;
    *((_WORD *)v7 + 133) = 3;
    *((_QWORD *)v7 + 34) = 0;
    *((_QWORD *)v7 + 35) = 0;
    v7[288] = 0;
    GetUserDefaultLocaleName((LPWSTR)v7 + 48, 85);
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 47) = v8;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CMP3MediaSink::CMP3MediaSink", 67);
  v10 = *((_QWORD *)this + 47);
  if ( !v10 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSink::CMP3MediaSink", 67, -2147024882);
    }
    if ( g_wppLevels )
    {
      v15 = 13;
LABEL_80:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids,
        this,
        -2147024882);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
  v16 = *((_QWORD *)this + 47);
  v46.vt = 31;
  v46.hVal.QuadPart = (LONGLONG)L"MPG/3";
  v45 = CID3Writer::SetProperty((CID3Writer *)(v16 + 8), L"TFLT", &v46);
  v12 = v45;
  if ( v45 < 0 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != v12 )
        CallStackContext::TraceFailure(v20, "CMP3MediaSink::CMP3MediaSink", 72, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_81;
    v21 = 14;
    goto LABEL_26;
  }
  v22 = (CMP3MediaStream *)operator new(0xD0u);
  if ( v22 )
  {
    v24 = CMP3MediaStream::CMP3MediaStream(v22, this, &v45);
    *((_QWORD *)this + 49) = v24;
    if ( v24 )
    {
      v12 = v45;
      if ( v45 >= 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v24 + 2);
        if ( *((_DWORD *)this + 93) )
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          v12 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v30, "CMP3MediaSink::CMP3MediaSink", 79, -2147418113);
          }
          if ( !g_wppLevels )
            goto LABEL_81;
          v21 = 17;
        }
        else
        {
          if ( !*((_QWORD *)this + 25) )
          {
            *((_DWORD *)this + 52) = 8;
            *((_QWORD *)this + 25) = (char *)this + 216;
            v31 = 0;
            *((_QWORD *)this + 27) = 0;
            do
            {
              v32 = 16 * v31++;
              v33 = v32 + *((_QWORD *)this + 25) + 8LL;
              *(_QWORD *)(v33 + 8) = *((_QWORD *)this + 24);
              *((_QWORD *)this + 24) = v33;
            }
            while ( v31 != 8 );
          }
          *((_QWORD *)this + 44) = 0;
          *((_QWORD *)this + 45) = 0;
          *((_DWORD *)this + 92) = 0;
          *((_DWORD *)this + 93) = 1;
          v12 = 0;
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)this + 60) = EventW;
          if ( EventW )
            goto LABEL_81;
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          if ( v12 >= 0 )
            goto LABEL_81;
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
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
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
            if ( *((_DWORD *)v39 + 499) != v12 )
              CallStackContext::TraceFailure(v39, "CMP3MediaSink::CMP3MediaSink", 84, v12);
          }
          if ( !g_wppLevels )
            goto LABEL_81;
          v21 = 18;
        }
      }
      else
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( v12 < 0 && *((_DWORD *)v27 + 499) != v12 )
            CallStackContext::TraceFailure(v27, "CMP3MediaSink::CMP3MediaSink", 76, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_81;
        v21 = 16;
      }
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v12);
      goto LABEL_81;
    }
  }
  else
  {
    *((_QWORD *)this + 49) = 0;
  }
  v40 = (wchar_t *)CallStackTracing::s_wpInstance;
  v12 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
    CallStackTracing::s_wpInstance = v41;
    if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
    {
      v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v40 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v40 + 8) )
  {
    v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
    if ( *((_DWORD *)v42 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v42, "CMP3MediaSink::CMP3MediaSink", 75, -2147024882);
  }
  if ( g_wppLevels )
  {
    v15 = 15;
    goto LABEL_80;
  }
LABEL_81:
  *a3 = v12;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return this;
}

```

## disassembly

```asm
0x18011f140  mov     [rsp+arg_8], rbx
0x18011f145  push    rbp
0x18011f146  push    rsi
0x18011f147  push    rdi
0x18011f148  push    r12
0x18011f14a  push    r14
0x18011f14c  sub     rsp, 60h
0x18011f150  mov     rax, cs:__security_cookie
0x18011f157  xor     rax, rsp
0x18011f15a  mov     [rsp+88h+var_38], rax
0x18011f15f  mov     r14, r8
0x18011f162  mov     rbx, rdx
0x18011f165  mov     rdi, rcx
0x18011f168  lock inc cs:dword_1801B079C
0x18011f16f  lea     rax, ??_7CMP3MediaSink@@6BIMFFinalizableMediaSink@@@; const CMP3MediaSink::`vftable'{for `IMFFinalizableMediaSink'}
0x18011f176  mov     [rcx], rax
0x18011f179  lea     rax, ??_7CMP3MediaSink@@6BIMFClockStateSink@@@; const CMP3MediaSink::`vftable'{for `IMFClockStateSink'}
0x18011f180  mov     [rcx+8], rax
0x18011f184  lea     rax, ??_7CMP3MediaSink@@6BIMFGetService@@@; const CMP3MediaSink::`vftable'{for `IMFGetService'}
0x18011f18b  mov     [rcx+10h], rax
0x18011f18f  lea     rax, ??_7CMP3MediaSink@@6BIMFMetadataProvider@@@; const CMP3MediaSink::`vftable'{for `IMFMetadataProvider'}
0x18011f196  mov     [rcx+18h], rax
0x18011f19a  lea     rax, ??_7CMP3MediaSink@@6BIMFStreamingSinkConfig@@@; const CMP3MediaSink::`vftable'{for `IMFStreamingSinkConfig'}
0x18011f1a1  mov     [rcx+20h], rax
0x18011f1a5  add     rcx, 28h ; '('; this
0x18011f1a9  call    ??0OnWriteSampleAsyncCallback@CMP3MediaSink@@QEAA@XZ; CMP3MediaSink::OnWriteSampleAsyncCallback::OnWriteSampleAsyncCallback(void)
0x18011f1ae  lea     rcx, [rdi+30h]; this
0x18011f1b2  call    ??0DoFinalizeAsyncCallback@CMP3MediaSink@@QEAA@XZ; CMP3MediaSink::DoFinalizeAsyncCallback::DoFinalizeAsyncCallback(void)
0x18011f1b7  lea     rcx, [rdi+38h]; this
0x18011f1bb  call    ??0OnWriteMetadataAsyncCallback@CMP3MediaSink@@QEAA@XZ; CMP3MediaSink::OnWriteMetadataAsyncCallback::OnWriteMetadataAsyncCallback(void)
0x18011f1c0  xor     ebp, ebp
0x18011f1c2  lea     rcx, [rdi+48h]; lpCriticalSection
0x18011f1c6  mov     [rdi+40h], ebp
0x18011f1c9  call    cs:__imp_InitializeCriticalSection
0x18011f1cf  mov     [rdi+80h], rbx
0x18011f1d6  lea     rcx, [rdi+90h]; lpCriticalSection
0x18011f1dd  lea     rbx, [rdi+88h]
0x18011f1e4  mov     dword ptr [rdi+70h], 3
0x18011f1eb  mov     [rbx], rbp
0x18011f1ee  mov     [rdi+78h], rbp
0x18011f1f2  call    cs:__imp_InitializeCriticalSection
0x18011f1f8  xorps   xmm0, xmm0
0x18011f1fb  lea     rax, ??_7?$CTFifo@PEAUIMFSample@@@@6B@; const CTFifo<IMFSample *>::`vftable'
0x18011f202  mov     [rdi+0B8h], rax
0x18011f209  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011f20d  mov     [rdi+0C0h], rbp
0x18011f214  mov     [rdi+0C8h], rbp
0x18011f21b  mov     [rdi+0D0h], ebp
0x18011f221  mov     [rdi+170h], rbp
0x18011f228  mov     [rdi+160h], rbp
0x18011f22f  mov     [rdi+1D0h], rax
0x18011f236  mov     [rdi+1D8h], rax
0x18011f23d  xor     eax, eax
0x18011f23f  mov     [rdi+178h], rbp
0x18011f246  mov     [rdi+180h], ebp
0x18011f24c  mov     [rdi+188h], rbp
0x18011f253  mov     [rdi+190h], rbp
0x18011f25a  mov     [rdi+198h], rbp
0x18011f261  mov     [rdi+1A0h], bp
0x18011f268  mov     [rdi+1E0h], rbp
0x18011f26f  movups  xmmword ptr [rdi+1A8h], xmm0
0x18011f276  mov     qword ptr [rsp+88h+var_50+10h], rax
0x18011f27b  movups  xmmword ptr [rdi+1B8h], xmm0
0x18011f282  mov     [rdi+1C8h], rax
0x18011f289  mov     rcx, [rdi+80h]
0x18011f290  movups  xmmword ptr [rsp+88h+var_50], xmm0
0x18011f295  mov     rax, [rcx]
0x18011f298  mov     rax, [rax+8]
0x18011f29c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f2a1  mov     rcx, [rdi+80h]
0x18011f2a8  lea     rdx, _GUID_8feed468_6f7e_440d_869a_49bdd283ad0d
0x18011f2af  mov     r8, rbx
0x18011f2b2  mov     rax, [rcx]
0x18011f2b5  mov     rax, [rax]
0x18011f2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f2bd  mov     ecx, 128h; Size
0x18011f2c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18011f2c7  mov     rbx, rax
0x18011f2ca  test    rax, rax
0x18011f2cd  jz      short loc_18011F335
0x18011f2cf  mov     [rbx+10h], ebp
0x18011f2d2  lea     rax, ??_7CID3Writer@@6BIMFMetadataProvider@@@; const CID3Writer::`vftable'{for `IMFMetadataProvider'}
0x18011f2d9  mov     [rbx], rax
0x18011f2dc  lea     rcx, [rbx+60h]; lpLocaleName
0x18011f2e0  lea     rax, ??_7CID3Writer@@6BIMFMetadata@@@; const CID3Writer::`vftable'{for `IMFMetadata'}
0x18011f2e7  mov     [rbx+8], rax
0x18011f2eb  lea     edx, [rbp+55h]; cchLocaleName
0x18011f2ee  mov     [rbx+18h], rbp
0x18011f2f2  mov     [rbx+24h], rbp
0x18011f2f6  mov     [rbx+20h], ebp
0x18011f2f9  mov     [rbx+30h], rbp
0x18011f2fd  mov     [rbx+3Ch], rbp
0x18011f301  mov     [rbx+38h], ebp
0x18011f304  mov     [rbx+48h], rbp
0x18011f308  mov     [rbx+54h], rbp
0x18011f30c  mov     [rbx+50h], ebp
0x18011f30f  mov     word ptr [rbx+10Ah], 3
0x18011f318  mov     [rbx+110h], rbp
0x18011f31f  mov     [rbx+118h], rbp
0x18011f326  mov     [rbx+120h], bpl
0x18011f32d  call    cs:__imp_GetUserDefaultLocaleName
0x18011f333  jmp     short loc_18011F338
0x18011f335  mov     rbx, rbp
0x18011f338  lea     r12, aCmp3mediasinkC; "CMP3MediaSink::CMP3MediaSink"
0x18011f33f  mov     [rdi+178h], rbx
0x18011f346  mov     rdx, r12; char *
0x18011f349  lea     rcx, [rsp+88h+var_58]; this
0x18011f34e  mov     r8d, 43h ; 'C'; int
0x18011f354  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18011f359  mov     rax, [rdi+178h]
0x18011f360  test    rax, rax
0x18011f363  jnz     loc_18011F3FB
0x18011f369  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f370  mov     esi, 8007000Eh
0x18011f375  mov     ebx, esi
0x18011f377  test    rcx, rcx
0x18011f37a  jnz     short loc_18011F3BD
0x18011f37c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011f382  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f389  mov     rcx, rax
0x18011f38c  test    rax, rax
0x18011f38f  jz      short loc_18011F3AF
0x18011f391  mov     rax, [rax]
0x18011f394  mov     edx, 7F0h
0x18011f399  mov     rax, [rax+8]
0x18011f39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f3a2  test    eax, eax
0x18011f3a4  jz      short loc_18011F3AF
0x18011f3a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f3ad  jmp     short loc_18011F3BD
0x18011f3af  lea     rcx, qword_1801B07E0; this
0x18011f3b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f3bd  cmp     [rcx+8], bpl
0x18011f3c1  jz      short loc_18011F3E4
0x18011f3c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011f3c8  cmp     [rax+7CCh], esi
0x18011f3ce  jz      short loc_18011F3E4
0x18011f3d0  mov     r9d, esi; int
0x18011f3d3  mov     r8d, 43h ; 'C'; int
0x18011f3d9  mov     rdx, r12; char *
0x18011f3dc  mov     rcx, rax; this
0x18011f3df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011f3e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011f3eb  jb      loc_18011F82B
0x18011f3f1  mov     edx, 0Dh
0x18011f3f6  jmp     loc_18011F80D
0x18011f3fb  lock inc dword ptr [rax+10h]
0x18011f3ff  mov     rcx, [rdi+178h]
0x18011f406  lea     r8, [rsp+88h+var_50]; struct tagPROPVARIANT *
0x18011f40b  mov     eax, 1Fh
0x18011f410  lea     rdx, aTflt; "TFLT"
0x18011f417  mov     word ptr [rsp+88h+var_50], ax
0x18011f41c  add     rcx, 8; this
0x18011f420  lea     rax, aMpg3; "MPG/3"
0x18011f427  mov     qword ptr [rsp+88h+var_50+8], rax
0x18011f42c  call    ?SetProperty@CID3Writer@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z; CID3Writer::SetProperty(ushort const *,tagPROPVARIANT const *)
0x18011f431  mov     [rsp+88h+var_54], eax
0x18011f435  mov     ebx, eax
0x18011f437  test    eax, eax
0x18011f439  jns     loc_18011F4CE
0x18011f43f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f446  test    rcx, rcx
0x18011f449  jnz     short loc_18011F48C
0x18011f44b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011f451  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f458  mov     rcx, rax
0x18011f45b  test    rax, rax
0x18011f45e  jz      short loc_18011F47E
0x18011f460  mov     rax, [rax]
0x18011f463  mov     edx, 7F0h
0x18011f468  mov     rax, [rax+8]
0x18011f46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f471  test    eax, eax
0x18011f473  jz      short loc_18011F47E
0x18011f475  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f47c  jmp     short loc_18011F48C
0x18011f47e  lea     rcx, qword_1801B07E0; this
0x18011f485  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f48c  cmp     [rcx+8], bpl
0x18011f490  jz      short loc_18011F4B3
0x18011f492  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011f497  cmp     [rax+7CCh], ebx
0x18011f49d  jz      short loc_18011F4B3
0x18011f49f  mov     r9d, ebx; int
0x18011f4a2  mov     r8d, 48h ; 'H'; int
0x18011f4a8  mov     rdx, r12; char *
0x18011f4ab  mov     rcx, rax; this
0x18011f4ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011f4b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011f4ba  jb      loc_18011F82B
0x18011f4c0  mov     edx, 0Eh
0x18011f4c5  mov     [rsp+88h+var_68], ebx
0x18011f4c9  jmp     loc_18011F811
0x18011f4ce  mov     ecx, 0D0h; Size
0x18011f4d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18011f4d8  test    rax, rax
0x18011f4db  jz      loc_18011F77D
0x18011f4e1  lea     r8, [rsp+88h+var_54]; int *
0x18011f4e6  mov     rdx, rdi; struct CMP3MediaSink *
0x18011f4e9  mov     rcx, rax; this
0x18011f4ec  call    ??0CMP3MediaStream@@QEAA@PEAVCMP3MediaSink@@PEAJ@Z; CMP3MediaStream::CMP3MediaStream(CMP3MediaSink *,long *)
0x18011f4f1  mov     [rdi+188h], rax
0x18011f4f8  test    rax, rax
0x18011f4fb  jz      loc_18011F784
0x18011f501  mov     ebx, [rsp+88h+var_54]
0x18011f505  test    ebx, ebx
0x18011f507  jns     loc_18011F59C
0x18011f50d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f514  test    rcx, rcx
0x18011f517  jnz     short loc_18011F55A
0x18011f519  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011f51f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f526  mov     rcx, rax
0x18011f529  test    rax, rax
0x18011f52c  jz      short loc_18011F54C
0x18011f52e  mov     rax, [rax]
0x18011f531  mov     edx, 7F0h
0x18011f536  mov     rax, [rax+8]
0x18011f53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f53f  test    eax, eax
0x18011f541  jz      short loc_18011F54C
0x18011f543  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f54a  jmp     short loc_18011F55A
0x18011f54c  lea     rcx, qword_1801B07E0; this
0x18011f553  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f55a  cmp     [rcx+8], bpl
0x18011f55e  jz      short loc_18011F585
0x18011f560  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011f565  test    ebx, ebx
0x18011f567  jns     short loc_18011F585
0x18011f569  cmp     [rax+7CCh], ebx
0x18011f56f  jz      short loc_18011F585
0x18011f571  mov     r9d, ebx; int
0x18011f574  mov     r8d, 4Ch ; 'L'; int
0x18011f57a  mov     rdx, r12; char *
0x18011f57d  mov     rcx, rax; this
0x18011f580  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011f585  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011f58c  jb      loc_18011F82B
0x18011f592  mov     edx, 10h
0x18011f597  jmp     loc_18011F4C5
0x18011f59c  lock inc dword ptr [rax+8]
0x18011f5a0  cmp     [rdi+174h], ebp
0x18011f5a6  jz      loc_18011F63C
0x18011f5ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f5b3  mov     ebx, 8000FFFFh
0x18011f5b8  test    rcx, rcx
0x18011f5bb  jnz     short loc_18011F5FE
0x18011f5bd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011f5c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f5ca  mov     rcx, rax
0x18011f5cd  test    rax, rax
0x18011f5d0  jz      short loc_18011F5F0
0x18011f5d2  mov     rax, [rax]
0x18011f5d5  mov     edx, 7F0h
0x18011f5da  mov     rax, [rax+8]
0x18011f5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f5e3  test    eax, eax
0x18011f5e5  jz      short loc_18011F5F0
0x18011f5e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f5ee  jmp     short loc_18011F5FE
0x18011f5f0  lea     rcx, qword_1801B07E0; this
0x18011f5f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011f5fe  cmp     [rcx+8], bpl
0x18011f602  jz      short loc_18011F625
0x18011f604  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011f609  cmp     [rax+7CCh], ebx
0x18011f60f  jz      short loc_18011F625
0x18011f611  mov     r9d, ebx; int
0x18011f614  mov     r8d, 4Fh ; 'O'; int
0x18011f61a  mov     rdx, r12; char *
0x18011f61d  mov     rcx, rax; this
0x18011f620  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011f625  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011f62c  jb      loc_18011F82B
0x18011f632  mov     edx, 11h
0x18011f637  jmp     loc_18011F4C5
0x18011f63c  cmp     [rdi+0C8h], rbp
0x18011f643  jnz     short loc_18011F693
0x18011f645  lea     rax, [rdi+0D8h]
0x18011f64c  mov     dword ptr [rdi+0D0h], 8
0x18011f656  mov     [rdi+0C8h], rax
0x18011f65d  mov     r8, rbp
0x18011f660  mov     [rax], rbp
0x18011f663  mov     rdx, [rdi+0C8h]
0x18011f66a  mov     rcx, r8
0x18011f66d  mov     rax, [rdi+0C0h]
0x18011f674  add     rdx, 8
0x18011f678  shl     rcx, 4
0x18011f67c  inc     r8
0x18011f67f  add     rdx, rcx
0x18011f682  mov     [rdx+8], rax
0x18011f686  mov     [rdi+0C0h], rdx
0x18011f68d  cmp     r8, 8
0x18011f691  jnz     short loc_18011F663
0x18011f693  xor     r9d, r9d; lpName
0x18011f696  mov     [rdi+160h], rbp
0x18011f69d  xor     r8d, r8d; bInitialState
0x18011f6a0  mov     [rdi+168h], rbp
0x18011f6a7  xor     ecx, ecx; lpEventAttributes
  ... truncated ...
```
