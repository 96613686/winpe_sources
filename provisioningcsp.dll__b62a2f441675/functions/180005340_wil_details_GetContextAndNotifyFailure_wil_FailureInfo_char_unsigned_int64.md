# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005340`
- end: `0x180005494`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005340`
- `0x180005ae0`
- `0x180005bcc`
- `0x180006ea4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000536a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005432`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000536a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005432`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180005340  push    rbx
0x180005342  push    rbp
0x180005343  push    rsi
0x180005344  push    rdi
0x180005345  push    r14
0x180005347  sub     rsp, 20h
0x18000534b  mov     r14, r8
0x18000534e  mov     rsi, rdx
0x180005351  mov     rdi, rcx
0x180005354  mov     byte ptr [rdx], 0
0x180005357  xor     bpl, bpl
0x18000535a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005361  test    rbx, rbx
0x180005364  jz      loc_180005406
0x18000536a  call    cs:__imp_GetCurrentThreadId
0x180005371  nop     dword ptr [rax+rax+00h]
0x180005376  mov     r9d, eax
0x180005379  mov     r8d, eax
0x18000537c  shr     r8, 2
0x180005380  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000538a  mul     r8
0x18000538d  shr     rdx, 3
0x180005391  lea     rcx, [rdx+rdx*4]
0x180005395  add     rcx, rcx
0x180005398  sub     r8, rcx
0x18000539b  mov     rbx, [rbx+r8*8]
0x18000539f  jmp     short loc_1800053AA
0x1800053a1  cmp     [rbx], r9d
0x1800053a4  jz      short loc_180005421
0x1800053a6  mov     rbx, [rbx+8]
0x1800053aa  test    rbx, rbx
0x1800053ad  jnz     short loc_1800053A1
0x1800053af  test    rbx, rbx
0x1800053b2  jz      short loc_180005406
0x1800053b4  cmp     qword ptr [rbx], 0
0x1800053b8  jz      short loc_180005406
0x1800053ba  mov     [rsi], bpl
0x1800053bd  mov     r9, r14; unsigned __int64
0x1800053c0  mov     r8, rsi; char *
0x1800053c3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800053c6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800053c9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800053ce  test    al, al
0x1800053d0  jz      short loc_1800053D6
0x1800053d2  mov     [rdi+48h], rsi
0x1800053d6  mov     rbx, [rbx]
0x1800053d9  mov     al, [rbx+28h]
0x1800053dc  mov     byte ptr [rbx+28h], 1
0x1800053e0  test    al, al
0x1800053e2  jnz     short loc_1800053FD
0x1800053e4  mov     rcx, [rbx+8]
0x1800053e8  mov     rax, [rcx]
0x1800053eb  mov     rdx, rdi
0x1800053ee  mov     rax, [rax]
0x1800053f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f6  or      bpl, al
0x1800053f9  mov     byte ptr [rbx+28h], 0
0x1800053fd  mov     rbx, [rbx+10h]
0x180005401  test    rbx, rbx
0x180005404  jnz     short loc_1800053D9
0x180005406  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000540d  test    rax, rax
0x180005410  jz      short loc_180005432
0x180005412  test    bpl, bpl
0x180005415  jnz     short loc_180005427
0x180005417  test    byte ptr [rdi+4], 2
0x18000541b  jnz     short loc_180005427
0x18000541d  xor     ecx, ecx
0x18000541f  jmp     short loc_180005429
0x180005421  add     rbx, 10h
0x180005425  jmp     short loc_1800053AF
0x180005427  mov     cl, 1
0x180005429  mov     rdx, rdi
0x18000542c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005431  nop
0x180005432  call    cs:__imp_GetCurrentThreadId
0x180005439  nop     dword ptr [rax+rax+00h]
0x18000543e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005444  cmp     ecx, eax
0x180005446  jz      short loc_180005488
0x180005448  mov     ecx, 1
0x18000544d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005455  inc     ecx; this
0x180005457  cmp     ecx, 4
0x18000545a  jge     short loc_180005481
0x18000545c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005462  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005467  test    rax, rax
0x18000546a  jz      short loc_180005477
0x18000546c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000546f  mov     rcx, rax; this
0x180005472  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180005477  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005481  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005488  add     rsp, 20h
0x18000548c  pop     r14
0x18000548e  pop     rdi
0x18000548f  pop     rsi
0x180005490  pop     rbp
0x180005491  pop     rbx
0x180005492  retn
```
