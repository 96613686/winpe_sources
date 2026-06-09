# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140006b00`
- end: `0x140006c47`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140006b00`
- `0x140007190`
- `0x140007274`
- `0x14000b288`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006bec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006bec`

## pseudocode

```c
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
0x140006b00  push    rbx
0x140006b02  push    rbp
0x140006b03  push    rsi
0x140006b04  push    rdi
0x140006b05  push    r14
0x140006b07  sub     rsp, 20h
0x140006b0b  mov     r14, r8
0x140006b0e  mov     rsi, rdx
0x140006b11  mov     rdi, rcx
0x140006b14  mov     byte ptr [rdx], 0
0x140006b17  xor     bpl, bpl
0x140006b1a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006b21  test    rbx, rbx
0x140006b24  jz      loc_140006BC0
0x140006b2a  call    cs:__imp_GetCurrentThreadId
0x140006b30  mov     r9d, eax
0x140006b33  mov     r8d, eax
0x140006b36  shr     r8, 2
0x140006b3a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006b44  mul     r8
0x140006b47  shr     rdx, 3
0x140006b4b  lea     rcx, [rdx+rdx*4]
0x140006b4f  add     rcx, rcx
0x140006b52  sub     r8, rcx
0x140006b55  mov     rbx, [rbx+r8*8]
0x140006b59  jmp     short loc_140006B64
0x140006b5b  cmp     [rbx], r9d
0x140006b5e  jz      short loc_140006BDB
0x140006b60  mov     rbx, [rbx+8]
0x140006b64  test    rbx, rbx
0x140006b67  jnz     short loc_140006B5B
0x140006b69  test    rbx, rbx
0x140006b6c  jz      short loc_140006BC0
0x140006b6e  cmp     qword ptr [rbx], 0
0x140006b72  jz      short loc_140006BC0
0x140006b74  mov     [rsi], bpl
0x140006b77  mov     r9, r14; unsigned __int64
0x140006b7a  mov     r8, rsi; char *
0x140006b7d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140006b80  mov     rcx, rdi; struct wil::FailureInfo *
0x140006b83  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006b88  test    al, al
0x140006b8a  jz      short loc_140006B90
0x140006b8c  mov     [rdi+48h], rsi
0x140006b90  mov     rbx, [rbx]
0x140006b93  mov     al, [rbx+28h]
0x140006b96  mov     byte ptr [rbx+28h], 1
0x140006b9a  test    al, al
0x140006b9c  jnz     short loc_140006BB7
0x140006b9e  mov     rcx, [rbx+8]
0x140006ba2  mov     rax, [rcx]
0x140006ba5  mov     rdx, rdi
0x140006ba8  mov     rax, [rax]
0x140006bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bb0  or      bpl, al
0x140006bb3  mov     byte ptr [rbx+28h], 0
0x140006bb7  mov     rbx, [rbx+10h]
0x140006bbb  test    rbx, rbx
0x140006bbe  jnz     short loc_140006B93
0x140006bc0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140006bc7  test    rax, rax
0x140006bca  jz      short loc_140006BEC
0x140006bcc  test    bpl, bpl
0x140006bcf  jnz     short loc_140006BE1
0x140006bd1  test    byte ptr [rdi+4], 2
0x140006bd5  jnz     short loc_140006BE1
0x140006bd7  xor     ecx, ecx
0x140006bd9  jmp     short loc_140006BE3
0x140006bdb  add     rbx, 10h
0x140006bdf  jmp     short loc_140006B69
0x140006be1  mov     cl, 1
0x140006be3  mov     rdx, rdi
0x140006be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006beb  nop
0x140006bec  call    cs:__imp_GetCurrentThreadId
0x140006bf2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006bf8  cmp     ecx, eax
0x140006bfa  jz      short loc_140006C3C
0x140006bfc  mov     ecx, 1
0x140006c01  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140006c09  inc     ecx; this
0x140006c0b  cmp     ecx, 4
0x140006c0e  jge     short loc_140006C35
0x140006c10  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006c16  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140006c1b  test    rax, rax
0x140006c1e  jz      short loc_140006C2B
0x140006c20  mov     rdx, rdi; struct wil::FailureInfo *
0x140006c23  mov     rcx, rax; this
0x140006c26  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140006c2b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006c35  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140006c3c  add     rsp, 20h
0x140006c40  pop     r14
0x140006c42  pop     rdi
0x140006c43  pop     rsi
0x140006c44  pop     rbp
0x140006c45  pop     rbx
0x140006c46  retn
```
