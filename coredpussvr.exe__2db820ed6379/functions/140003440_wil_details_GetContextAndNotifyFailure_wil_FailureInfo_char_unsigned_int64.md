# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003440`
- end: `0x140003594`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140003440`
- `0x140003ab8`
- `0x140003b9c`
- `0x140004ed8`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000346a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003532`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000346a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003532`

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
0x140003440  push    rbx
0x140003442  push    rbp
0x140003443  push    rsi
0x140003444  push    rdi
0x140003445  push    r14
0x140003447  sub     rsp, 20h
0x14000344b  mov     r14, r8
0x14000344e  mov     rsi, rdx
0x140003451  mov     rdi, rcx
0x140003454  mov     byte ptr [rdx], 0
0x140003457  xor     bpl, bpl
0x14000345a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003461  test    rbx, rbx
0x140003464  jz      loc_140003506
0x14000346a  call    cs:__imp_GetCurrentThreadId
0x140003471  nop     dword ptr [rax+rax+00h]
0x140003476  mov     r9d, eax
0x140003479  mov     r8d, eax
0x14000347c  shr     r8, 2
0x140003480  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000348a  mul     r8
0x14000348d  shr     rdx, 3
0x140003491  lea     rcx, [rdx+rdx*4]
0x140003495  add     rcx, rcx
0x140003498  sub     r8, rcx
0x14000349b  mov     rbx, [rbx+r8*8]
0x14000349f  jmp     short loc_1400034AA
0x1400034a1  cmp     [rbx], r9d
0x1400034a4  jz      short loc_140003521
0x1400034a6  mov     rbx, [rbx+8]
0x1400034aa  test    rbx, rbx
0x1400034ad  jnz     short loc_1400034A1
0x1400034af  test    rbx, rbx
0x1400034b2  jz      short loc_140003506
0x1400034b4  cmp     qword ptr [rbx], 0
0x1400034b8  jz      short loc_140003506
0x1400034ba  mov     [rsi], bpl
0x1400034bd  mov     r9, r14; unsigned __int64
0x1400034c0  mov     r8, rsi; char *
0x1400034c3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400034c6  mov     rcx, rdi; struct wil::FailureInfo *
0x1400034c9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400034ce  test    al, al
0x1400034d0  jz      short loc_1400034D6
0x1400034d2  mov     [rdi+48h], rsi
0x1400034d6  mov     rbx, [rbx]
0x1400034d9  mov     al, [rbx+28h]
0x1400034dc  mov     byte ptr [rbx+28h], 1
0x1400034e0  test    al, al
0x1400034e2  jnz     short loc_1400034FD
0x1400034e4  mov     rcx, [rbx+8]
0x1400034e8  mov     rax, [rcx]
0x1400034eb  mov     rdx, rdi
0x1400034ee  mov     rax, [rax]
0x1400034f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034f6  or      bpl, al
0x1400034f9  mov     byte ptr [rbx+28h], 0
0x1400034fd  mov     rbx, [rbx+10h]
0x140003501  test    rbx, rbx
0x140003504  jnz     short loc_1400034D9
0x140003506  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000350d  test    rax, rax
0x140003510  jz      short loc_140003532
0x140003512  test    bpl, bpl
0x140003515  jnz     short loc_140003527
0x140003517  test    byte ptr [rdi+4], 2
0x14000351b  jnz     short loc_140003527
0x14000351d  xor     ecx, ecx
0x14000351f  jmp     short loc_140003529
0x140003521  add     rbx, 10h
0x140003525  jmp     short loc_1400034AF
0x140003527  mov     cl, 1
0x140003529  mov     rdx, rdi
0x14000352c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003531  nop
0x140003532  call    cs:__imp_GetCurrentThreadId
0x140003539  nop     dword ptr [rax+rax+00h]
0x14000353e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003544  cmp     ecx, eax
0x140003546  jz      short loc_140003588
0x140003548  mov     ecx, 1
0x14000354d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003555  inc     ecx; this
0x140003557  cmp     ecx, 4
0x14000355a  jge     short loc_140003581
0x14000355c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003562  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003567  test    rax, rax
0x14000356a  jz      short loc_140003577
0x14000356c  mov     rdx, rdi; struct wil::FailureInfo *
0x14000356f  mov     rcx, rax; this
0x140003572  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140003577  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003581  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003588  add     rsp, 20h
0x14000358c  pop     r14
0x14000358e  pop     rdi
0x14000358f  pop     rsi
0x140003590  pop     rbp
0x140003591  pop     rbx
0x140003592  retn
```
