# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800083f0`
- end: `0x180008537`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800083f0`
- `0x180008600`
- `0x1800086e4`
- `0x180009dbc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000841a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000841a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x1800083f0  push    rbx
0x1800083f2  push    rbp
0x1800083f3  push    rsi
0x1800083f4  push    rdi
0x1800083f5  push    r14
0x1800083f7  sub     rsp, 20h
0x1800083fb  mov     r14, r8
0x1800083fe  mov     rsi, rdx
0x180008401  mov     rdi, rcx
0x180008404  mov     byte ptr [rdx], 0
0x180008407  xor     bpl, bpl
0x18000840a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008411  test    rbx, rbx
0x180008414  jz      loc_1800084B0
0x18000841a  call    cs:__imp_GetCurrentThreadId
0x180008420  mov     r9d, eax
0x180008423  mov     r8d, eax
0x180008426  shr     r8, 2
0x18000842a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008434  mul     r8
0x180008437  shr     rdx, 3
0x18000843b  lea     rcx, [rdx+rdx*4]
0x18000843f  add     rcx, rcx
0x180008442  sub     r8, rcx
0x180008445  mov     rbx, [rbx+r8*8]
0x180008449  jmp     short loc_180008454
0x18000844b  cmp     [rbx], r9d
0x18000844e  jz      short loc_1800084CB
0x180008450  mov     rbx, [rbx+8]
0x180008454  test    rbx, rbx
0x180008457  jnz     short loc_18000844B
0x180008459  test    rbx, rbx
0x18000845c  jz      short loc_1800084B0
0x18000845e  cmp     qword ptr [rbx], 0
0x180008462  jz      short loc_1800084B0
0x180008464  mov     [rsi], bpl
0x180008467  mov     r9, r14; unsigned __int64
0x18000846a  mov     r8, rsi; char *
0x18000846d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008470  mov     rcx, rdi; struct wil::FailureInfo *
0x180008473  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008478  test    al, al
0x18000847a  jz      short loc_180008480
0x18000847c  mov     [rdi+48h], rsi
0x180008480  mov     rbx, [rbx]
0x180008483  mov     al, [rbx+28h]
0x180008486  mov     byte ptr [rbx+28h], 1
0x18000848a  test    al, al
0x18000848c  jnz     short loc_1800084A7
0x18000848e  mov     rcx, [rbx+8]
0x180008492  mov     rax, [rcx]
0x180008495  mov     rdx, rdi
0x180008498  mov     rax, [rax]
0x18000849b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a0  or      bpl, al
0x1800084a3  mov     byte ptr [rbx+28h], 0
0x1800084a7  mov     rbx, [rbx+10h]
0x1800084ab  test    rbx, rbx
0x1800084ae  jnz     short loc_180008483
0x1800084b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800084b7  test    rax, rax
0x1800084ba  jz      short loc_1800084DC
0x1800084bc  test    bpl, bpl
0x1800084bf  jnz     short loc_1800084D1
0x1800084c1  test    byte ptr [rdi+4], 2
0x1800084c5  jnz     short loc_1800084D1
0x1800084c7  xor     ecx, ecx
0x1800084c9  jmp     short loc_1800084D3
0x1800084cb  add     rbx, 10h
0x1800084cf  jmp     short loc_180008459
0x1800084d1  mov     cl, 1
0x1800084d3  mov     rdx, rdi
0x1800084d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084db  nop
0x1800084dc  call    cs:__imp_GetCurrentThreadId
0x1800084e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800084e8  cmp     ecx, eax
0x1800084ea  jz      short loc_18000852C
0x1800084ec  mov     ecx, 1
0x1800084f1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800084f9  inc     ecx; this
0x1800084fb  cmp     ecx, 4
0x1800084fe  jge     short loc_180008525
0x180008500  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008506  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000850b  test    rax, rax
0x18000850e  jz      short loc_18000851B
0x180008510  mov     rdx, rdi; struct wil::FailureInfo *
0x180008513  mov     rcx, rax; this
0x180008516  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000851b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008525  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000852c  add     rsp, 20h
0x180008530  pop     r14
0x180008532  pop     rdi
0x180008533  pop     rsi
0x180008534  pop     rbp
0x180008535  pop     rbx
0x180008536  retn
```
