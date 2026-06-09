# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003b70`
- end: `0x180003cb6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `326`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003b70`
- `0x1800041b8`
- `0x18000429c`
- `0x1800050c0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c5b`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180003b70  push    rbx
0x180003b72  push    rbp
0x180003b73  push    rsi
0x180003b74  push    rdi
0x180003b75  push    r14
0x180003b77  sub     rsp, 20h
0x180003b7b  mov     byte ptr [rdx], 0
0x180003b7e  xor     bpl, bpl
0x180003b81  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003b88  mov     r14, r8
0x180003b8b  mov     rsi, rdx
0x180003b8e  mov     rdi, rcx
0x180003b91  test    rbx, rbx
0x180003b94  jz      loc_180003C30
0x180003b9a  call    cs:__imp_GetCurrentThreadId
0x180003ba0  mov     r8d, eax
0x180003ba3  mov     r9d, eax
0x180003ba6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003bb0  shr     r8, 2
0x180003bb4  mul     r8
0x180003bb7  shr     rdx, 3
0x180003bbb  lea     rcx, [rdx+rdx*4]
0x180003bbf  add     rcx, rcx
0x180003bc2  sub     r8, rcx
0x180003bc5  mov     rbx, [rbx+r8*8]
0x180003bc9  jmp     short loc_180003BD4
0x180003bcb  cmp     [rbx], r9d
0x180003bce  jz      short loc_180003C4B
0x180003bd0  mov     rbx, [rbx+8]
0x180003bd4  test    rbx, rbx
0x180003bd7  jnz     short loc_180003BCB
0x180003bd9  test    rbx, rbx
0x180003bdc  jz      short loc_180003C30
0x180003bde  cmp     qword ptr [rbx], 0
0x180003be2  jz      short loc_180003C30
0x180003be4  mov     [rsi], bpl
0x180003be7  mov     r9, r14; unsigned __int64
0x180003bea  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003bed  mov     r8, rsi; char *
0x180003bf0  mov     rcx, rdi; struct wil::FailureInfo *
0x180003bf3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003bf8  test    al, al
0x180003bfa  jz      short loc_180003C00
0x180003bfc  mov     [rdi+48h], rsi
0x180003c00  mov     rbx, [rbx]
0x180003c03  mov     al, [rbx+28h]
0x180003c06  mov     byte ptr [rbx+28h], 1
0x180003c0a  test    al, al
0x180003c0c  jnz     short loc_180003C27
0x180003c0e  mov     rcx, [rbx+8]
0x180003c12  mov     rdx, rdi
0x180003c15  mov     rax, [rcx]
0x180003c18  mov     rax, [rax]
0x180003c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c20  or      bpl, al
0x180003c23  mov     byte ptr [rbx+28h], 0
0x180003c27  mov     rbx, [rbx+10h]
0x180003c2b  test    rbx, rbx
0x180003c2e  jnz     short loc_180003C03
0x180003c30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003c37  test    rax, rax
0x180003c3a  jz      short loc_180003C5B
0x180003c3c  test    bpl, bpl
0x180003c3f  jnz     short loc_180003C51
0x180003c41  test    byte ptr [rdi+4], 2
0x180003c45  jnz     short loc_180003C51
0x180003c47  xor     ecx, ecx
0x180003c49  jmp     short loc_180003C53
0x180003c4b  add     rbx, 10h
0x180003c4f  jmp     short loc_180003BD9
0x180003c51  mov     cl, 1
0x180003c53  mov     rdx, rdi
0x180003c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5b  call    cs:__imp_GetCurrentThreadId
0x180003c61  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003c67  cmp     ecx, eax
0x180003c69  jz      short loc_180003CAB
0x180003c6b  mov     ecx, 1
0x180003c70  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003c78  inc     ecx; this
0x180003c7a  cmp     ecx, 4
0x180003c7d  jge     short loc_180003CA4
0x180003c7f  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003c85  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003c8a  test    rax, rax
0x180003c8d  jz      short loc_180003C9A
0x180003c8f  mov     rdx, rdi; struct wil::FailureInfo *
0x180003c92  mov     rcx, rax; this
0x180003c95  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180003c9a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003ca4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003cab  add     rsp, 20h
0x180003caf  pop     r14
0x180003cb1  pop     rdi
0x180003cb2  pop     rsi
0x180003cb3  pop     rbp
0x180003cb4  pop     rbx
0x180003cb5  retn
```
