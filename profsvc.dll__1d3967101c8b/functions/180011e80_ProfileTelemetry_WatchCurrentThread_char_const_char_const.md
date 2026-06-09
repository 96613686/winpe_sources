# ProfileTelemetry::WatchCurrentThread(char const *,char const *,...)

- ea: `0x180011e80`
- end: `0x180012064`
- name: `?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ`
- size: `484`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011200`
- `0x180013048`

## callees

- `0x180011e80`
- `0x180012070`
- `0x1800121d0`
- `0x18001e4ac`
- `0x18003aae0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ff1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011ec5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011ec5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011f51`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011f51`

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
    v18 = &qword_18007F9A0;
    qword_18007F9A8 = 0;
    byte_18007F9B0 = 0;
    dword_18007F9B4 = 0;
    qword_18007F9A0 = (__int64)&wil::TraceLoggingProvider::`vftable';
    atexit(_lambda_5fc566e46d8b54a39d36627b74c496ab_::_lambda_invoker_cdecl_);
    qword_18007F9A8 = (__int64)ProfileLogging::Provider();
    byte_18007F9B0 = 0;
    dword_18007F9B4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18007F9A0 + 8))(&qword_18007F9A0);
    InitOnceComplete(&`ProfileTelemetry::Instance'::`2'::wrapper, 0, &qword_18007F9A0);
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
0x180011e80  mov     rax, rsp
0x180011e83  mov     [rax+18h], r8
0x180011e87  mov     [rax+20h], r9
0x180011e8b  push    rbx
0x180011e8c  push    rbp
0x180011e8d  push    rsi
0x180011e8e  push    rdi
0x180011e8f  push    r12
0x180011e91  push    r13
0x180011e93  push    r14
0x180011e95  push    r15
0x180011e97  sub     rsp, 38h
0x180011e9b  mov     rdi, rdx
0x180011e9e  mov     rbx, rcx
0x180011ea1  xor     r12d, r12d
0x180011ea4  mov     [rax-50h], r12
0x180011ea8  lea     r13, [rax+20h]
0x180011eac  mov     [rax-50h], r12
0x180011eb0  mov     [rax-58h], r12d
0x180011eb4  lea     r9, [rax-50h]; lpContext
0x180011eb8  lea     r8, [rax-58h]; fPending
0x180011ebc  xor     edx, edx; dwFlags
0x180011ebe  lea     rcx, ?wrapper@?1??Instance@ProfileTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VProfileTelemetry@@@details@wil@@A; lpInitOnce
0x180011ec5  call    cs:__imp_InitOnceBeginInitialize
0x180011ecb  test    eax, eax
0x180011ecd  jz      loc_180011F57
0x180011ed3  cmp     [rsp+78h+var_58], r12d
0x180011ed8  jz      short loc_180011F57
0x180011eda  lea     rsi, qword_18007F9A0
0x180011ee1  mov     [rsp+78h+var_50], rsi
0x180011ee6  mov     cs:qword_18007F9A8, r12
0x180011eed  mov     cs:byte_18007F9B0, r12b
0x180011ef4  mov     cs:dword_18007F9B4, r12d
0x180011efb  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180011f02  mov     cs:qword_18007F9A0, rax
0x180011f09  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5fc566e46d8b54a39d36627b74c496ab_@@CA@XZ; void (__cdecl *)()
0x180011f10  call    atexit
0x180011f15  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180011f1a  mov     cs:qword_18007F9A8, rax
0x180011f21  mov     cs:byte_18007F9B0, r12b
0x180011f28  mov     cs:dword_18007F9B4, 1
0x180011f32  mov     rax, cs:qword_18007F9A0
0x180011f39  mov     rcx, rsi
0x180011f3c  mov     rax, [rax+8]
0x180011f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f45  mov     r8, rsi; lpContext
0x180011f48  xor     edx, edx; dwFlags
0x180011f4a  lea     rcx, ?wrapper@?1??Instance@ProfileTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VProfileTelemetry@@@details@wil@@A; lpInitOnce
0x180011f51  call    cs:__imp_InitOnceComplete
0x180011f57  mov     rax, [rsp+78h+var_50]
0x180011f5c  mov     rsi, [rsp+78h+arg_10]
0x180011f64  mov     [rbx+18h], r12b
0x180011f68  mov     [rbx], r12d
0x180011f6b  mov     [rbx+8], rdi
0x180011f6f  mov     [rbx+10h], r12
0x180011f73  lea     rdi, [rbx+20h]
0x180011f77  mov     [rdi], r12
0x180011f7a  mov     [rdi+8], rax
0x180011f7e  mov     [rdi+10h], r12
0x180011f82  mov     [rdi+18h], r12d
0x180011f86  mov     [rdi+20h], rbx
0x180011f8a  mov     byte ptr [rdi+28h], 0
0x180011f8e  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011f95  test    rbp, rbp
0x180011f98  jz      short loc_180011FFA
0x180011f9a  call    cs:__imp_GetCurrentThreadId
0x180011fa0  mov     r14d, eax
0x180011fa3  mov     r8d, eax
0x180011fa6  shr     r8, 2
0x180011faa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180011fb4  mul     r8
0x180011fb7  shr     rdx, 3
0x180011fbb  lea     rcx, [rdx+rdx*4]
0x180011fbf  add     rcx, rcx
0x180011fc2  sub     r8, rcx; unsigned __int64
0x180011fc5  lea     r15, ds:0[r8*8]
0x180011fcd  mov     rcx, [r15+rbp]
0x180011fd1  test    rcx, rcx
0x180011fd4  jz      short loc_180012022
0x180011fd6  cmp     [rcx], r14d
0x180011fd9  jnz     short loc_18001201C
0x180011fdb  add     rcx, 10h
0x180011fdf  mov     [rdi], rcx
0x180011fe2  test    rcx, rcx
0x180011fe5  jz      short loc_180011FFA
0x180011fe7  mov     rax, [rcx]
0x180011fea  mov     [rdi+10h], rax
0x180011fee  mov     [rcx], rdi
0x180011ff1  call    cs:__imp_GetCurrentThreadId
0x180011ff7  mov     [rdi+18h], eax
0x180011ffa  mov     r8, r13; char *
0x180011ffd  mov     rdx, rsi; char *
0x180012000  mov     rcx, rbx; this
0x180012003  call    ?SetMessage@StoredCallContextInfo@details@wil@@QEAAXPEBDPEAD@Z; wil::details::StoredCallContextInfo::SetMessage(char const *,char *)
0x180012008  mov     rax, rbx
0x18001200b  add     rsp, 38h
0x18001200f  pop     r15
0x180012011  pop     r14
0x180012013  pop     r13
0x180012015  pop     r12
0x180012017  pop     rdi
0x180012018  pop     rsi
0x180012019  pop     rbp
0x18001201a  pop     rbx
0x18001201b  retn
0x18001201c  mov     rcx, [rcx+8]
0x180012020  jmp     short loc_180011FD1
0x180012022  mov     edx, 18h; dwBytes
0x180012027  xor     ecx, ecx; dwFlags
0x180012029  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001202e  mov     rdx, rax
0x180012031  test    rax, rax
0x180012034  jnz     short loc_18001203B
0x180012036  mov     rcx, r12
0x180012039  jmp     short loc_180011FDF
0x18001203b  mov     [rax], r14d
0x18001203e  xor     eax, eax
0x180012040  mov     [rdx+4], eax
0x180012043  mov     [rdx+8], r12
0x180012047  lea     rcx, [rdx+10h]
0x18001204b  mov     [rcx], r12
0x18001204e  mov     rax, [r15+rbp]
0x180012052  mov     [rdx+8], rax
0x180012056  lock cmpxchg [r15+rbp], rdx
0x18001205c  jnz     short loc_18001204E
0x18001205e  jmp     loc_180011FDF
```
