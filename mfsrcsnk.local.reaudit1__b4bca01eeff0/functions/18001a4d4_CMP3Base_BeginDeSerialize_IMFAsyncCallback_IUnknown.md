# CMP3Base::BeginDeSerialize(IMFAsyncCallback *,IUnknown *)

- ea: `0x18001a4d4`
- end: `0x18001a8eb`
- name: `?BeginDeSerialize@CMP3Base@@QEAAJPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1047`
- prototype: `__int64 __fastcall(CMP3Base *__hidden this, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009771c`
- `0x1800cbf30`

## callees

- `0x180005cf4`
- `0x180018a3c`
- `0x18001a4d4`
- `0x18001c6c0`
- `0x18004f030`
- `0x180077708`
- `0x180079680`
- `0x180110a94`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a646`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a646`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a61f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a6a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a6a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a721`
- `MFPlat!MFLockPlatform` at `0x18001a572`
- `MFPlat!MFLockPlatform` at `0x18001a572`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a775`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a7b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a775`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a7b7`

## string_xrefs

- `0x18001a4f9`: `CMP3Base::BeginDeSerialize`
- `0x18001a5fc`: `CByteStreamCacheReaderEx::GetCurrentPosition`

## pseudocode

```c
__int64 __fastcall CMP3Base::BeginDeSerialize(CMP3Base *this, struct IMFAsyncCallback *a2, struct IUnknown *a3)
{
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  tagMFASYNCRESULT *v9; // rax
  __int64 v10; // rdx
  tagMFASYNCRESULT *v11; // rbx
  __int64 v12; // rcx
  CallStackTracing *v13; // rcx
  char *v14; // r14
  __int64 v15; // rbx
  struct CallStackContext *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  struct CallStackContext *v20; // rax
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // rdx
  int v24; // ebx
  struct CallStackContext *v25; // rax
  int v26; // ecx
  int v27; // ecx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax

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
      *((_QWORD *)ThreadRelativeContext + v8) = "CMP3Base::BeginDeSerialize";
      *((_DWORD *)ThreadRelativeContext + 2 * v8 + 2) = 129;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v9 = (tagMFASYNCRESULT *)operator new(0x68u);
  v11 = v9;
  if ( !v9 )
  {
    v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    v24 = -2147024882;
    if ( *((_BYTE *)v29 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v34 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v34, "CMP3Base::BeginDeSerialize", 137, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_d18bbb785de430394c1967457ee8924f_Traceguids,
        this,
        -2147024882);
    v14 = (char *)this + 48;
    goto LABEL_43;
  }
  tagMFASYNCRESULT::tagMFASYNCRESULT(v9);
  *(_QWORD *)(v12 + 64) = &CMFRefCounted::`vftable';
  *(_DWORD *)(v12 + 72) = 0;
  *(_QWORD *)v12 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
  *(_QWORD *)(v12 + 64) = &CAsyncResult::`vftable'{for `CMFRefCounted'};
  *(_DWORD *)(v12 + 96) = 0;
  MFLockPlatform();
  HIDWORD(v11[1].overlapped.hEvent) = 0;
  v11->hrStatusResult = 0;
  v11->hEvent = 0;
  v11[1].overlapped.InternalHigh = 0;
  v11[1].overlapped.Pointer = 0;
  v11->pCallback = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IMFAsyncCallback *))a2->lpVtbl->AddRef)(a2);
  *(_OWORD *)&v11->overlapped.Internal = 0;
  *(_OWORD *)&v11->overlapped.Offset = 0;
  v11->dwBytesTransferred = 0;
  ((void (__fastcall *)(tagMFASYNCRESULT *))v11->AsyncResult.lpVtbl->AddRef)(v11);
  v13 = CallStackTracing::s_wpInstance;
  v14 = (char *)this + 48;
  *((_QWORD *)this + 6) = v11;
  v15 = *((_QWORD *)this + 5);
  if ( !v13 )
  {
    CallStackTracing::InitInstance();
    v13 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v16 = CallStackTracing::GetThreadRelativeContext(v13);
    v17 = *((unsigned int *)v16 + 497);
    if ( (unsigned int)v17 < *((_DWORD *)v16 + 498) )
    {
      v18 = 2 * v17;
      *((_QWORD *)v16 + v18) = "CByteStreamCacheReaderEx::GetCurrentPosition";
      *((_DWORD *)v16 + 2 * v18 + 2) = 439;
    }
    ++*((_DWORD *)v16 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 568));
  v19 = *(_QWORD *)(v15 + 512);
  if ( v19 == -1 )
    v19 = *(_QWORD *)(v15 + 504);
  *((_QWORD *)this + 3) = v19;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 568));
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v21 = *((_DWORD *)v20 + 497);
    if ( v21 )
    {
      v22 = v21 - 1;
      *((_DWORD *)v20 + 497) = v22;
      if ( !v22 )
      {
        *((_DWORD *)v20 + 497) = 0;
        *((_QWORD *)v20 + 252) = 0;
        *((_DWORD *)v20 + 499) = 0;
        *((GUID *)v20 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v20 + 506) = 0;
        *((_DWORD *)v20 + 496) = GetCurrentThreadId();
      }
    }
  }
  v24 = (*(__int64 (__fastcall **)(CMP3Base *))(*(_QWORD *)this + 48LL))(this);
  if ( v24 < 0 )
  {
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
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
      if ( *((_DWORD *)v33 + 499) != v24 )
        CallStackContext::TraceFailure(v33, "CMP3Base::BeginDeSerialize", 145, v24);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d18bbb785de430394c1967457ee8924f_Traceguids, this, v24);
LABEL_43:
    ComSmartPtr<CBaseStreamSink>::operator=(v14);
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v25 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v26 = *((_DWORD *)v25 + 497);
    if ( v26 )
    {
      v27 = v26 - 1;
      *((_DWORD *)v25 + 497) = v27;
      if ( !v27 )
      {
        *((_DWORD *)v25 + 497) = 0;
        *((_QWORD *)v25 + 252) = 0;
        *((_DWORD *)v25 + 499) = 0;
        *((GUID *)v25 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v25 + 506) = 0;
        *((_DWORD *)v25 + 496) = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18001a4d4  push    rbx
0x18001a4d6  push    rbp
0x18001a4d7  push    rsi
0x18001a4d8  push    rdi
0x18001a4d9  push    r14
0x18001a4db  push    r15
0x18001a4dd  sub     rsp, 38h
0x18001a4e1  mov     rsi, rcx
0x18001a4e4  xor     ebp, ebp
0x18001a4e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a4ed  mov     rdi, rdx
0x18001a4f0  test    rcx, rcx
0x18001a4f3  jz      loc_18001A743
0x18001a4f9  lea     r15, aCmp3baseBegind; "CMP3Base::BeginDeSerialize"
0x18001a500  cmp     [rcx+8], bpl
0x18001a504  jz      short loc_18001A52E
0x18001a506  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a50b  mov     ecx, [rax+7C4h]
0x18001a511  cmp     ecx, [rax+7C8h]
0x18001a517  jnb     short loc_18001A528
0x18001a519  add     rcx, rcx
0x18001a51c  mov     [rax+rcx*8], r15
0x18001a520  mov     dword ptr [rax+rcx*8+8], 81h
0x18001a528  inc     dword ptr [rax+7C4h]
0x18001a52e  mov     ecx, 68h ; 'h'; Size
0x18001a533  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a538  mov     rbx, rax
0x18001a53b  test    rax, rax
0x18001a53e  jz      loc_18001A765
0x18001a544  mov     rcx, rax; this
0x18001a547  call    ??0tagMFASYNCRESULT@@QEAA@XZ; tagMFASYNCRESULT::tagMFASYNCRESULT(void)
0x18001a54c  lea     rax, ??_7CMFRefCounted@@6B@; const CMFRefCounted::`vftable'
0x18001a553  mov     [rcx+40h], rax
0x18001a557  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x18001a55e  mov     [rcx+48h], ebp
0x18001a561  mov     [rcx], rax
0x18001a564  lea     rax, ??_7CAsyncResult@@6BCMFRefCounted@@@; const CAsyncResult::`vftable'{for `CMFRefCounted'}
0x18001a56b  mov     [rcx+40h], rax
0x18001a56f  mov     [rcx+60h], ebp
0x18001a572  call    cs:__imp_MFLockPlatform
0x18001a579  nop     dword ptr [rax+rax+00h]
0x18001a57e  mov     [rbx+64h], ebp
0x18001a581  mov     [rbx+30h], ebp
0x18001a584  mov     [rbx+38h], rbp
0x18001a588  mov     [rbx+50h], rbp
0x18001a58c  mov     [rbx+58h], rbp
0x18001a590  mov     [rbx+28h], rdi
0x18001a594  test    rdi, rdi
0x18001a597  jz      short loc_18001A5A8
0x18001a599  mov     rax, [rdi]
0x18001a59c  mov     rcx, rdi
0x18001a59f  mov     rax, [rax+8]
0x18001a5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5a8  xorps   xmm0, xmm0
0x18001a5ab  mov     rcx, rbx
0x18001a5ae  movups  xmmword ptr [rbx+8], xmm0
0x18001a5b2  movups  xmmword ptr [rbx+18h], xmm0
0x18001a5b6  mov     [rbx+34h], ebp
0x18001a5b9  mov     rax, [rbx]
0x18001a5bc  mov     rax, [rax+8]
0x18001a5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a5cc  lea     r14, [rsi+30h]
0x18001a5d0  mov     [r14], rbx
0x18001a5d3  mov     rbx, [rsi+28h]
0x18001a5d7  test    rcx, rcx
0x18001a5da  jz      loc_18001A754
0x18001a5e0  cmp     [rcx+8], bpl
0x18001a5e4  jz      short loc_18001A615
0x18001a5e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a5eb  mov     ecx, [rax+7C4h]
0x18001a5f1  cmp     ecx, [rax+7C8h]
0x18001a5f7  jnb     short loc_18001A60F
0x18001a5f9  add     rcx, rcx
0x18001a5fc  lea     rdx, aCbytestreamcac_21; "CByteStreamCacheReaderEx::GetCurrentPos"...
0x18001a603  mov     [rax+rcx*8], rdx
0x18001a607  mov     dword ptr [rax+rcx*8+8], 1B7h
0x18001a60f  inc     dword ptr [rax+7C4h]
0x18001a615  lea     rdi, [rbx+238h]
0x18001a61c  mov     rcx, rdi; lpCriticalSection
0x18001a61f  call    cs:__imp_EnterCriticalSection
0x18001a626  nop     dword ptr [rax+rax+00h]
0x18001a62b  mov     rax, [rbx+200h]
0x18001a632  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a636  jnz     short loc_18001A63F
0x18001a638  mov     rax, [rbx+1F8h]
0x18001a63f  mov     rcx, rdi; lpCriticalSection
0x18001a642  mov     [rsi+18h], rax
0x18001a646  call    cs:__imp_LeaveCriticalSection
0x18001a64d  nop     dword ptr [rax+rax+00h]
0x18001a652  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a659  cmp     [rcx+8], bpl
0x18001a65d  jz      short loc_18001A6B6
0x18001a65f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a664  mov     rbx, rax
0x18001a667  mov     ecx, [rax+7C4h]
0x18001a66d  test    ecx, ecx
0x18001a66f  jz      short loc_18001A6B6
0x18001a671  sub     ecx, 1
0x18001a674  mov     [rax+7C4h], ecx
0x18001a67a  jnz     short loc_18001A6B6
0x18001a67c  mov     [rax+7C4h], ebp
0x18001a682  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001a689  mov     [rax+7E0h], rbp
0x18001a690  mov     [rax+7CCh], ebp
0x18001a696  movdqu  xmmword ptr [rax+7D0h], xmm0
0x18001a69e  mov     [rax+7E8h], ebp
0x18001a6a4  call    cs:__imp_GetCurrentThreadId
0x18001a6ab  nop     dword ptr [rax+rax+00h]
0x18001a6b0  mov     [rbx+7C0h], eax
0x18001a6b6  mov     rax, [rsi]
0x18001a6b9  mov     rcx, rsi
0x18001a6bc  mov     rax, [rax+30h]
0x18001a6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c5  mov     ebx, eax
0x18001a6c7  test    eax, eax
0x18001a6c9  js      loc_18001A7A7
0x18001a6cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a6d6  cmp     [rcx+8], bpl
0x18001a6da  jz      short loc_18001A733
0x18001a6dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a6e1  mov     rdi, rax
0x18001a6e4  mov     ecx, [rax+7C4h]
0x18001a6ea  test    ecx, ecx
0x18001a6ec  jz      short loc_18001A733
0x18001a6ee  sub     ecx, 1
0x18001a6f1  mov     [rax+7C4h], ecx
0x18001a6f7  jnz     short loc_18001A733
0x18001a6f9  mov     [rax+7C4h], ebp
0x18001a6ff  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001a706  mov     [rax+7E0h], rbp
0x18001a70d  mov     [rax+7CCh], ebp
0x18001a713  movdqu  xmmword ptr [rax+7D0h], xmm0
0x18001a71b  mov     [rax+7E8h], ebp
0x18001a721  call    cs:__imp_GetCurrentThreadId
0x18001a728  nop     dword ptr [rax+rax+00h]
0x18001a72d  mov     [rdi+7C0h], eax
0x18001a733  mov     eax, ebx
0x18001a735  add     rsp, 38h
0x18001a739  pop     r15
0x18001a73b  pop     r14
0x18001a73d  pop     rdi
0x18001a73e  pop     rsi
0x18001a73f  pop     rbp
0x18001a740  pop     rbx
0x18001a741  retn
0x18001a743  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a748  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a74f  jmp     loc_18001A4F9
0x18001a754  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a759  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a760  jmp     loc_18001A5E0
0x18001a765  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a76c  test    rcx, rcx
0x18001a76f  jnz     loc_18001A8AA
0x18001a775  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a77c  nop     dword ptr [rax+rax+00h]
0x18001a781  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a788  mov     rcx, rax
0x18001a78b  test    rax, rax
0x18001a78e  jnz     loc_18001A88A
0x18001a794  lea     rcx, qword_1801B97E0
0x18001a79b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a7a2  jmp     loc_18001A8AA
0x18001a7a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a7ae  test    rcx, rcx
0x18001a7b1  jnz     loc_18001A84B
0x18001a7b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a7be  nop     dword ptr [rax+rax+00h]
0x18001a7c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a7ca  mov     rcx, rax
0x18001a7cd  test    rax, rax
0x18001a7d0  jnz     short loc_18001A82F
0x18001a7d2  lea     rcx, qword_1801B97E0
0x18001a7d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a7e0  jmp     short loc_18001A84B
0x18001a7e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a7e7  cmp     [rax+7CCh], ebx
0x18001a7ed  jz      short loc_18001A851
0x18001a7ef  mov     r9d, ebx; int
0x18001a7f2  mov     r8d, 91h; int
0x18001a7f8  mov     rdx, r15; char *
0x18001a7fb  mov     rcx, rax; this
0x18001a7fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a803  jmp     short loc_18001A851
0x18001a805  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a80a  cmp     [rax+7CCh], ebx
0x18001a810  jz      loc_18001A8B9
0x18001a816  mov     r9d, ebx; int
0x18001a819  mov     r8d, 89h; int
0x18001a81f  mov     rdx, r15; char *
0x18001a822  mov     rcx, rax; this
0x18001a825  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a82a  jmp     loc_18001A8B9
0x18001a82f  mov     rax, [rax]
0x18001a832  mov     edx, 7F0h
0x18001a837  mov     rax, [rax+8]
0x18001a83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a840  test    eax, eax
0x18001a842  jz      short loc_18001A7D2
0x18001a844  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a84b  cmp     [rcx+8], bpl
0x18001a84f  jnz     short loc_18001A7E2
0x18001a851  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a858  jb      short loc_18001A87D
0x18001a85a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a861  lea     r8, WPP_d18bbb785de430394c1967457ee8924f_Traceguids
0x18001a868  mov     edx, 11h
0x18001a86d  mov     [rsp+68h+var_48], ebx
0x18001a871  mov     r9, rsi
0x18001a874  mov     rcx, [rcx+10h]
0x18001a878  call    WPP_SF_qD
0x18001a87d  mov     rcx, r14
0x18001a880  call    ??4?$ComSmartPtr@VCBaseStreamSink@@@@QEAAPEAVCBaseStreamSink@@PEAV1@@Z; ComSmartPtr<CBaseStreamSink>::operator=(CBaseStreamSink *)
0x18001a885  jmp     loc_18001A6CF
0x18001a88a  mov     rax, [rax]
0x18001a88d  mov     edx, 7F0h
0x18001a892  mov     rax, [rax+8]
0x18001a896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a89b  test    eax, eax
0x18001a89d  jz      loc_18001A794
0x18001a8a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a8aa  mov     ebx, 8007000Eh
0x18001a8af  cmp     [rcx+8], bpl
0x18001a8b3  jnz     loc_18001A805
0x18001a8b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a8c0  jb      short loc_18001A8E5
0x18001a8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8c9  lea     r8, WPP_d18bbb785de430394c1967457ee8924f_Traceguids
0x18001a8d0  mov     edx, 0Fh
0x18001a8d5  mov     [rsp+68h+var_48], ebx
0x18001a8d9  mov     r9, rsi
0x18001a8dc  mov     rcx, [rcx+10h]
0x18001a8e0  call    WPP_SF_qD
0x18001a8e5  lea     r14, [rsi+30h]
0x18001a8e9  jmp     short loc_18001A87D
```
