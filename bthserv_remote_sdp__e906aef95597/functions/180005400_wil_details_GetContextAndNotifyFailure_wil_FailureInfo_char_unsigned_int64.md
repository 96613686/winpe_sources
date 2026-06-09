# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005400`
- end: `0x18000556e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `366`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005400`
- `0x180005a98`
- `0x180005b90`
- `0x18000894c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005438`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005438`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054fc`

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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
0x180005400  mov     rax, rsp
0x180005403  mov     [rax+8], rbx
0x180005407  mov     [rax+10h], rbp
0x18000540b  mov     [rax+18h], rsi
0x18000540f  mov     [rax+20h], rdi
0x180005413  push    r14
0x180005415  sub     rsp, 20h
0x180005419  mov     r14, r8
0x18000541c  mov     rsi, rdx
0x18000541f  mov     rdi, rcx
0x180005422  mov     byte ptr [rdx], 0
0x180005425  xor     bpl, bpl
0x180005428  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000542f  test    rbx, rbx
0x180005432  jz      loc_1800054D0
0x180005438  call    cs:__imp_GetCurrentThreadId
0x18000543f  nop     dword ptr [rax+rax+00h]
0x180005444  mov     r9d, eax
0x180005447  mov     r8d, eax
0x18000544a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005454  mul     r9
0x180005457  shr     rdx, 3
0x18000545b  lea     rcx, [rdx+rdx*4]
0x18000545f  add     rcx, rcx
0x180005462  sub     r8, rcx
0x180005465  mov     rbx, [rbx+r8*8]
0x180005469  jmp     short loc_180005474
0x18000546b  cmp     [rbx], r9d
0x18000546e  jz      short loc_1800054EB
0x180005470  mov     rbx, [rbx+8]
0x180005474  test    rbx, rbx
0x180005477  jnz     short loc_18000546B
0x180005479  test    rbx, rbx
0x18000547c  jz      short loc_1800054D0
0x18000547e  cmp     qword ptr [rbx], 0
0x180005482  jz      short loc_1800054D0
0x180005484  mov     [rsi], bpl
0x180005487  mov     r9, r14; unsigned __int64
0x18000548a  mov     r8, rsi; char *
0x18000548d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005490  mov     rcx, rdi; struct wil::FailureInfo *
0x180005493  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005498  test    al, al
0x18000549a  jz      short loc_1800054A0
0x18000549c  mov     [rdi+48h], rsi
0x1800054a0  mov     rbx, [rbx]
0x1800054a3  mov     al, [rbx+28h]
0x1800054a6  mov     byte ptr [rbx+28h], 1
0x1800054aa  test    al, al
0x1800054ac  jnz     short loc_1800054C7
0x1800054ae  mov     rcx, [rbx+8]
0x1800054b2  mov     rax, [rcx]
0x1800054b5  mov     rdx, rdi
0x1800054b8  mov     rax, [rax]
0x1800054bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c0  or      bpl, al
0x1800054c3  mov     byte ptr [rbx+28h], 0
0x1800054c7  mov     rbx, [rbx+10h]
0x1800054cb  test    rbx, rbx
0x1800054ce  jnz     short loc_1800054A3
0x1800054d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800054d7  test    rax, rax
0x1800054da  jz      short loc_1800054FC
0x1800054dc  test    bpl, bpl
0x1800054df  jnz     short loc_1800054F1
0x1800054e1  test    byte ptr [rdi+4], 2
0x1800054e5  jnz     short loc_1800054F1
0x1800054e7  xor     ecx, ecx
0x1800054e9  jmp     short loc_1800054F3
0x1800054eb  add     rbx, 10h
0x1800054ef  jmp     short loc_180005479
0x1800054f1  mov     cl, 1
0x1800054f3  mov     rdx, rdi
0x1800054f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fb  nop
0x1800054fc  call    cs:__imp_GetCurrentThreadId
0x180005503  nop     dword ptr [rax+rax+00h]
0x180005508  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000550e  cmp     ecx, eax
0x180005510  jz      short loc_180005552
0x180005512  mov     ecx, 1
0x180005517  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000551f  inc     ecx; this
0x180005521  cmp     ecx, 4
0x180005524  jge     short loc_18000554B
0x180005526  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000552c  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005531  test    rax, rax
0x180005534  jz      short loc_180005541
0x180005536  mov     rdx, rdi; struct wil::FailureInfo *
0x180005539  mov     rcx, rax; this
0x18000553c  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180005541  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000554b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005552  mov     rbx, [rsp+28h+arg_0]
0x180005557  mov     rbp, [rsp+28h+arg_8]
0x18000555c  mov     rsi, [rsp+28h+arg_10]
0x180005561  mov     rdi, [rsp+28h+arg_18]
0x180005566  add     rsp, 20h
0x18000556a  pop     r14
0x18000556c  retn
```
