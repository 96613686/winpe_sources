# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009850`
- end: `0x180009997`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009850`
- `0x180009e8c`
- `0x180009f70`
- `0x18000c1cc`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000987a`
- `KERNEL32!GetCurrentThreadId` at `0x18000993c`
- `KERNEL32!GetCurrentThreadId` at `0x18000987a`
- `KERNEL32!GetCurrentThreadId` at `0x18000993c`

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
0x180009850  push    rbx
0x180009852  push    rbp
0x180009853  push    rsi
0x180009854  push    rdi
0x180009855  push    r14
0x180009857  sub     rsp, 20h
0x18000985b  mov     r14, r8
0x18000985e  mov     rsi, rdx
0x180009861  mov     rdi, rcx
0x180009864  mov     byte ptr [rdx], 0
0x180009867  xor     bpl, bpl
0x18000986a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009871  test    rbx, rbx
0x180009874  jz      loc_180009910
0x18000987a  call    cs:__imp_GetCurrentThreadId
0x180009880  mov     r9d, eax
0x180009883  mov     r8d, eax
0x180009886  shr     r8, 2
0x18000988a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009894  mul     r8
0x180009897  shr     rdx, 3
0x18000989b  lea     rcx, [rdx+rdx*4]
0x18000989f  add     rcx, rcx
0x1800098a2  sub     r8, rcx
0x1800098a5  mov     rbx, [rbx+r8*8]
0x1800098a9  jmp     short loc_1800098B4
0x1800098ab  cmp     [rbx], r9d
0x1800098ae  jz      short loc_18000992B
0x1800098b0  mov     rbx, [rbx+8]
0x1800098b4  test    rbx, rbx
0x1800098b7  jnz     short loc_1800098AB
0x1800098b9  test    rbx, rbx
0x1800098bc  jz      short loc_180009910
0x1800098be  cmp     qword ptr [rbx], 0
0x1800098c2  jz      short loc_180009910
0x1800098c4  mov     [rsi], bpl
0x1800098c7  mov     r9, r14; unsigned __int64
0x1800098ca  mov     r8, rsi; char *
0x1800098cd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800098d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800098d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800098d8  test    al, al
0x1800098da  jz      short loc_1800098E0
0x1800098dc  mov     [rdi+48h], rsi
0x1800098e0  mov     rbx, [rbx]
0x1800098e3  mov     al, [rbx+28h]
0x1800098e6  mov     byte ptr [rbx+28h], 1
0x1800098ea  test    al, al
0x1800098ec  jnz     short loc_180009907
0x1800098ee  mov     rcx, [rbx+8]
0x1800098f2  mov     rax, [rcx]
0x1800098f5  mov     rdx, rdi
0x1800098f8  mov     rax, [rax]
0x1800098fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009900  or      bpl, al
0x180009903  mov     byte ptr [rbx+28h], 0
0x180009907  mov     rbx, [rbx+10h]
0x18000990b  test    rbx, rbx
0x18000990e  jnz     short loc_1800098E3
0x180009910  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009917  test    rax, rax
0x18000991a  jz      short loc_18000993C
0x18000991c  test    bpl, bpl
0x18000991f  jnz     short loc_180009931
0x180009921  test    byte ptr [rdi+4], 2
0x180009925  jnz     short loc_180009931
0x180009927  xor     ecx, ecx
0x180009929  jmp     short loc_180009933
0x18000992b  add     rbx, 10h
0x18000992f  jmp     short loc_1800098B9
0x180009931  mov     cl, 1
0x180009933  mov     rdx, rdi
0x180009936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993b  nop
0x18000993c  call    cs:__imp_GetCurrentThreadId
0x180009942  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009948  cmp     ecx, eax
0x18000994a  jz      short loc_18000998C
0x18000994c  mov     ecx, 1
0x180009951  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009959  inc     ecx; this
0x18000995b  cmp     ecx, 4
0x18000995e  jge     short loc_180009985
0x180009960  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009966  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000996b  test    rax, rax
0x18000996e  jz      short loc_18000997B
0x180009970  mov     rdx, rdi; struct wil::FailureInfo *
0x180009973  mov     rcx, rax; this
0x180009976  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000997b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009985  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000998c  add     rsp, 20h
0x180009990  pop     r14
0x180009992  pop     rdi
0x180009993  pop     rsi
0x180009994  pop     rbp
0x180009995  pop     rbx
0x180009996  retn
```
