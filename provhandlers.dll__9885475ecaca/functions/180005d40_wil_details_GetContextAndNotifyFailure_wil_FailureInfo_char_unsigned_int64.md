# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005d40`
- end: `0x180005e87`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005d40`
- `0x1800063d0`
- `0x1800064b4`
- `0x180007b98`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180005d40  push    rbx
0x180005d42  push    rbp
0x180005d43  push    rsi
0x180005d44  push    rdi
0x180005d45  push    r14
0x180005d47  sub     rsp, 20h
0x180005d4b  mov     r14, r8
0x180005d4e  mov     rsi, rdx
0x180005d51  mov     rdi, rcx
0x180005d54  mov     byte ptr [rdx], 0
0x180005d57  xor     bpl, bpl
0x180005d5a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005d61  test    rbx, rbx
0x180005d64  jz      loc_180005E00
0x180005d6a  call    cs:__imp_GetCurrentThreadId
0x180005d70  mov     r9d, eax
0x180005d73  mov     r8d, eax
0x180005d76  shr     r8, 2
0x180005d7a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005d84  mul     r8
0x180005d87  shr     rdx, 3
0x180005d8b  lea     rcx, [rdx+rdx*4]
0x180005d8f  add     rcx, rcx
0x180005d92  sub     r8, rcx
0x180005d95  mov     rbx, [rbx+r8*8]
0x180005d99  jmp     short loc_180005DA4
0x180005d9b  cmp     [rbx], r9d
0x180005d9e  jz      short loc_180005E1B
0x180005da0  mov     rbx, [rbx+8]
0x180005da4  test    rbx, rbx
0x180005da7  jnz     short loc_180005D9B
0x180005da9  test    rbx, rbx
0x180005dac  jz      short loc_180005E00
0x180005dae  cmp     qword ptr [rbx], 0
0x180005db2  jz      short loc_180005E00
0x180005db4  mov     [rsi], bpl
0x180005db7  mov     r9, r14; unsigned __int64
0x180005dba  mov     r8, rsi; char *
0x180005dbd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005dc0  mov     rcx, rdi; struct wil::FailureInfo *
0x180005dc3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005dc8  test    al, al
0x180005dca  jz      short loc_180005DD0
0x180005dcc  mov     [rdi+48h], rsi
0x180005dd0  mov     rbx, [rbx]
0x180005dd3  mov     al, [rbx+28h]
0x180005dd6  mov     byte ptr [rbx+28h], 1
0x180005dda  test    al, al
0x180005ddc  jnz     short loc_180005DF7
0x180005dde  mov     rcx, [rbx+8]
0x180005de2  mov     rax, [rcx]
0x180005de5  mov     rdx, rdi
0x180005de8  mov     rax, [rax]
0x180005deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df0  or      bpl, al
0x180005df3  mov     byte ptr [rbx+28h], 0
0x180005df7  mov     rbx, [rbx+10h]
0x180005dfb  test    rbx, rbx
0x180005dfe  jnz     short loc_180005DD3
0x180005e00  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005e07  test    rax, rax
0x180005e0a  jz      short loc_180005E2C
0x180005e0c  test    bpl, bpl
0x180005e0f  jnz     short loc_180005E21
0x180005e11  test    byte ptr [rdi+4], 2
0x180005e15  jnz     short loc_180005E21
0x180005e17  xor     ecx, ecx
0x180005e19  jmp     short loc_180005E23
0x180005e1b  add     rbx, 10h
0x180005e1f  jmp     short loc_180005DA9
0x180005e21  mov     cl, 1
0x180005e23  mov     rdx, rdi
0x180005e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2b  nop
0x180005e2c  call    cs:__imp_GetCurrentThreadId
0x180005e32  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005e38  cmp     ecx, eax
0x180005e3a  jz      short loc_180005E7C
0x180005e3c  mov     ecx, 1
0x180005e41  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005e49  inc     ecx; this
0x180005e4b  cmp     ecx, 4
0x180005e4e  jge     short loc_180005E75
0x180005e50  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005e56  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005e5b  test    rax, rax
0x180005e5e  jz      short loc_180005E6B
0x180005e60  mov     rdx, rdi; struct wil::FailureInfo *
0x180005e63  mov     rcx, rax; this
0x180005e66  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180005e6b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005e75  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005e7c  add     rsp, 20h
0x180005e80  pop     r14
0x180005e82  pop     rdi
0x180005e83  pop     rsi
0x180005e84  pop     rbp
0x180005e85  pop     rbx
0x180005e86  retn
```
