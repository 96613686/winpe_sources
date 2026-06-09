# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005460`
- end: `0x1400055b4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140005460`
- `0x140005ad8`
- `0x140005bc4`
- `0x140008b50`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000548a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000548a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005552`

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
0x140005460  push    rbx
0x140005462  push    rbp
0x140005463  push    rsi
0x140005464  push    rdi
0x140005465  push    r14
0x140005467  sub     rsp, 20h
0x14000546b  mov     r14, r8
0x14000546e  mov     rsi, rdx
0x140005471  mov     rdi, rcx
0x140005474  mov     byte ptr [rdx], 0
0x140005477  xor     bpl, bpl
0x14000547a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005481  test    rbx, rbx
0x140005484  jz      loc_140005526
0x14000548a  call    cs:__imp_GetCurrentThreadId
0x140005491  nop     dword ptr [rax+rax+00h]
0x140005496  mov     r9d, eax
0x140005499  mov     r8d, eax
0x14000549c  shr     r8, 2
0x1400054a0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400054aa  mul     r8
0x1400054ad  shr     rdx, 3
0x1400054b1  lea     rcx, [rdx+rdx*4]
0x1400054b5  add     rcx, rcx
0x1400054b8  sub     r8, rcx
0x1400054bb  mov     rbx, [rbx+r8*8]
0x1400054bf  jmp     short loc_1400054CA
0x1400054c1  cmp     [rbx], r9d
0x1400054c4  jz      short loc_140005541
0x1400054c6  mov     rbx, [rbx+8]
0x1400054ca  test    rbx, rbx
0x1400054cd  jnz     short loc_1400054C1
0x1400054cf  test    rbx, rbx
0x1400054d2  jz      short loc_140005526
0x1400054d4  cmp     qword ptr [rbx], 0
0x1400054d8  jz      short loc_140005526
0x1400054da  mov     [rsi], bpl
0x1400054dd  mov     r9, r14; unsigned __int64
0x1400054e0  mov     r8, rsi; char *
0x1400054e3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400054e6  mov     rcx, rdi; struct wil::FailureInfo *
0x1400054e9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400054ee  test    al, al
0x1400054f0  jz      short loc_1400054F6
0x1400054f2  mov     [rdi+48h], rsi
0x1400054f6  mov     rbx, [rbx]
0x1400054f9  mov     al, [rbx+28h]
0x1400054fc  mov     byte ptr [rbx+28h], 1
0x140005500  test    al, al
0x140005502  jnz     short loc_14000551D
0x140005504  mov     rcx, [rbx+8]
0x140005508  mov     rax, [rcx]
0x14000550b  mov     rdx, rdi
0x14000550e  mov     rax, [rax]
0x140005511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005516  or      bpl, al
0x140005519  mov     byte ptr [rbx+28h], 0
0x14000551d  mov     rbx, [rbx+10h]
0x140005521  test    rbx, rbx
0x140005524  jnz     short loc_1400054F9
0x140005526  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000552d  test    rax, rax
0x140005530  jz      short loc_140005552
0x140005532  test    bpl, bpl
0x140005535  jnz     short loc_140005547
0x140005537  test    byte ptr [rdi+4], 2
0x14000553b  jnz     short loc_140005547
0x14000553d  xor     ecx, ecx
0x14000553f  jmp     short loc_140005549
0x140005541  add     rbx, 10h
0x140005545  jmp     short loc_1400054CF
0x140005547  mov     cl, 1
0x140005549  mov     rdx, rdi
0x14000554c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005551  nop
0x140005552  call    cs:__imp_GetCurrentThreadId
0x140005559  nop     dword ptr [rax+rax+00h]
0x14000555e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005564  cmp     ecx, eax
0x140005566  jz      short loc_1400055A8
0x140005568  mov     ecx, 1
0x14000556d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005575  inc     ecx; this
0x140005577  cmp     ecx, 4
0x14000557a  jge     short loc_1400055A1
0x14000557c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005582  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140005587  test    rax, rax
0x14000558a  jz      short loc_140005597
0x14000558c  mov     rdx, rdi; struct wil::FailureInfo *
0x14000558f  mov     rcx, rax; this
0x140005592  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140005597  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400055a1  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400055a8  add     rsp, 20h
0x1400055ac  pop     r14
0x1400055ae  pop     rdi
0x1400055af  pop     rsi
0x1400055b0  pop     rbp
0x1400055b1  pop     rbx
0x1400055b2  retn
```
