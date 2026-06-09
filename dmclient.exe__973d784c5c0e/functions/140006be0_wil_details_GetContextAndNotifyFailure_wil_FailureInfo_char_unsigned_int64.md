# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140006be0`
- end: `0x140006d34`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140006be0`
- `0x1400072ac`
- `0x140007398`
- `0x14000b5b4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006cd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006cd2`

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
0x140006be0  push    rbx
0x140006be2  push    rbp
0x140006be3  push    rsi
0x140006be4  push    rdi
0x140006be5  push    r14
0x140006be7  sub     rsp, 20h
0x140006beb  mov     r14, r8
0x140006bee  mov     rsi, rdx
0x140006bf1  mov     rdi, rcx
0x140006bf4  mov     byte ptr [rdx], 0
0x140006bf7  xor     bpl, bpl
0x140006bfa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006c01  test    rbx, rbx
0x140006c04  jz      loc_140006CA6
0x140006c0a  call    cs:__imp_GetCurrentThreadId
0x140006c11  nop     dword ptr [rax+rax+00h]
0x140006c16  mov     r9d, eax
0x140006c19  mov     r8d, eax
0x140006c1c  shr     r8, 2
0x140006c20  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006c2a  mul     r8
0x140006c2d  shr     rdx, 3
0x140006c31  lea     rcx, [rdx+rdx*4]
0x140006c35  add     rcx, rcx
0x140006c38  sub     r8, rcx
0x140006c3b  mov     rbx, [rbx+r8*8]
0x140006c3f  jmp     short loc_140006C4A
0x140006c41  cmp     [rbx], r9d
0x140006c44  jz      short loc_140006CC1
0x140006c46  mov     rbx, [rbx+8]
0x140006c4a  test    rbx, rbx
0x140006c4d  jnz     short loc_140006C41
0x140006c4f  test    rbx, rbx
0x140006c52  jz      short loc_140006CA6
0x140006c54  cmp     qword ptr [rbx], 0
0x140006c58  jz      short loc_140006CA6
0x140006c5a  mov     [rsi], bpl
0x140006c5d  mov     r9, r14; unsigned __int64
0x140006c60  mov     r8, rsi; char *
0x140006c63  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140006c66  mov     rcx, rdi; struct wil::FailureInfo *
0x140006c69  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006c6e  test    al, al
0x140006c70  jz      short loc_140006C76
0x140006c72  mov     [rdi+48h], rsi
0x140006c76  mov     rbx, [rbx]
0x140006c79  mov     al, [rbx+28h]
0x140006c7c  mov     byte ptr [rbx+28h], 1
0x140006c80  test    al, al
0x140006c82  jnz     short loc_140006C9D
0x140006c84  mov     rcx, [rbx+8]
0x140006c88  mov     rax, [rcx]
0x140006c8b  mov     rdx, rdi
0x140006c8e  mov     rax, [rax]
0x140006c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c96  or      bpl, al
0x140006c99  mov     byte ptr [rbx+28h], 0
0x140006c9d  mov     rbx, [rbx+10h]
0x140006ca1  test    rbx, rbx
0x140006ca4  jnz     short loc_140006C79
0x140006ca6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140006cad  test    rax, rax
0x140006cb0  jz      short loc_140006CD2
0x140006cb2  test    bpl, bpl
0x140006cb5  jnz     short loc_140006CC7
0x140006cb7  test    byte ptr [rdi+4], 2
0x140006cbb  jnz     short loc_140006CC7
0x140006cbd  xor     ecx, ecx
0x140006cbf  jmp     short loc_140006CC9
0x140006cc1  add     rbx, 10h
0x140006cc5  jmp     short loc_140006C4F
0x140006cc7  mov     cl, 1
0x140006cc9  mov     rdx, rdi
0x140006ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cd1  nop
0x140006cd2  call    cs:__imp_GetCurrentThreadId
0x140006cd9  nop     dword ptr [rax+rax+00h]
0x140006cde  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006ce4  cmp     ecx, eax
0x140006ce6  jz      short loc_140006D28
0x140006ce8  mov     ecx, 1
0x140006ced  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140006cf5  inc     ecx; this
0x140006cf7  cmp     ecx, 4
0x140006cfa  jge     short loc_140006D21
0x140006cfc  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006d02  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140006d07  test    rax, rax
0x140006d0a  jz      short loc_140006D17
0x140006d0c  mov     rdx, rdi; struct wil::FailureInfo *
0x140006d0f  mov     rcx, rax; this
0x140006d12  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140006d17  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006d21  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140006d28  add     rsp, 20h
0x140006d2c  pop     r14
0x140006d2e  pop     rdi
0x140006d2f  pop     rsi
0x140006d30  pop     rbp
0x140006d31  pop     rbx
0x140006d32  retn
```
