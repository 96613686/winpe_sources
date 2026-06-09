# ProfileTelemetry::WatchCurrentThread(char const *,char const *,...)

- ea: `0x180016ea0`
- end: `0x1800170a1`
- name: `?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ`
- size: `513`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800156ec`
- `0x180016150`

## callees

- `0x180016ea0`
- `0x1800170b0`
- `0x180017220`
- `0x180017430`
- `0x18003c020`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017027`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016ee5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016ee5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016f7b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016f7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ProfileTelemetry::WatchCurrentThread(__int64 a1, __int64 a2, const char *a3, ...)
{
  __int64 *v5; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rbp
  DWORD CurrentThreadId; // r14d
  unsigned __int64 v9; // r8
  __int64 v10; // r15
  __int64 i; // rcx
  _QWORD *v12; // rcx
  char *v14; // rax
  signed __int64 v15; // rdx
  signed __int64 v16; // rax
  WINBOOL v17; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-50h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  v18 = 0;
  v17 = 0;
  if ( InitOnceBeginInitialize(&`ProfileTelemetry::Instance'::`2'::wrapper, 0, &v17, (LPVOID *)&v18) && v17 )
  {
    v18 = &qword_180082AA8;
    qword_180082AB0 = 0;
    byte_180082AB8 = 0;
    dword_180082ABC = 0;
    qword_180082AA8 = (__int64)&wil::TraceLoggingProvider::`vftable';
    atexit(_lambda_5fc566e46d8b54a39d36627b74c496ab_::_lambda_invoker_cdecl_);
    qword_180082AB0 = (__int64)ProfileLogging::Provider();
    byte_180082AB8 = 0;
    dword_180082ABC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180082AA8 + 8))(&qword_180082AA8);
    InitOnceComplete(&`ProfileTelemetry::Instance'::`2'::wrapper, 0, &qword_180082AA8);
  }
  v5 = v18;
  *(_BYTE *)(a1 + 24) = 0;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  v6 = (_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = v5;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = a1;
  *(_BYTE *)(a1 + 72) = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v10 = 8 * v9;
    for ( i = *(_QWORD *)(8 * v9 + v7); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v12 = (_QWORD *)(i + 16);
        goto LABEL_9;
      }
    }
    v14 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v9);
    v15 = (signed __int64)v14;
    if ( v14 )
    {
      *(_DWORD *)v14 = CurrentThreadId;
      *((_DWORD *)v14 + 1) = 0;
      *((_QWORD *)v14 + 1) = 0;
      v12 = v14 + 16;
      *((_QWORD *)v14 + 2) = 0;
      do
      {
        v16 = *(_QWORD *)(v10 + v7);
        *(_QWORD *)(v15 + 8) = v16;
      }
      while ( v16 != _InterlockedCompareExchange64((volatile signed __int64 *)(v10 + v7), v15, v16) );
    }
    else
    {
      v12 = 0;
    }
LABEL_9:
    *v6 = v12;
    if ( v12 )
    {
      *(_QWORD *)(a1 + 48) = *v12;
      *v12 = v6;
      *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
    }
  }
  wil::details::StoredCallContextInfo::SetMessage((wil::details::StoredCallContextInfo *)a1, a3, va);
  return a1;
}

```

## disassembly

```asm
0x180016ea0  mov     rax, rsp
0x180016ea3  mov     [rax+18h], r8
0x180016ea7  mov     [rax+20h], r9
0x180016eab  push    rbx
0x180016eac  push    rbp
0x180016ead  push    rsi
0x180016eae  push    rdi
0x180016eaf  push    r12
0x180016eb1  push    r13
0x180016eb3  push    r14
0x180016eb5  push    r15
0x180016eb7  sub     rsp, 38h
0x180016ebb  mov     rdi, rdx
0x180016ebe  mov     rbx, rcx
0x180016ec1  xor     r12d, r12d
0x180016ec4  mov     [rax-50h], r12
0x180016ec8  lea     r13, [rax+20h]
0x180016ecc  mov     [rax-50h], r12
0x180016ed0  mov     [rax-58h], r12d
0x180016ed4  lea     r9, [rax-50h]; lpContext
0x180016ed8  lea     r8, [rax-58h]; fPending
0x180016edc  xor     edx, edx; dwFlags
0x180016ede  lea     rcx, ?wrapper@?1??Instance@ProfileTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VProfileTelemetry@@@details@wil@@A; lpInitOnce
0x180016ee5  call    cs:__imp_InitOnceBeginInitialize
0x180016eec  nop     dword ptr [rax+rax+00h]
0x180016ef1  test    eax, eax
0x180016ef3  jz      loc_180016F87
0x180016ef9  cmp     [rsp+78h+var_58], r12d
0x180016efe  jz      loc_180016F87
0x180016f04  lea     rsi, qword_180082AA8
0x180016f0b  mov     [rsp+78h+var_50], rsi
0x180016f10  mov     cs:qword_180082AB0, r12
0x180016f17  mov     cs:byte_180082AB8, r12b
0x180016f1e  mov     cs:dword_180082ABC, r12d
0x180016f25  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180016f2c  mov     cs:qword_180082AA8, rax
0x180016f33  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5fc566e46d8b54a39d36627b74c496ab_@@CA@XZ; void (__cdecl *)()
0x180016f3a  call    atexit
0x180016f3f  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180016f44  mov     cs:qword_180082AB0, rax
0x180016f4b  mov     cs:byte_180082AB8, r12b
0x180016f52  mov     cs:dword_180082ABC, 1
0x180016f5c  mov     rax, cs:qword_180082AA8
0x180016f63  mov     rcx, rsi
0x180016f66  mov     rax, [rax+8]
0x180016f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f6f  mov     r8, rsi; lpContext
0x180016f72  xor     edx, edx; dwFlags
0x180016f74  lea     rcx, ?wrapper@?1??Instance@ProfileTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VProfileTelemetry@@@details@wil@@A; lpInitOnce
0x180016f7b  call    cs:__imp_InitOnceComplete
0x180016f82  nop     dword ptr [rax+rax+00h]
0x180016f87  mov     rax, [rsp+78h+var_50]
0x180016f8c  mov     rsi, [rsp+78h+arg_10]
0x180016f94  mov     [rbx+18h], r12b
0x180016f98  mov     [rbx], r12d
0x180016f9b  mov     [rbx+8], rdi
0x180016f9f  mov     [rbx+10h], r12
0x180016fa3  lea     rdi, [rbx+20h]
0x180016fa7  mov     [rdi], r12
0x180016faa  mov     [rdi+8], rax
0x180016fae  mov     [rdi+10h], r12
0x180016fb2  mov     [rdi+18h], r12d
0x180016fb6  mov     [rdi+20h], rbx
0x180016fba  mov     byte ptr [rdi+28h], 0
0x180016fbe  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180016fc5  test    rbp, rbp
0x180016fc8  jz      short loc_180017036
0x180016fca  call    cs:__imp_GetCurrentThreadId
0x180016fd1  nop     dword ptr [rax+rax+00h]
0x180016fd6  mov     r14d, eax
0x180016fd9  mov     r8d, eax
0x180016fdc  shr     r8, 2
0x180016fe0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180016fea  mul     r8
0x180016fed  shr     rdx, 3
0x180016ff1  lea     rcx, [rdx+rdx*4]
0x180016ff5  add     rcx, rcx
0x180016ff8  sub     r8, rcx; unsigned __int64
0x180016ffb  lea     r15, ds:0[r8*8]
0x180017003  mov     rcx, [r15+rbp]
0x180017007  test    rcx, rcx
0x18001700a  jz      short loc_18001705F
0x18001700c  cmp     [rcx], r14d
0x18001700f  jnz     short loc_180017059
0x180017011  add     rcx, 10h
0x180017015  mov     [rdi], rcx
0x180017018  test    rcx, rcx
0x18001701b  jz      short loc_180017036
0x18001701d  mov     rax, [rcx]
0x180017020  mov     [rdi+10h], rax
0x180017024  mov     [rcx], rdi
0x180017027  call    cs:__imp_GetCurrentThreadId
0x18001702e  nop     dword ptr [rax+rax+00h]
0x180017033  mov     [rdi+18h], eax
0x180017036  mov     r8, r13; char *
0x180017039  mov     rdx, rsi; char *
0x18001703c  mov     rcx, rbx; this
0x18001703f  call    ?SetMessage@StoredCallContextInfo@details@wil@@QEAAXPEBDPEAD@Z; wil::details::StoredCallContextInfo::SetMessage(char const *,char *)
0x180017044  mov     rax, rbx
0x180017047  add     rsp, 38h
0x18001704b  pop     r15
0x18001704d  pop     r14
0x18001704f  pop     r13
0x180017051  pop     r12
0x180017053  pop     rdi
0x180017054  pop     rsi
0x180017055  pop     rbp
0x180017056  pop     rbx
0x180017057  retn
0x180017059  mov     rcx, [rcx+8]
0x18001705d  jmp     short loc_180017007
0x18001705f  mov     edx, 18h; dwBytes
0x180017064  xor     ecx, ecx; dwFlags
0x180017066  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001706b  mov     rdx, rax
0x18001706e  test    rax, rax
0x180017071  jnz     short loc_180017078
0x180017073  mov     rcx, r12
0x180017076  jmp     short loc_180017015
0x180017078  mov     [rax], r14d
0x18001707b  xor     eax, eax
0x18001707d  mov     [rdx+4], eax
0x180017080  mov     [rdx+8], r12
0x180017084  lea     rcx, [rdx+10h]
0x180017088  mov     [rcx], r12
0x18001708b  mov     rax, [r15+rbp]
0x18001708f  mov     [rdx+8], rax
0x180017093  lock cmpxchg [r15+rbp], rdx
0x180017099  jnz     short loc_18001708B
0x18001709b  jmp     loc_180017015
```
