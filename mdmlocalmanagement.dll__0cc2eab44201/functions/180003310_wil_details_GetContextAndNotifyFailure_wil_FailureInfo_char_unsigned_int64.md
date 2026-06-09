# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003310`
- end: `0x180003464`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003310`
- `0x180003988`
- `0x180003a6c`
- `0x180004db8`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000333a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000333a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003402`

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
0x180003310  push    rbx
0x180003312  push    rbp
0x180003313  push    rsi
0x180003314  push    rdi
0x180003315  push    r14
0x180003317  sub     rsp, 20h
0x18000331b  mov     r14, r8
0x18000331e  mov     rsi, rdx
0x180003321  mov     rdi, rcx
0x180003324  mov     byte ptr [rdx], 0
0x180003327  xor     bpl, bpl
0x18000332a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003331  test    rbx, rbx
0x180003334  jz      loc_1800033D6
0x18000333a  call    cs:__imp_GetCurrentThreadId
0x180003341  nop     dword ptr [rax+rax+00h]
0x180003346  mov     r9d, eax
0x180003349  mov     r8d, eax
0x18000334c  shr     r8, 2
0x180003350  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000335a  mul     r8
0x18000335d  shr     rdx, 3
0x180003361  lea     rcx, [rdx+rdx*4]
0x180003365  add     rcx, rcx
0x180003368  sub     r8, rcx
0x18000336b  mov     rbx, [rbx+r8*8]
0x18000336f  jmp     short loc_18000337A
0x180003371  cmp     [rbx], r9d
0x180003374  jz      short loc_1800033F1
0x180003376  mov     rbx, [rbx+8]
0x18000337a  test    rbx, rbx
0x18000337d  jnz     short loc_180003371
0x18000337f  test    rbx, rbx
0x180003382  jz      short loc_1800033D6
0x180003384  cmp     qword ptr [rbx], 0
0x180003388  jz      short loc_1800033D6
0x18000338a  mov     [rsi], bpl
0x18000338d  mov     r9, r14; unsigned __int64
0x180003390  mov     r8, rsi; char *
0x180003393  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003396  mov     rcx, rdi; struct wil::FailureInfo *
0x180003399  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000339e  test    al, al
0x1800033a0  jz      short loc_1800033A6
0x1800033a2  mov     [rdi+48h], rsi
0x1800033a6  mov     rbx, [rbx]
0x1800033a9  mov     al, [rbx+28h]
0x1800033ac  mov     byte ptr [rbx+28h], 1
0x1800033b0  test    al, al
0x1800033b2  jnz     short loc_1800033CD
0x1800033b4  mov     rcx, [rbx+8]
0x1800033b8  mov     rax, [rcx]
0x1800033bb  mov     rdx, rdi
0x1800033be  mov     rax, [rax]
0x1800033c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c6  or      bpl, al
0x1800033c9  mov     byte ptr [rbx+28h], 0
0x1800033cd  mov     rbx, [rbx+10h]
0x1800033d1  test    rbx, rbx
0x1800033d4  jnz     short loc_1800033A9
0x1800033d6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800033dd  test    rax, rax
0x1800033e0  jz      short loc_180003402
0x1800033e2  test    bpl, bpl
0x1800033e5  jnz     short loc_1800033F7
0x1800033e7  test    byte ptr [rdi+4], 2
0x1800033eb  jnz     short loc_1800033F7
0x1800033ed  xor     ecx, ecx
0x1800033ef  jmp     short loc_1800033F9
0x1800033f1  add     rbx, 10h
0x1800033f5  jmp     short loc_18000337F
0x1800033f7  mov     cl, 1
0x1800033f9  mov     rdx, rdi
0x1800033fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003401  nop
0x180003402  call    cs:__imp_GetCurrentThreadId
0x180003409  nop     dword ptr [rax+rax+00h]
0x18000340e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003414  cmp     ecx, eax
0x180003416  jz      short loc_180003458
0x180003418  mov     ecx, 1
0x18000341d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003425  inc     ecx; this
0x180003427  cmp     ecx, 4
0x18000342a  jge     short loc_180003451
0x18000342c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003432  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003437  test    rax, rax
0x18000343a  jz      short loc_180003447
0x18000343c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000343f  mov     rcx, rax; this
0x180003442  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180003447  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003451  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003458  add     rsp, 20h
0x18000345c  pop     r14
0x18000345e  pop     rdi
0x18000345f  pop     rsi
0x180003460  pop     rbp
0x180003461  pop     rbx
0x180003462  retn
```
