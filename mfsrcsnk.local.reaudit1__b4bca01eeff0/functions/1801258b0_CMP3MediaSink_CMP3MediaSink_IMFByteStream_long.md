# CMP3MediaSink::CMP3MediaSink(IMFByteStream *,long *)

- ea: `0x1801258b0`
- end: `0x180125f2e`
- name: `??0CMP3MediaSink@@QEAA@PEAUIMFByteStream@@PEAJ@Z`
- size: `1662`
- prototype: `CMP3MediaSink *__fastcall(CMP3MediaSink *__hidden this, struct IMFByteStream *, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800f4944`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800a3880`
- `0x1800cfd30`
- `0x180110a94`
- `0x180110ed0`
- `0x180121bf0`
- `0x1801258b0`
- `0x180125f34`
- `0x180125f4c`
- `0x180125f64`
- `0x180128ff8`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180125d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180125d94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180125d78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180125d78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180125939`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180125968`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180125939`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180125968`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125a93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125b68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125c3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125ce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125e62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125a93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125b68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125c3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125ce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180125e62`

## pseudocode

```c
CMP3MediaSink *__fastcall CMP3MediaSink::CMP3MediaSink(CMP3MediaSink *this, struct IMFByteStream *a2, int *a3)
{
  __int64 v6; // rcx
  CID3Writer *v7; // rax
  unsigned __int8 v8; // dl
  unsigned __int8 v9; // r8
  CID3Writer *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  wchar_t *v13; // rcx
  int v14; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  CMP3MediaStream *v24; // rax
  __int64 v25; // rdx
  CMP3MediaStream *v26; // rax
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
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

  _InterlockedIncrement(&dword_1801B979C);
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
  v7 = (CID3Writer *)operator new(0x128u);
  if ( v7 )
    v10 = CID3Writer::CID3Writer(v7, v8, v9);
  else
    v10 = 0;
  *((_QWORD *)this + 47) = v10;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CMP3MediaSink::CMP3MediaSink", 67);
  v12 = *((_QWORD *)this + 47);
  if ( !v12 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSink::CMP3MediaSink", 67, -2147024882);
    }
    if ( g_wppLevels )
    {
      v17 = 13;
LABEL_77:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids,
        this,
        -2147024882);
      goto LABEL_78;
    }
    goto LABEL_78;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
  v18 = *((_QWORD *)this + 47);
  v46.vt = 31;
  v46.hVal.QuadPart = (LONGLONG)L"MPG/3";
  v45 = CID3Writer::SetProperty((CID3Writer *)(v18 + 8), L"TFLT", &v46);
  v14 = v45;
  if ( v45 < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != v14 )
        CallStackContext::TraceFailure(v22, "CMP3MediaSink::CMP3MediaSink", 72, v14);
    }
    if ( !g_wppLevels )
      goto LABEL_78;
    v23 = 14;
    goto LABEL_26;
  }
  v24 = (CMP3MediaStream *)operator new(0xD0u);
  if ( v24 )
  {
    v26 = CMP3MediaStream::CMP3MediaStream(v24, this, &v45);
    *((_QWORD *)this + 49) = v26;
    if ( v26 )
    {
      v14 = v45;
      if ( v45 >= 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v26 + 2);
        v14 = CTFifo<CAC3StreamSink::CMarkerItem *>::Initialize((char *)this + 184);
        if ( v14 >= 0 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)this + 60) = EventW;
          if ( EventW )
            goto LABEL_78;
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          if ( v14 >= 0 )
            goto LABEL_78;
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
              v37 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v37 + 8) )
          {
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
            if ( *((_DWORD *)v39 + 499) != v14 )
              CallStackContext::TraceFailure(v39, "CMP3MediaSink::CMP3MediaSink", 84, v14);
          }
          if ( !g_wppLevels )
            goto LABEL_78;
          v23 = 18;
        }
        else
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != v14 )
              CallStackContext::TraceFailure(v33, "CMP3MediaSink::CMP3MediaSink", 79, v14);
          }
          if ( !g_wppLevels )
            goto LABEL_78;
          v23 = 17;
        }
      }
      else
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( v14 < 0 && *((_DWORD *)v29 + 499) != v14 )
            CallStackContext::TraceFailure(v29, "CMP3MediaSink::CMP3MediaSink", 76, v14);
        }
        if ( !g_wppLevels )
          goto LABEL_78;
        v23 = 16;
      }
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v14);
      goto LABEL_78;
    }
  }
  else
  {
    *((_QWORD *)this + 49) = 0;
  }
  v40 = (wchar_t *)CallStackTracing::s_wpInstance;
  v14 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
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
    if ( *((_DWORD *)v42 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v42, "CMP3MediaSink::CMP3MediaSink", 75, -2147024882);
  }
  if ( g_wppLevels )
  {
    v17 = 15;
    goto LABEL_77;
  }
LABEL_78:
  *a3 = v14;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return this;
}

```

## disassembly

```asm
0x1801258b0  mov     [rsp+arg_8], rbx
0x1801258b5  push    rbp
0x1801258b6  push    rsi
0x1801258b7  push    rdi
0x1801258b8  push    r12
0x1801258ba  push    r14
0x1801258bc  sub     rsp, 60h
0x1801258c0  mov     rax, cs:__security_cookie
0x1801258c7  xor     rax, rsp
0x1801258ca  mov     [rsp+88h+var_38], rax
0x1801258cf  mov     r14, r8
0x1801258d2  mov     rbx, rdx
0x1801258d5  mov     rdi, rcx
0x1801258d8  lock inc cs:dword_1801B979C
0x1801258df  lea     rax, ??_7CMP3MediaSink@@6BIMFFinalizableMediaSink@@@; const CMP3MediaSink::`vftable'{for `IMFFinalizableMediaSink'}
0x1801258e6  mov     [rcx], rax
0x1801258e9  lea     rax, ??_7CMP3MediaSink@@6BIMFClockStateSink@@@; const CMP3MediaSink::`vftable'{for `IMFClockStateSink'}
0x1801258f0  mov     [rcx+8], rax
0x1801258f4  lea     rax, ??_7CMP3MediaSink@@6BIMFGetService@@@; const CMP3MediaSink::`vftable'{for `IMFGetService'}
0x1801258fb  mov     [rcx+10h], rax
0x1801258ff  lea     rax, ??_7CMP3MediaSink@@6BIMFMetadataProvider@@@; const CMP3MediaSink::`vftable'{for `IMFMetadataProvider'}
0x180125906  mov     [rcx+18h], rax
0x18012590a  lea     rax, ??_7CMP3MediaSink@@6BIMFStreamingSinkConfig@@@; const CMP3MediaSink::`vftable'{for `IMFStreamingSinkConfig'}
0x180125911  mov     [rcx+20h], rax
0x180125915  add     rcx, 28h ; '('; this
0x180125919  call    ??0OnWriteSampleAsyncCallback@CMP3MediaSink@@QEAA@XZ; CMP3MediaSink::OnWriteSampleAsyncCallback::OnWriteSampleAsyncCallback(void)
0x18012591e  lea     rcx, [rdi+30h]; this
0x180125922  call    ??0DoFinalizeAsyncCallback@CMP3MediaSink@@QEAA@XZ; CMP3MediaSink::DoFinalizeAsyncCallback::DoFinalizeAsyncCallback(void)
0x180125927  lea     rcx, [rdi+38h]; this
0x18012592b  call    ??0OnWriteMetadataAsyncCallback@CMP3MediaSink@@QEAA@XZ; CMP3MediaSink::OnWriteMetadataAsyncCallback::OnWriteMetadataAsyncCallback(void)
0x180125930  xor     ebp, ebp
0x180125932  lea     rcx, [rdi+48h]; lpCriticalSection
0x180125936  mov     [rdi+40h], ebp
0x180125939  call    cs:__imp_InitializeCriticalSection
0x180125940  nop     dword ptr [rax+rax+00h]
0x180125945  mov     [rdi+80h], rbx
0x18012594c  lea     rcx, [rdi+90h]; lpCriticalSection
0x180125953  lea     rbx, [rdi+88h]
0x18012595a  mov     dword ptr [rdi+70h], 3
0x180125961  mov     [rbx], rbp
0x180125964  mov     [rdi+78h], rbp
0x180125968  call    cs:__imp_InitializeCriticalSection
0x18012596f  nop     dword ptr [rax+rax+00h]
0x180125974  lea     rsi, [rdi+0B8h]
0x18012597b  xorps   xmm0, xmm0
0x18012597e  lea     rax, ??_7?$CTFifo@PEAUIMFSample@@@@6B@; const CTFifo<IMFSample *>::`vftable'
0x180125985  mov     [rsi], rax
0x180125988  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012598c  mov     [rsi+8], rbp
0x180125990  mov     [rsi+10h], rbp
0x180125994  mov     [rsi+18h], ebp
0x180125997  mov     [rsi+0B8h], rbp
0x18012599e  mov     [rsi+0A8h], rbp
0x1801259a5  mov     [rdi+1D0h], rax
0x1801259ac  mov     [rdi+1D8h], rax
0x1801259b3  xor     eax, eax
0x1801259b5  mov     [rdi+178h], rbp
0x1801259bc  mov     [rdi+180h], ebp
0x1801259c2  mov     [rdi+188h], rbp
0x1801259c9  mov     [rdi+190h], rbp
0x1801259d0  mov     [rdi+198h], rbp
0x1801259d7  mov     [rdi+1A0h], bp
0x1801259de  mov     [rdi+1E0h], rbp
0x1801259e5  movups  xmmword ptr [rdi+1A8h], xmm0
0x1801259ec  mov     qword ptr [rsp+88h+var_50+10h], rax
0x1801259f1  movups  xmmword ptr [rdi+1B8h], xmm0
0x1801259f8  mov     [rdi+1C8h], rax
0x1801259ff  mov     rcx, [rdi+80h]
0x180125a06  movups  xmmword ptr [rsp+88h+var_50], xmm0
0x180125a0b  mov     rax, [rcx]
0x180125a0e  mov     rax, [rax+8]
0x180125a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125a17  mov     rcx, [rdi+80h]
0x180125a1e  lea     rdx, _GUID_8feed468_6f7e_440d_869a_49bdd283ad0d
0x180125a25  mov     r8, rbx
0x180125a28  mov     rax, [rcx]
0x180125a2b  mov     rax, [rax]
0x180125a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125a33  mov     ecx, 128h; Size
0x180125a38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180125a3d  test    rax, rax
0x180125a40  jz      short loc_180125A4C
0x180125a42  mov     rcx, rax; this
0x180125a45  call    ??0CID3Writer@@QEAA@EE@Z; CID3Writer::CID3Writer(uchar,uchar)
0x180125a4a  jmp     short loc_180125A4F
0x180125a4c  mov     rax, rbp
0x180125a4f  lea     r12, aCmp3mediasinkC; "CMP3MediaSink::CMP3MediaSink"
0x180125a56  mov     [rdi+178h], rax
0x180125a5d  mov     rdx, r12; char *
0x180125a60  lea     rcx, [rsp+88h+var_58]; this
0x180125a65  mov     r8d, 43h ; 'C'; int
0x180125a6b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180125a70  mov     rax, [rdi+178h]
0x180125a77  test    rax, rax
0x180125a7a  jnz     loc_180125B18
0x180125a80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125a87  mov     esi, 8007000Eh
0x180125a8c  mov     ebx, esi
0x180125a8e  test    rcx, rcx
0x180125a91  jnz     short loc_180125ADA
0x180125a93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180125a9a  nop     dword ptr [rax+rax+00h]
0x180125a9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180125aa6  mov     rcx, rax
0x180125aa9  test    rax, rax
0x180125aac  jz      short loc_180125ACC
0x180125aae  mov     rax, [rax]
0x180125ab1  mov     edx, 7F0h
0x180125ab6  mov     rax, [rax+8]
0x180125aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125abf  test    eax, eax
0x180125ac1  jz      short loc_180125ACC
0x180125ac3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125aca  jmp     short loc_180125ADA
0x180125acc  lea     rcx, qword_1801B97E0; this
0x180125ad3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180125ada  cmp     [rcx+8], bpl
0x180125ade  jz      short loc_180125B01
0x180125ae0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180125ae5  cmp     [rax+7CCh], esi
0x180125aeb  jz      short loc_180125B01
0x180125aed  mov     r9d, esi; int
0x180125af0  mov     r8d, 43h ; 'C'; int
0x180125af6  mov     rdx, r12; char *
0x180125af9  mov     rcx, rax; this
0x180125afc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180125b01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180125b08  jb      loc_180125EFC
0x180125b0e  mov     edx, 0Dh
0x180125b13  jmp     loc_180125EDE
0x180125b18  lock inc dword ptr [rax+10h]
0x180125b1c  mov     rcx, [rdi+178h]
0x180125b23  lea     r8, [rsp+88h+var_50]; struct tagPROPVARIANT *
0x180125b28  mov     eax, 1Fh
0x180125b2d  lea     rdx, aTflt; "TFLT"
0x180125b34  mov     word ptr [rsp+88h+var_50], ax
0x180125b39  add     rcx, 8; this
0x180125b3d  lea     rax, aMpg3; "MPG/3"
0x180125b44  mov     qword ptr [rsp+88h+var_50+8], rax
0x180125b49  call    ?SetProperty@CID3Writer@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z; CID3Writer::SetProperty(ushort const *,tagPROPVARIANT const *)
0x180125b4e  mov     [rsp+88h+var_54], eax
0x180125b52  mov     ebx, eax
0x180125b54  test    eax, eax
0x180125b56  jns     loc_180125BF1
0x180125b5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125b63  test    rcx, rcx
0x180125b66  jnz     short loc_180125BAF
0x180125b68  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180125b6f  nop     dword ptr [rax+rax+00h]
0x180125b74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180125b7b  mov     rcx, rax
0x180125b7e  test    rax, rax
0x180125b81  jz      short loc_180125BA1
0x180125b83  mov     rax, [rax]
0x180125b86  mov     edx, 7F0h
0x180125b8b  mov     rax, [rax+8]
0x180125b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125b94  test    eax, eax
0x180125b96  jz      short loc_180125BA1
0x180125b98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125b9f  jmp     short loc_180125BAF
0x180125ba1  lea     rcx, qword_1801B97E0; this
0x180125ba8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180125baf  cmp     [rcx+8], bpl
0x180125bb3  jz      short loc_180125BD6
0x180125bb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180125bba  cmp     [rax+7CCh], ebx
0x180125bc0  jz      short loc_180125BD6
0x180125bc2  mov     r9d, ebx; int
0x180125bc5  mov     r8d, 48h ; 'H'; int
0x180125bcb  mov     rdx, r12; char *
0x180125bce  mov     rcx, rax; this
0x180125bd1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180125bd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180125bdd  jb      loc_180125EFC
0x180125be3  mov     edx, 0Eh
0x180125be8  mov     [rsp+88h+var_68], ebx
0x180125bec  jmp     loc_180125EE2
0x180125bf1  mov     ecx, 0D0h; Size
0x180125bf6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180125bfb  test    rax, rax
0x180125bfe  jz      loc_180125E48
0x180125c04  lea     r8, [rsp+88h+var_54]; int *
0x180125c09  mov     rdx, rdi; struct CMP3MediaSink *
0x180125c0c  mov     rcx, rax; this
0x180125c0f  call    ??0CMP3MediaStream@@QEAA@PEAVCMP3MediaSink@@PEAJ@Z; CMP3MediaStream::CMP3MediaStream(CMP3MediaSink *,long *)
0x180125c14  mov     [rdi+188h], rax
0x180125c1b  test    rax, rax
0x180125c1e  jz      loc_180125E4F
0x180125c24  mov     ebx, [rsp+88h+var_54]
0x180125c28  test    ebx, ebx
0x180125c2a  jns     loc_180125CC5
0x180125c30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125c37  test    rcx, rcx
0x180125c3a  jnz     short loc_180125C83
0x180125c3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180125c43  nop     dword ptr [rax+rax+00h]
0x180125c48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180125c4f  mov     rcx, rax
0x180125c52  test    rax, rax
0x180125c55  jz      short loc_180125C75
0x180125c57  mov     rax, [rax]
0x180125c5a  mov     edx, 7F0h
0x180125c5f  mov     rax, [rax+8]
0x180125c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125c68  test    eax, eax
0x180125c6a  jz      short loc_180125C75
0x180125c6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125c73  jmp     short loc_180125C83
0x180125c75  lea     rcx, qword_1801B97E0; this
0x180125c7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180125c83  cmp     [rcx+8], bpl
0x180125c87  jz      short loc_180125CAE
0x180125c89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180125c8e  test    ebx, ebx
0x180125c90  jns     short loc_180125CAE
0x180125c92  cmp     [rax+7CCh], ebx
0x180125c98  jz      short loc_180125CAE
0x180125c9a  mov     r9d, ebx; int
0x180125c9d  mov     r8d, 4Ch ; 'L'; int
0x180125ca3  mov     rdx, r12; char *
0x180125ca6  mov     rcx, rax; this
0x180125ca9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180125cae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180125cb5  jb      loc_180125EFC
0x180125cbb  mov     edx, 10h
0x180125cc0  jmp     loc_180125BE8
0x180125cc5  lock inc dword ptr [rax+8]
0x180125cc9  mov     rcx, rsi
0x180125ccc  call    ?Initialize@?$CTFifo@PEAVCMarkerItem@CAC3StreamSink@@@@QEAAJKH@Z; CTFifo<CAC3StreamSink::CMarkerItem *>::Initialize(ulong,int)
0x180125cd1  mov     ebx, eax
0x180125cd3  test    eax, eax
0x180125cd5  jns     loc_180125D6C
0x180125cdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125ce2  test    rcx, rcx
0x180125ce5  jnz     short loc_180125D2E
0x180125ce7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180125cee  nop     dword ptr [rax+rax+00h]
0x180125cf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180125cfa  mov     rcx, rax
0x180125cfd  test    rax, rax
0x180125d00  jz      short loc_180125D20
0x180125d02  mov     rax, [rax]
0x180125d05  mov     edx, 7F0h
0x180125d0a  mov     rax, [rax+8]
0x180125d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d13  test    eax, eax
0x180125d15  jz      short loc_180125D20
0x180125d17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125d1e  jmp     short loc_180125D2E
0x180125d20  lea     rcx, qword_1801B97E0; this
0x180125d27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180125d2e  cmp     [rcx+8], bpl
0x180125d32  jz      short loc_180125D55
0x180125d34  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180125d39  cmp     [rax+7CCh], ebx
0x180125d3f  jz      short loc_180125D55
0x180125d41  mov     r9d, ebx; int
0x180125d44  mov     r8d, 4Fh ; 'O'; int
0x180125d4a  mov     rdx, r12; char *
0x180125d4d  mov     rcx, rax; this
0x180125d50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180125d55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180125d5c  jb      loc_180125EFC
0x180125d62  mov     edx, 11h
0x180125d67  jmp     loc_180125BE8
0x180125d6c  xor     r9d, r9d; lpName
0x180125d6f  xor     r8d, r8d; bInitialState
0x180125d72  xor     ecx, ecx; lpEventAttributes
0x180125d74  lea     edx, [r9+1]; bManualReset
0x180125d78  call    cs:__imp_CreateEventW
0x180125d7f  nop     dword ptr [rax+rax+00h]
0x180125d84  mov     [rdi+1E0h], rax
0x180125d8b  test    rax, rax
0x180125d8e  jnz     loc_180125EFC
0x180125d94  call    cs:__imp_GetLastError
0x180125d9b  nop     dword ptr [rax+rax+00h]
0x180125da0  mov     ebx, eax
0x180125da2  test    eax, eax
0x180125da4  jle     short loc_180125DAF
0x180125da6  movzx   ebx, ax
0x180125da9  or      ebx, 80070000h
0x180125daf  test    ebx, ebx
0x180125db1  jns     loc_180125EFC
0x180125db7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180125dbe  test    rcx, rcx
0x180125dc1  jnz     short loc_180125E0A
0x180125dc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180125dca  nop     dword ptr [rax+rax+00h]
0x180125dcf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180125dd6  mov     rcx, rax
0x180125dd9  test    rax, rax
0x180125ddc  jz      short loc_180125DFC
0x180125dde  mov     rax, [rax]
0x180125de1  mov     edx, 7F0h
0x180125de6  mov     rax, [rax+8]
0x180125dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125def  test    eax, eax
0x180125df1  jz      short loc_180125DFC
0x180125df3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
