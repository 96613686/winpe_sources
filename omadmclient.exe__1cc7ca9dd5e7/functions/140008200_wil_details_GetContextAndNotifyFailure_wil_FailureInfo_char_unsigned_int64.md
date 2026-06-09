# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140008200`
- end: `0x140008354`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140008200`
- `0x140008b40`
- `0x140008c24`
- `0x14000b84c`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000822a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400082f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000822a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400082f2`

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
0x140008200  push    rbx
0x140008202  push    rbp
0x140008203  push    rsi
0x140008204  push    rdi
0x140008205  push    r14
0x140008207  sub     rsp, 20h
0x14000820b  mov     r14, r8
0x14000820e  mov     rsi, rdx
0x140008211  mov     rdi, rcx
0x140008214  mov     byte ptr [rdx], 0
0x140008217  xor     bpl, bpl
0x14000821a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140008221  test    rbx, rbx
0x140008224  jz      loc_1400082C6
0x14000822a  call    cs:__imp_GetCurrentThreadId
0x140008231  nop     dword ptr [rax+rax+00h]
0x140008236  mov     r9d, eax
0x140008239  mov     r8d, eax
0x14000823c  shr     r8, 2
0x140008240  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000824a  mul     r8
0x14000824d  shr     rdx, 3
0x140008251  lea     rcx, [rdx+rdx*4]
0x140008255  add     rcx, rcx
0x140008258  sub     r8, rcx
0x14000825b  mov     rbx, [rbx+r8*8]
0x14000825f  jmp     short loc_14000826A
0x140008261  cmp     [rbx], r9d
0x140008264  jz      short loc_1400082E1
0x140008266  mov     rbx, [rbx+8]
0x14000826a  test    rbx, rbx
0x14000826d  jnz     short loc_140008261
0x14000826f  test    rbx, rbx
0x140008272  jz      short loc_1400082C6
0x140008274  cmp     qword ptr [rbx], 0
0x140008278  jz      short loc_1400082C6
0x14000827a  mov     [rsi], bpl
0x14000827d  mov     r9, r14; unsigned __int64
0x140008280  mov     r8, rsi; char *
0x140008283  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140008286  mov     rcx, rdi; struct wil::FailureInfo *
0x140008289  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000828e  test    al, al
0x140008290  jz      short loc_140008296
0x140008292  mov     [rdi+48h], rsi
0x140008296  mov     rbx, [rbx]
0x140008299  mov     al, [rbx+28h]
0x14000829c  mov     byte ptr [rbx+28h], 1
0x1400082a0  test    al, al
0x1400082a2  jnz     short loc_1400082BD
0x1400082a4  mov     rcx, [rbx+8]
0x1400082a8  mov     rax, [rcx]
0x1400082ab  mov     rdx, rdi
0x1400082ae  mov     rax, [rax]
0x1400082b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082b6  or      bpl, al
0x1400082b9  mov     byte ptr [rbx+28h], 0
0x1400082bd  mov     rbx, [rbx+10h]
0x1400082c1  test    rbx, rbx
0x1400082c4  jnz     short loc_140008299
0x1400082c6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400082cd  test    rax, rax
0x1400082d0  jz      short loc_1400082F2
0x1400082d2  test    bpl, bpl
0x1400082d5  jnz     short loc_1400082E7
0x1400082d7  test    byte ptr [rdi+4], 2
0x1400082db  jnz     short loc_1400082E7
0x1400082dd  xor     ecx, ecx
0x1400082df  jmp     short loc_1400082E9
0x1400082e1  add     rbx, 10h
0x1400082e5  jmp     short loc_14000826F
0x1400082e7  mov     cl, 1
0x1400082e9  mov     rdx, rdi
0x1400082ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082f1  nop
0x1400082f2  call    cs:__imp_GetCurrentThreadId
0x1400082f9  nop     dword ptr [rax+rax+00h]
0x1400082fe  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140008304  cmp     ecx, eax
0x140008306  jz      short loc_140008348
0x140008308  mov     ecx, 1
0x14000830d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140008315  inc     ecx; this
0x140008317  cmp     ecx, 4
0x14000831a  jge     short loc_140008341
0x14000831c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140008322  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140008327  test    rax, rax
0x14000832a  jz      short loc_140008337
0x14000832c  mov     rdx, rdi; struct wil::FailureInfo *
0x14000832f  mov     rcx, rax; this
0x140008332  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140008337  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140008341  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140008348  add     rsp, 20h
0x14000834c  pop     r14
0x14000834e  pop     rdi
0x14000834f  pop     rsi
0x140008350  pop     rbp
0x140008351  pop     rbx
0x140008352  retn
```
