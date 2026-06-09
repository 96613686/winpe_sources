# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000ccd0`
- end: `0x18000ce24`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000ccd0`
- `0x18000d0b0`
- `0x18000d194`
- `0x1800129d0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdc2`

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
0x18000ccd0  push    rbx
0x18000ccd2  push    rbp
0x18000ccd3  push    rsi
0x18000ccd4  push    rdi
0x18000ccd5  push    r14
0x18000ccd7  sub     rsp, 20h
0x18000ccdb  mov     r14, r8
0x18000ccde  mov     rsi, rdx
0x18000cce1  mov     rdi, rcx
0x18000cce4  mov     byte ptr [rdx], 0
0x18000cce7  xor     bpl, bpl
0x18000ccea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ccf1  test    rbx, rbx
0x18000ccf4  jz      loc_18000CD96
0x18000ccfa  call    cs:__imp_GetCurrentThreadId
0x18000cd01  nop     dword ptr [rax+rax+00h]
0x18000cd06  mov     r9d, eax
0x18000cd09  mov     r8d, eax
0x18000cd0c  shr     r8, 2
0x18000cd10  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000cd1a  mul     r8
0x18000cd1d  shr     rdx, 3
0x18000cd21  lea     rcx, [rdx+rdx*4]
0x18000cd25  add     rcx, rcx
0x18000cd28  sub     r8, rcx
0x18000cd2b  mov     rbx, [rbx+r8*8]
0x18000cd2f  jmp     short loc_18000CD3A
0x18000cd31  cmp     [rbx], r9d
0x18000cd34  jz      short loc_18000CDB1
0x18000cd36  mov     rbx, [rbx+8]
0x18000cd3a  test    rbx, rbx
0x18000cd3d  jnz     short loc_18000CD31
0x18000cd3f  test    rbx, rbx
0x18000cd42  jz      short loc_18000CD96
0x18000cd44  cmp     qword ptr [rbx], 0
0x18000cd48  jz      short loc_18000CD96
0x18000cd4a  mov     [rsi], bpl
0x18000cd4d  mov     r9, r14; unsigned __int64
0x18000cd50  mov     r8, rsi; char *
0x18000cd53  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000cd56  mov     rcx, rdi; struct wil::FailureInfo *
0x18000cd59  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000cd5e  test    al, al
0x18000cd60  jz      short loc_18000CD66
0x18000cd62  mov     [rdi+48h], rsi
0x18000cd66  mov     rbx, [rbx]
0x18000cd69  mov     al, [rbx+28h]
0x18000cd6c  mov     byte ptr [rbx+28h], 1
0x18000cd70  test    al, al
0x18000cd72  jnz     short loc_18000CD8D
0x18000cd74  mov     rcx, [rbx+8]
0x18000cd78  mov     rax, [rcx]
0x18000cd7b  mov     rdx, rdi
0x18000cd7e  mov     rax, [rax]
0x18000cd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd86  or      bpl, al
0x18000cd89  mov     byte ptr [rbx+28h], 0
0x18000cd8d  mov     rbx, [rbx+10h]
0x18000cd91  test    rbx, rbx
0x18000cd94  jnz     short loc_18000CD69
0x18000cd96  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000cd9d  test    rax, rax
0x18000cda0  jz      short loc_18000CDC2
0x18000cda2  test    bpl, bpl
0x18000cda5  jnz     short loc_18000CDB7
0x18000cda7  test    byte ptr [rdi+4], 2
0x18000cdab  jnz     short loc_18000CDB7
0x18000cdad  xor     ecx, ecx
0x18000cdaf  jmp     short loc_18000CDB9
0x18000cdb1  add     rbx, 10h
0x18000cdb5  jmp     short loc_18000CD3F
0x18000cdb7  mov     cl, 1
0x18000cdb9  mov     rdx, rdi
0x18000cdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc1  nop
0x18000cdc2  call    cs:__imp_GetCurrentThreadId
0x18000cdc9  nop     dword ptr [rax+rax+00h]
0x18000cdce  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000cdd4  cmp     ecx, eax
0x18000cdd6  jz      short loc_18000CE18
0x18000cdd8  mov     ecx, 1
0x18000cddd  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000cde5  inc     ecx; this
0x18000cde7  cmp     ecx, 4
0x18000cdea  jge     short loc_18000CE11
0x18000cdec  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000cdf2  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000cdf7  test    rax, rax
0x18000cdfa  jz      short loc_18000CE07
0x18000cdfc  mov     rdx, rdi; struct wil::FailureInfo *
0x18000cdff  mov     rcx, rax; this
0x18000ce02  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000ce07  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000ce11  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000ce18  add     rsp, 20h
0x18000ce1c  pop     r14
0x18000ce1e  pop     rdi
0x18000ce1f  pop     rsi
0x18000ce20  pop     rbp
0x18000ce21  pop     rbx
0x18000ce22  retn
```
