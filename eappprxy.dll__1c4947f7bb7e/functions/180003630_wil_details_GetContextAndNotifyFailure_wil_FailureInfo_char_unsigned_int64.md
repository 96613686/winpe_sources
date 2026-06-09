# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003630`
- end: `0x180003784`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003630`
- `0x180003ca8`
- `0x180003d8c`
- `0x180005138`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000365a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000365a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003722`

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
0x180003630  push    rbx
0x180003632  push    rbp
0x180003633  push    rsi
0x180003634  push    rdi
0x180003635  push    r14
0x180003637  sub     rsp, 20h
0x18000363b  mov     r14, r8
0x18000363e  mov     rsi, rdx
0x180003641  mov     rdi, rcx
0x180003644  mov     byte ptr [rdx], 0
0x180003647  xor     bpl, bpl
0x18000364a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003651  test    rbx, rbx
0x180003654  jz      loc_1800036F6
0x18000365a  call    cs:__imp_GetCurrentThreadId
0x180003661  nop     dword ptr [rax+rax+00h]
0x180003666  mov     r9d, eax
0x180003669  mov     r8d, eax
0x18000366c  shr     r8, 2
0x180003670  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000367a  mul     r8
0x18000367d  shr     rdx, 3
0x180003681  lea     rcx, [rdx+rdx*4]
0x180003685  add     rcx, rcx
0x180003688  sub     r8, rcx
0x18000368b  mov     rbx, [rbx+r8*8]
0x18000368f  jmp     short loc_18000369A
0x180003691  cmp     [rbx], r9d
0x180003694  jz      short loc_180003711
0x180003696  mov     rbx, [rbx+8]
0x18000369a  test    rbx, rbx
0x18000369d  jnz     short loc_180003691
0x18000369f  test    rbx, rbx
0x1800036a2  jz      short loc_1800036F6
0x1800036a4  cmp     qword ptr [rbx], 0
0x1800036a8  jz      short loc_1800036F6
0x1800036aa  mov     [rsi], bpl
0x1800036ad  mov     r9, r14; unsigned __int64
0x1800036b0  mov     r8, rsi; char *
0x1800036b3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800036b6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800036b9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800036be  test    al, al
0x1800036c0  jz      short loc_1800036C6
0x1800036c2  mov     [rdi+48h], rsi
0x1800036c6  mov     rbx, [rbx]
0x1800036c9  mov     al, [rbx+28h]
0x1800036cc  mov     byte ptr [rbx+28h], 1
0x1800036d0  test    al, al
0x1800036d2  jnz     short loc_1800036ED
0x1800036d4  mov     rcx, [rbx+8]
0x1800036d8  mov     rax, [rcx]
0x1800036db  mov     rdx, rdi
0x1800036de  mov     rax, [rax]
0x1800036e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e6  or      bpl, al
0x1800036e9  mov     byte ptr [rbx+28h], 0
0x1800036ed  mov     rbx, [rbx+10h]
0x1800036f1  test    rbx, rbx
0x1800036f4  jnz     short loc_1800036C9
0x1800036f6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800036fd  test    rax, rax
0x180003700  jz      short loc_180003722
0x180003702  test    bpl, bpl
0x180003705  jnz     short loc_180003717
0x180003707  test    byte ptr [rdi+4], 2
0x18000370b  jnz     short loc_180003717
0x18000370d  xor     ecx, ecx
0x18000370f  jmp     short loc_180003719
0x180003711  add     rbx, 10h
0x180003715  jmp     short loc_18000369F
0x180003717  mov     cl, 1
0x180003719  mov     rdx, rdi
0x18000371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003721  nop
0x180003722  call    cs:__imp_GetCurrentThreadId
0x180003729  nop     dword ptr [rax+rax+00h]
0x18000372e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003734  cmp     ecx, eax
0x180003736  jz      short loc_180003778
0x180003738  mov     ecx, 1
0x18000373d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003745  inc     ecx; this
0x180003747  cmp     ecx, 4
0x18000374a  jge     short loc_180003771
0x18000374c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003752  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003757  test    rax, rax
0x18000375a  jz      short loc_180003767
0x18000375c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000375f  mov     rcx, rax; this
0x180003762  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180003767  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003771  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003778  add     rsp, 20h
0x18000377c  pop     r14
0x18000377e  pop     rdi
0x18000377f  pop     rsi
0x180003780  pop     rbp
0x180003781  pop     rbx
0x180003782  retn
```
