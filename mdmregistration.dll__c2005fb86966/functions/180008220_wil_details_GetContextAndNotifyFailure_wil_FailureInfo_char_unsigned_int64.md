# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008220`
- end: `0x180008374`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008220`
- `0x1800088ec`
- `0x1800089d0`
- `0x18000b9ac`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000824a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000824a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008312`

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
0x180008220  push    rbx
0x180008222  push    rbp
0x180008223  push    rsi
0x180008224  push    rdi
0x180008225  push    r14
0x180008227  sub     rsp, 20h
0x18000822b  mov     r14, r8
0x18000822e  mov     rsi, rdx
0x180008231  mov     rdi, rcx
0x180008234  mov     byte ptr [rdx], 0
0x180008237  xor     bpl, bpl
0x18000823a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008241  test    rbx, rbx
0x180008244  jz      loc_1800082E6
0x18000824a  call    cs:__imp_GetCurrentThreadId
0x180008251  nop     dword ptr [rax+rax+00h]
0x180008256  mov     r9d, eax
0x180008259  mov     r8d, eax
0x18000825c  shr     r8, 2
0x180008260  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000826a  mul     r8
0x18000826d  shr     rdx, 3
0x180008271  lea     rcx, [rdx+rdx*4]
0x180008275  add     rcx, rcx
0x180008278  sub     r8, rcx
0x18000827b  mov     rbx, [rbx+r8*8]
0x18000827f  jmp     short loc_18000828A
0x180008281  cmp     [rbx], r9d
0x180008284  jz      short loc_180008301
0x180008286  mov     rbx, [rbx+8]
0x18000828a  test    rbx, rbx
0x18000828d  jnz     short loc_180008281
0x18000828f  test    rbx, rbx
0x180008292  jz      short loc_1800082E6
0x180008294  cmp     qword ptr [rbx], 0
0x180008298  jz      short loc_1800082E6
0x18000829a  mov     [rsi], bpl
0x18000829d  mov     r9, r14; unsigned __int64
0x1800082a0  mov     r8, rsi; char *
0x1800082a3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800082a6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800082a9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800082ae  test    al, al
0x1800082b0  jz      short loc_1800082B6
0x1800082b2  mov     [rdi+48h], rsi
0x1800082b6  mov     rbx, [rbx]
0x1800082b9  mov     al, [rbx+28h]
0x1800082bc  mov     byte ptr [rbx+28h], 1
0x1800082c0  test    al, al
0x1800082c2  jnz     short loc_1800082DD
0x1800082c4  mov     rcx, [rbx+8]
0x1800082c8  mov     rax, [rcx]
0x1800082cb  mov     rdx, rdi
0x1800082ce  mov     rax, [rax]
0x1800082d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d6  or      bpl, al
0x1800082d9  mov     byte ptr [rbx+28h], 0
0x1800082dd  mov     rbx, [rbx+10h]
0x1800082e1  test    rbx, rbx
0x1800082e4  jnz     short loc_1800082B9
0x1800082e6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800082ed  test    rax, rax
0x1800082f0  jz      short loc_180008312
0x1800082f2  test    bpl, bpl
0x1800082f5  jnz     short loc_180008307
0x1800082f7  test    byte ptr [rdi+4], 2
0x1800082fb  jnz     short loc_180008307
0x1800082fd  xor     ecx, ecx
0x1800082ff  jmp     short loc_180008309
0x180008301  add     rbx, 10h
0x180008305  jmp     short loc_18000828F
0x180008307  mov     cl, 1
0x180008309  mov     rdx, rdi
0x18000830c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008311  nop
0x180008312  call    cs:__imp_GetCurrentThreadId
0x180008319  nop     dword ptr [rax+rax+00h]
0x18000831e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008324  cmp     ecx, eax
0x180008326  jz      short loc_180008368
0x180008328  mov     ecx, 1
0x18000832d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008335  inc     ecx; this
0x180008337  cmp     ecx, 4
0x18000833a  jge     short loc_180008361
0x18000833c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008342  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008347  test    rax, rax
0x18000834a  jz      short loc_180008357
0x18000834c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000834f  mov     rcx, rax; this
0x180008352  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180008357  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008361  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008368  add     rsp, 20h
0x18000836c  pop     r14
0x18000836e  pop     rdi
0x18000836f  pop     rsi
0x180008370  pop     rbp
0x180008371  pop     rbx
0x180008372  retn
```
