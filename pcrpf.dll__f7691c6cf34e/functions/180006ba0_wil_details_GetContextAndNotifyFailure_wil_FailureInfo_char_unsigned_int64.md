# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006ba0`
- end: `0x180006cf4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006ba0`
- `0x1800072c4`
- `0x1800073a8`
- `0x18000a29c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c92`

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
0x180006ba0  push    rbx
0x180006ba2  push    rbp
0x180006ba3  push    rsi
0x180006ba4  push    rdi
0x180006ba5  push    r14
0x180006ba7  sub     rsp, 20h
0x180006bab  mov     r14, r8
0x180006bae  mov     rsi, rdx
0x180006bb1  mov     rdi, rcx
0x180006bb4  mov     byte ptr [rdx], 0
0x180006bb7  xor     bpl, bpl
0x180006bba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006bc1  test    rbx, rbx
0x180006bc4  jz      loc_180006C66
0x180006bca  call    cs:__imp_GetCurrentThreadId
0x180006bd1  nop     dword ptr [rax+rax+00h]
0x180006bd6  mov     r9d, eax
0x180006bd9  mov     r8d, eax
0x180006bdc  shr     r8, 2
0x180006be0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006bea  mul     r8
0x180006bed  shr     rdx, 3
0x180006bf1  lea     rcx, [rdx+rdx*4]
0x180006bf5  add     rcx, rcx
0x180006bf8  sub     r8, rcx
0x180006bfb  mov     rbx, [rbx+r8*8]
0x180006bff  jmp     short loc_180006C0A
0x180006c01  cmp     [rbx], r9d
0x180006c04  jz      short loc_180006C81
0x180006c06  mov     rbx, [rbx+8]
0x180006c0a  test    rbx, rbx
0x180006c0d  jnz     short loc_180006C01
0x180006c0f  test    rbx, rbx
0x180006c12  jz      short loc_180006C66
0x180006c14  cmp     qword ptr [rbx], 0
0x180006c18  jz      short loc_180006C66
0x180006c1a  mov     [rsi], bpl
0x180006c1d  mov     r9, r14; unsigned __int64
0x180006c20  mov     r8, rsi; char *
0x180006c23  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006c26  mov     rcx, rdi; struct wil::FailureInfo *
0x180006c29  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006c2e  test    al, al
0x180006c30  jz      short loc_180006C36
0x180006c32  mov     [rdi+48h], rsi
0x180006c36  mov     rbx, [rbx]
0x180006c39  mov     al, [rbx+28h]
0x180006c3c  mov     byte ptr [rbx+28h], 1
0x180006c40  test    al, al
0x180006c42  jnz     short loc_180006C5D
0x180006c44  mov     rcx, [rbx+8]
0x180006c48  mov     rax, [rcx]
0x180006c4b  mov     rdx, rdi
0x180006c4e  mov     rax, [rax]
0x180006c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c56  or      bpl, al
0x180006c59  mov     byte ptr [rbx+28h], 0
0x180006c5d  mov     rbx, [rbx+10h]
0x180006c61  test    rbx, rbx
0x180006c64  jnz     short loc_180006C39
0x180006c66  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006c6d  test    rax, rax
0x180006c70  jz      short loc_180006C92
0x180006c72  test    bpl, bpl
0x180006c75  jnz     short loc_180006C87
0x180006c77  test    byte ptr [rdi+4], 2
0x180006c7b  jnz     short loc_180006C87
0x180006c7d  xor     ecx, ecx
0x180006c7f  jmp     short loc_180006C89
0x180006c81  add     rbx, 10h
0x180006c85  jmp     short loc_180006C0F
0x180006c87  mov     cl, 1
0x180006c89  mov     rdx, rdi
0x180006c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c91  nop
0x180006c92  call    cs:__imp_GetCurrentThreadId
0x180006c99  nop     dword ptr [rax+rax+00h]
0x180006c9e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006ca4  cmp     ecx, eax
0x180006ca6  jz      short loc_180006CE8
0x180006ca8  mov     ecx, 1
0x180006cad  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006cb5  inc     ecx; this
0x180006cb7  cmp     ecx, 4
0x180006cba  jge     short loc_180006CE1
0x180006cbc  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006cc2  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006cc7  test    rax, rax
0x180006cca  jz      short loc_180006CD7
0x180006ccc  mov     rdx, rdi; struct wil::FailureInfo *
0x180006ccf  mov     rcx, rax; this
0x180006cd2  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180006cd7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006ce1  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006ce8  add     rsp, 20h
0x180006cec  pop     r14
0x180006cee  pop     rdi
0x180006cef  pop     rsi
0x180006cf0  pop     rbp
0x180006cf1  pop     rbx
0x180006cf2  retn
```
