# CMP3Base::~CMP3Base(void)

- ea: `0x18002e7a0`
- end: `0x18002ec31`
- name: `??1CMP3Base@@UEAA@XZ`
- size: `1169`
- prototype: `void __fastcall(CMP3Base *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e720`
- `0x180077d90`
- `0x18007a2a0`
- `0x180174720`

## callees

- `0x18002e7a0`
- `0x180077708`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e812`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e90c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e9b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e812`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e90c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e98c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e98c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e95e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ea02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e95e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ea02`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e7f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e876`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e8f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e99d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e7f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e876`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e8f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e99d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea93`

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
      v2 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v2 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18002e7a0  sub     rsp, 28h
0x18002e7a4  mov     [rsp+28h+arg_0], rbx
0x18002e7a9  lea     rax, ??_7CMP3Base@@6B@; const CMP3Base::`vftable'
0x18002e7b0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7b7  mov     [rsp+28h+arg_10], rsi
0x18002e7bc  mov     rsi, rcx
0x18002e7bf  mov     [rsp+28h+var_8], r14
0x18002e7c4  mov     [rcx], rax
0x18002e7c7  test    rbx, rbx
0x18002e7ca  jz      loc_18002EA61
0x18002e7d0  cmp     byte ptr [rbx+8], 0
0x18002e7d4  mov     [rsp+28h+arg_8], rbp
0x18002e7d9  mov     [rsp+28h+arg_18], rdi
0x18002e7de  jz      short loc_18002E84F
0x18002e7e0  lea     rdi, [rbx+0D0h]
0x18002e7e7  call    cs:__imp_GetLastError
0x18002e7ee  nop     dword ptr [rax+rax+00h]
0x18002e7f3  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002e7f6  mov     ebp, eax
0x18002e7f8  call    cs:__imp_TlsGetValue
0x18002e7ff  nop     dword ptr [rax+rax+00h]
0x18002e804  test    rax, rax
0x18002e807  jz      loc_18002EAC5
0x18002e80d  mov     rdi, rax
0x18002e810  mov     ecx, ebp; dwErrCode
0x18002e812  call    cs:__imp_SetLastError
0x18002e819  nop     dword ptr [rax+rax+00h]
0x18002e81e  mov     eax, [rdi+7C4h]
0x18002e824  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e82b  cmp     eax, [rdi+7C8h]
0x18002e831  jnb     short loc_18002E849
0x18002e833  add     rax, rax
0x18002e836  lea     rcx, aCmp3baseCmp3ba_0; "CMP3Base::~CMP3Base"
0x18002e83d  mov     [rdi+rax*8], rcx
0x18002e841  mov     dword ptr [rdi+rax*8+8], 36h ; '6'
0x18002e849  inc     dword ptr [rdi+7C4h]
0x18002e84f  test    rbx, rbx
0x18002e852  jz      loc_18002EA93
0x18002e858  cmp     byte ptr [rbx+8], 0
0x18002e85c  jz      short loc_18002E8CD
0x18002e85e  lea     rdi, [rbx+0D0h]
0x18002e865  call    cs:__imp_GetLastError
0x18002e86c  nop     dword ptr [rax+rax+00h]
0x18002e871  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002e874  mov     ebp, eax
0x18002e876  call    cs:__imp_TlsGetValue
0x18002e87d  nop     dword ptr [rax+rax+00h]
0x18002e882  test    rax, rax
0x18002e885  jz      loc_18002EB00
0x18002e88b  mov     rdi, rax
0x18002e88e  mov     ecx, ebp; dwErrCode
0x18002e890  call    cs:__imp_SetLastError
0x18002e897  nop     dword ptr [rax+rax+00h]
0x18002e89c  mov     eax, [rdi+7C4h]
0x18002e8a2  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8a9  cmp     eax, [rdi+7C8h]
0x18002e8af  jnb     short loc_18002E8C7
0x18002e8b1  add     rax, rax
0x18002e8b4  lea     rcx, aCmp3baseClear; "CMP3Base::Clear"
0x18002e8bb  mov     [rdi+rax*8], rcx
0x18002e8bf  mov     dword ptr [rdi+rax*8+8], 7Bh ; '{'
0x18002e8c7  inc     dword ptr [rdi+7C4h]
0x18002e8cd  xor     r14d, r14d
0x18002e8d0  cmp     [rbx+8], r14b
0x18002e8d4  jz      loc_18002E977
0x18002e8da  lea     rdi, [rbx+0D0h]
0x18002e8e1  call    cs:__imp_GetLastError
0x18002e8e8  nop     dword ptr [rax+rax+00h]
0x18002e8ed  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002e8f0  mov     ebp, eax
0x18002e8f2  call    cs:__imp_TlsGetValue
0x18002e8f9  nop     dword ptr [rax+rax+00h]
0x18002e8fe  test    rax, rax
0x18002e901  jz      loc_18002EB3B
0x18002e907  mov     rdi, rax
0x18002e90a  mov     ecx, ebp; dwErrCode
0x18002e90c  call    cs:__imp_SetLastError
0x18002e913  nop     dword ptr [rax+rax+00h]
0x18002e918  mov     eax, [rdi+7C4h]
0x18002e91e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e925  test    eax, eax
0x18002e927  jz      short loc_18002E977
0x18002e929  sub     eax, 1
0x18002e92c  mov     [rdi+7C4h], eax
0x18002e932  jnz     short loc_18002E977
0x18002e934  mov     [rdi+7C4h], r14d
0x18002e93b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002e942  mov     [rdi+7E0h], r14
0x18002e949  mov     [rdi+7CCh], r14d
0x18002e950  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002e957  mov     [rdi+7E8h], r14d
0x18002e95e  call    cs:__imp_GetCurrentThreadId
0x18002e965  nop     dword ptr [rax+rax+00h]
0x18002e96a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e971  mov     [rdi+7C0h], eax
0x18002e977  mov     [rsi+10h], r14d
0x18002e97b  cmp     [rbx+8], r14b
0x18002e97f  jz      loc_18002EA14
0x18002e985  lea     rdi, [rbx+0D0h]
0x18002e98c  call    cs:__imp_GetLastError
0x18002e993  nop     dword ptr [rax+rax+00h]
0x18002e998  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002e99b  mov     ebp, eax
0x18002e99d  call    cs:__imp_TlsGetValue
0x18002e9a4  nop     dword ptr [rax+rax+00h]
0x18002e9a9  test    rax, rax
0x18002e9ac  jz      loc_18002EB72
0x18002e9b2  mov     rdi, rax
0x18002e9b5  mov     ecx, ebp; dwErrCode
0x18002e9b7  call    cs:__imp_SetLastError
0x18002e9be  nop     dword ptr [rax+rax+00h]
0x18002e9c3  mov     eax, [rdi+7C4h]
0x18002e9c9  test    eax, eax
0x18002e9cb  jz      short loc_18002EA14
0x18002e9cd  sub     eax, 1
0x18002e9d0  mov     [rdi+7C4h], eax
0x18002e9d6  jnz     short loc_18002EA14
0x18002e9d8  mov     [rdi+7C4h], r14d
0x18002e9df  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002e9e6  mov     [rdi+7E0h], r14
0x18002e9ed  mov     [rdi+7CCh], r14d
0x18002e9f4  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002e9fb  mov     [rdi+7E8h], r14d
0x18002ea02  call    cs:__imp_GetCurrentThreadId
0x18002ea09  nop     dword ptr [rax+rax+00h]
0x18002ea0e  mov     [rdi+7C0h], eax
0x18002ea14  mov     rcx, [rsi+30h]
0x18002ea18  mov     r14, [rsp+28h+var_8]
0x18002ea1d  mov     rdi, [rsp+28h+arg_18]
0x18002ea22  mov     rbp, [rsp+28h+arg_8]
0x18002ea27  mov     rbx, [rsp+28h+arg_0]
0x18002ea2c  test    rcx, rcx
0x18002ea2f  jz      short loc_18002EA3D
0x18002ea31  mov     rax, [rcx]
0x18002ea34  mov     rax, [rax+10h]
0x18002ea38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea3d  mov     rcx, [rsi+28h]
0x18002ea41  mov     rsi, [rsp+28h+arg_10]
0x18002ea46  test    rcx, rcx
0x18002ea49  jz      short loc_18002EA5B
0x18002ea4b  mov     rax, [rcx]
0x18002ea4e  mov     rax, [rax+10h]
0x18002ea52  add     rsp, 28h
0x18002ea56  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea5b  add     rsp, 28h
0x18002ea5f  retn
0x18002ea61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002ea68  nop     dword ptr [rax+rax+00h]
0x18002ea6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea74  mov     rcx, rax
0x18002ea77  test    rax, rax
0x18002ea7a  jnz     loc_18002EBE7
0x18002ea80  lea     rbx, qword_1801B97E0
0x18002ea87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea8e  jmp     loc_18002E7D0
0x18002ea93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002ea9a  nop     dword ptr [rax+rax+00h]
0x18002ea9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eaa6  mov     rcx, rax
0x18002eaa9  test    rax, rax
0x18002eaac  jnz     loc_18002EC0C
0x18002eab2  lea     rbx, qword_1801B97E0
0x18002eab9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eac0  jmp     loc_18002E858
0x18002eac5  call    cs:__imp_GetLastError
0x18002eacc  nop     dword ptr [rax+rax+00h]
0x18002ead1  test    eax, eax
0x18002ead3  jnz     loc_18002E810
0x18002ead9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eae0  test    rcx, rcx
0x18002eae3  jz      loc_18002EBA9
0x18002eae9  mov     rax, [rcx]
0x18002eaec  mov     rax, [rax]
0x18002eaef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaf4  test    rax, rax
0x18002eaf7  cmovnz  rdi, rax
0x18002eafb  jmp     loc_18002E810
0x18002eb00  call    cs:__imp_GetLastError
0x18002eb07  nop     dword ptr [rax+rax+00h]
0x18002eb0c  test    eax, eax
0x18002eb0e  jnz     loc_18002E88E
0x18002eb14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb1b  test    rcx, rcx
0x18002eb1e  jz      loc_18002EBBA
0x18002eb24  mov     rax, [rcx]
0x18002eb27  mov     rax, [rax]
0x18002eb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb2f  test    rax, rax
0x18002eb32  cmovnz  rdi, rax
0x18002eb36  jmp     loc_18002E88E
0x18002eb3b  call    cs:__imp_GetLastError
0x18002eb42  nop     dword ptr [rax+rax+00h]
0x18002eb47  test    eax, eax
0x18002eb49  jnz     loc_18002E90A
0x18002eb4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb56  test    rcx, rcx
0x18002eb59  jz      short loc_18002EBCB
0x18002eb5b  mov     rax, [rcx]
0x18002eb5e  mov     rax, [rax]
0x18002eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb66  test    rax, rax
0x18002eb69  cmovnz  rdi, rax
0x18002eb6d  jmp     loc_18002E90A
0x18002eb72  call    cs:__imp_GetLastError
0x18002eb79  nop     dword ptr [rax+rax+00h]
0x18002eb7e  test    eax, eax
0x18002eb80  jnz     loc_18002E9B5
0x18002eb86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb8d  test    rcx, rcx
0x18002eb90  jz      short loc_18002EBD9
0x18002eb92  mov     rax, [rcx]
0x18002eb95  mov     rax, [rax]
0x18002eb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb9d  test    rax, rax
0x18002eba0  cmovnz  rdi, rax
0x18002eba4  jmp     loc_18002E9B5
0x18002eba9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ebae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ebb5  jmp     loc_18002EAE9
0x18002ebba  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ebbf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ebc6  jmp     loc_18002EB24
0x18002ebcb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ebd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ebd7  jmp     short loc_18002EB5B
0x18002ebd9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ebde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ebe5  jmp     short loc_18002EB92
0x18002ebe7  mov     rax, [rax]
0x18002ebea  mov     edx, 7F0h
0x18002ebef  mov     rax, [rax+8]
0x18002ebf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf8  test    eax, eax
0x18002ebfa  jz      loc_18002EA80
0x18002ec00  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ec07  jmp     loc_18002E7D0
0x18002ec0c  mov     rax, [rax]
0x18002ec0f  mov     edx, 7F0h
0x18002ec14  mov     rax, [rax+8]
0x18002ec18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec1d  test    eax, eax
0x18002ec1f  jz      loc_18002EAB2
0x18002ec25  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ec2c  jmp     loc_18002E858
```
