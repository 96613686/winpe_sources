# CMP3Base::~CMP3Base(void)

- ea: `0x18002a3d0`
- end: `0x18002a7e4`
- name: `??1CMP3Base@@UEAA@XZ`
- size: `1044`
- prototype: `void __fastcall(CMP3Base *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a350`
- `0x180072318`
- `0x180074854`
- `0x18016b650`

## callees

- `0x18002a3d0`
- `0x180071a44`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a50c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a59b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a50c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a72b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a5e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a422`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a48e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a4f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a587`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a422`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a48e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a4f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a587`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a664`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a664`

## pseudocode

```c
void __fastcall CMP3Base::~CMP3Base(CMP3Base *this, __int64 a2)
{
  wchar_t *v2; // rbx
  CMP3Base *v3; // rsi
  wchar_t *v4; // rdi
  DWORD LastError; // ebp
  wchar_t *Value; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rdi
  DWORD v10; // ebp
  wchar_t *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // rdi
  DWORD v15; // ebp
  wchar_t *v16; // rax
  int v17; // eax
  int v18; // eax
  DWORD CurrentThreadId; // eax
  wchar_t *v20; // rdi
  DWORD v21; // ebp
  wchar_t *v22; // rax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  CallStackTracing *v27; // rax
  CallStackTracing *v28; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rax
  CallStackTracing *v31; // rcx
  __int64 v32; // rax
  CallStackTracing *v33; // rcx
  __int64 v34; // rax
  CallStackTracing *v35; // rcx
  __int64 v36; // rax

  v2 = (wchar_t *)CallStackTracing::s_wpInstance;
  v3 = this;
  *(_QWORD *)this = &CMP3Base::`vftable';
  if ( !v2 )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v27;
    this = v27;
    if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
    {
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v4 = v2 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v4 = Value;
    }
    else if ( !GetLastError() )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v29 = CallStackTracing::s_wpInstance;
      }
      v30 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
      if ( v30 )
        v4 = (wchar_t *)v30;
    }
    SetLastError(LastError);
    v7 = *((unsigned int *)v4 + 497);
    v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( (unsigned int)v7 < *((_DWORD *)v4 + 498) )
    {
      v8 = 2 * v7;
      this = (CMP3Base *)"CMP3Base::~CMP3Base";
      *(_QWORD *)&v4[4 * v8] = "CMP3Base::~CMP3Base";
      *(_DWORD *)&v4[4 * v8 + 4] = 54;
    }
    ++*((_DWORD *)v4 + 497);
  }
  if ( !v2 )
  {
    v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v28;
    if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
    {
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v9 = v2 + 104;
    v10 = GetLastError();
    v11 = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( v11 )
    {
      v9 = v11;
    }
    else if ( !GetLastError() )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v31 = CallStackTracing::s_wpInstance;
      }
      v32 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
      if ( v32 )
        v9 = (wchar_t *)v32;
    }
    SetLastError(v10);
    v12 = *((unsigned int *)v9 + 497);
    v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[4 * v13] = "CMP3Base::Clear";
      *(_DWORD *)&v9[4 * v13 + 4] = 123;
    }
    ++*((_DWORD *)v9 + 497);
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v14 = v2 + 104;
    v15 = GetLastError();
    v16 = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( v16 )
    {
      v14 = v16;
    }
    else if ( !GetLastError() )
    {
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v33 = CallStackTracing::s_wpInstance;
      }
      v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v33)(v33);
      if ( v34 )
        v14 = (wchar_t *)v34;
    }
    SetLastError(v15);
    v17 = *((_DWORD *)v14 + 497);
    v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( v17 )
    {
      v18 = v17 - 1;
      *((_DWORD *)v14 + 497) = v18;
      if ( !v18 )
      {
        *((_DWORD *)v14 + 497) = 0;
        *((_QWORD *)v14 + 252) = 0;
        *((_DWORD *)v14 + 499) = 0;
        *((GUID *)v14 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v14 + 506) = 0;
        CurrentThreadId = GetCurrentThreadId();
        v2 = (wchar_t *)CallStackTracing::s_wpInstance;
        *((_DWORD *)v14 + 496) = CurrentThreadId;
      }
    }
  }
  *((_DWORD *)v3 + 4) = 0;
  if ( *((_BYTE *)v2 + 8) )
  {
    v20 = v2 + 104;
    v21 = GetLastError();
    v22 = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( v22 )
    {
      v20 = v22;
    }
    else if ( !GetLastError() )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v35 = CallStackTracing::s_wpInstance;
      }
      v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v35)(v35);
      if ( v36 )
        v20 = (wchar_t *)v36;
    }
    SetLastError(v21);
    v23 = *((_DWORD *)v20 + 497);
    if ( v23 )
    {
      v24 = v23 - 1;
      *((_DWORD *)v20 + 497) = v24;
      if ( !v24 )
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
  v25 = *((_QWORD *)v3 + 6);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = *((_QWORD *)v3 + 5);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
}

```

## disassembly

```asm
0x18002a3d0  sub     rsp, 28h
0x18002a3d4  mov     [rsp+28h+arg_0], rbx
0x18002a3d9  lea     rax, ??_7CMP3Base@@6B@; const CMP3Base::`vftable'
0x18002a3e0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a3e7  mov     [rsp+28h+arg_10], rsi
0x18002a3ec  mov     rsi, rcx
0x18002a3ef  mov     [rsp+28h+var_8], r14
0x18002a3f4  mov     [rcx], rax
0x18002a3f7  test    rbx, rbx
0x18002a3fa  jz      loc_18002A638
0x18002a400  cmp     byte ptr [rbx+8], 0
0x18002a404  mov     [rsp+28h+arg_8], rbp
0x18002a409  mov     [rsp+28h+arg_18], rdi
0x18002a40e  jz      short loc_18002A46D
0x18002a410  lea     rdi, [rbx+0D0h]
0x18002a417  call    cs:__imp_GetLastError
0x18002a41d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002a420  mov     ebp, eax
0x18002a422  call    cs:__imp_TlsGetValue
0x18002a428  test    rax, rax
0x18002a42b  jz      loc_18002A690
0x18002a431  mov     rdi, rax
0x18002a434  mov     ecx, ebp; dwErrCode
0x18002a436  call    cs:__imp_SetLastError
0x18002a43c  mov     eax, [rdi+7C4h]
0x18002a442  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a449  cmp     eax, [rdi+7C8h]
0x18002a44f  jnb     short loc_18002A467
0x18002a451  add     rax, rax
0x18002a454  lea     rcx, aCmp3baseCmp3ba_0; "CMP3Base::~CMP3Base"
0x18002a45b  mov     [rdi+rax*8], rcx
0x18002a45f  mov     dword ptr [rdi+rax*8+8], 36h ; '6'
0x18002a467  inc     dword ptr [rdi+7C4h]
0x18002a46d  test    rbx, rbx
0x18002a470  jz      loc_18002A664
0x18002a476  cmp     byte ptr [rbx+8], 0
0x18002a47a  jz      short loc_18002A4D9
0x18002a47c  lea     rdi, [rbx+0D0h]
0x18002a483  call    cs:__imp_GetLastError
0x18002a489  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002a48c  mov     ebp, eax
0x18002a48e  call    cs:__imp_TlsGetValue
0x18002a494  test    rax, rax
0x18002a497  jz      loc_18002A6C5
0x18002a49d  mov     rdi, rax
0x18002a4a0  mov     ecx, ebp; dwErrCode
0x18002a4a2  call    cs:__imp_SetLastError
0x18002a4a8  mov     eax, [rdi+7C4h]
0x18002a4ae  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a4b5  cmp     eax, [rdi+7C8h]
0x18002a4bb  jnb     short loc_18002A4D3
0x18002a4bd  add     rax, rax
0x18002a4c0  lea     rcx, aCmp3baseClear; "CMP3Base::Clear"
0x18002a4c7  mov     [rdi+rax*8], rcx
0x18002a4cb  mov     dword ptr [rdi+rax*8+8], 7Bh ; '{'
0x18002a4d3  inc     dword ptr [rdi+7C4h]
0x18002a4d9  xor     r14d, r14d
0x18002a4dc  cmp     [rbx+8], r14b
0x18002a4e0  jz      loc_18002A56B
0x18002a4e6  lea     rdi, [rbx+0D0h]
0x18002a4ed  call    cs:__imp_GetLastError
0x18002a4f3  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002a4f6  mov     ebp, eax
0x18002a4f8  call    cs:__imp_TlsGetValue
0x18002a4fe  test    rax, rax
0x18002a501  jz      loc_18002A6FA
0x18002a507  mov     rdi, rax
0x18002a50a  mov     ecx, ebp; dwErrCode
0x18002a50c  call    cs:__imp_SetLastError
0x18002a512  mov     eax, [rdi+7C4h]
0x18002a518  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a51f  test    eax, eax
0x18002a521  jz      short loc_18002A56B
0x18002a523  sub     eax, 1
0x18002a526  mov     [rdi+7C4h], eax
0x18002a52c  jnz     short loc_18002A56B
0x18002a52e  mov     [rdi+7C4h], r14d
0x18002a535  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002a53c  mov     [rdi+7E0h], r14
0x18002a543  mov     [rdi+7CCh], r14d
0x18002a54a  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002a551  mov     [rdi+7E8h], r14d
0x18002a558  call    cs:__imp_GetCurrentThreadId
0x18002a55e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a565  mov     [rdi+7C0h], eax
0x18002a56b  mov     [rsi+10h], r14d
0x18002a56f  cmp     [rbx+8], r14b
0x18002a573  jz      short loc_18002A5EC
0x18002a575  lea     rdi, [rbx+0D0h]
0x18002a57c  call    cs:__imp_GetLastError
0x18002a582  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002a585  mov     ebp, eax
0x18002a587  call    cs:__imp_TlsGetValue
0x18002a58d  test    rax, rax
0x18002a590  jz      loc_18002A72B
0x18002a596  mov     rdi, rax
0x18002a599  mov     ecx, ebp; dwErrCode
0x18002a59b  call    cs:__imp_SetLastError
0x18002a5a1  mov     eax, [rdi+7C4h]
0x18002a5a7  test    eax, eax
0x18002a5a9  jz      short loc_18002A5EC
0x18002a5ab  sub     eax, 1
0x18002a5ae  mov     [rdi+7C4h], eax
0x18002a5b4  jnz     short loc_18002A5EC
0x18002a5b6  mov     [rdi+7C4h], r14d
0x18002a5bd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002a5c4  mov     [rdi+7E0h], r14
0x18002a5cb  mov     [rdi+7CCh], r14d
0x18002a5d2  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002a5d9  mov     [rdi+7E8h], r14d
0x18002a5e0  call    cs:__imp_GetCurrentThreadId
0x18002a5e6  mov     [rdi+7C0h], eax
0x18002a5ec  mov     rcx, [rsi+30h]
0x18002a5f0  mov     r14, [rsp+28h+var_8]
0x18002a5f5  mov     rdi, [rsp+28h+arg_18]
0x18002a5fa  mov     rbp, [rsp+28h+arg_8]
0x18002a5ff  mov     rbx, [rsp+28h+arg_0]
0x18002a604  test    rcx, rcx
0x18002a607  jz      short loc_18002A615
0x18002a609  mov     rax, [rcx]
0x18002a60c  mov     rax, [rax+10h]
0x18002a610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a615  mov     rcx, [rsi+28h]
0x18002a619  mov     rsi, [rsp+28h+arg_10]
0x18002a61e  test    rcx, rcx
0x18002a621  jz      short loc_18002A633
0x18002a623  mov     rax, [rcx]
0x18002a626  mov     rax, [rax+10h]
0x18002a62a  add     rsp, 28h
0x18002a62e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18002a633  add     rsp, 28h
0x18002a637  retn
0x18002a638  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a63e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a645  mov     rcx, rax
0x18002a648  test    rax, rax
0x18002a64b  jnz     loc_18002A79A
0x18002a651  lea     rbx, qword_1801B07E0
0x18002a658  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a65f  jmp     loc_18002A400
0x18002a664  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a66a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a671  mov     rcx, rax
0x18002a674  test    rax, rax
0x18002a677  jnz     loc_18002A7BF
0x18002a67d  lea     rbx, qword_1801B07E0
0x18002a684  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a68b  jmp     loc_18002A476
0x18002a690  call    cs:__imp_GetLastError
0x18002a696  test    eax, eax
0x18002a698  jnz     loc_18002A434
0x18002a69e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6a5  test    rcx, rcx
0x18002a6a8  jz      loc_18002A75C
0x18002a6ae  mov     rax, [rcx]
0x18002a6b1  mov     rax, [rax]
0x18002a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6b9  test    rax, rax
0x18002a6bc  cmovnz  rdi, rax
0x18002a6c0  jmp     loc_18002A434
0x18002a6c5  call    cs:__imp_GetLastError
0x18002a6cb  test    eax, eax
0x18002a6cd  jnz     loc_18002A4A0
0x18002a6d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6da  test    rcx, rcx
0x18002a6dd  jz      loc_18002A76D
0x18002a6e3  mov     rax, [rcx]
0x18002a6e6  mov     rax, [rax]
0x18002a6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6ee  test    rax, rax
0x18002a6f1  cmovnz  rdi, rax
0x18002a6f5  jmp     loc_18002A4A0
0x18002a6fa  call    cs:__imp_GetLastError
0x18002a700  test    eax, eax
0x18002a702  jnz     loc_18002A50A
0x18002a708  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a70f  test    rcx, rcx
0x18002a712  jz      short loc_18002A77E
0x18002a714  mov     rax, [rcx]
0x18002a717  mov     rax, [rax]
0x18002a71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a71f  test    rax, rax
0x18002a722  cmovnz  rdi, rax
0x18002a726  jmp     loc_18002A50A
0x18002a72b  call    cs:__imp_GetLastError
0x18002a731  test    eax, eax
0x18002a733  jnz     loc_18002A599
0x18002a739  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a740  test    rcx, rcx
0x18002a743  jz      short loc_18002A78C
0x18002a745  mov     rax, [rcx]
0x18002a748  mov     rax, [rax]
0x18002a74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a750  test    rax, rax
0x18002a753  cmovnz  rdi, rax
0x18002a757  jmp     loc_18002A599
0x18002a75c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002a761  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a768  jmp     loc_18002A6AE
0x18002a76d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002a772  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a779  jmp     loc_18002A6E3
0x18002a77e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002a783  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a78a  jmp     short loc_18002A714
0x18002a78c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002a791  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a798  jmp     short loc_18002A745
0x18002a79a  mov     rax, [rax]
0x18002a79d  mov     edx, 7F0h
0x18002a7a2  mov     rax, [rax+8]
0x18002a7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ab  test    eax, eax
0x18002a7ad  jz      loc_18002A651
0x18002a7b3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a7ba  jmp     loc_18002A400
0x18002a7bf  mov     rax, [rax]
0x18002a7c2  mov     edx, 7F0h
0x18002a7c7  mov     rax, [rax+8]
0x18002a7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7d0  test    eax, eax
0x18002a7d2  jz      loc_18002A67D
0x18002a7d8  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a7df  jmp     loc_18002A476
```
