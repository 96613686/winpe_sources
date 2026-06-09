# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800044d0`
- end: `0x180004617`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800044d0`
- `0x180004b0c`
- `0x180004bf0`
- `0x180005bb8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045bc`

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
0x1800044d0  push    rbx
0x1800044d2  push    rbp
0x1800044d3  push    rsi
0x1800044d4  push    rdi
0x1800044d5  push    r14
0x1800044d7  sub     rsp, 20h
0x1800044db  mov     r14, r8
0x1800044de  mov     rsi, rdx
0x1800044e1  mov     rdi, rcx
0x1800044e4  mov     byte ptr [rdx], 0
0x1800044e7  xor     bpl, bpl
0x1800044ea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800044f1  test    rbx, rbx
0x1800044f4  jz      loc_180004590
0x1800044fa  call    cs:__imp_GetCurrentThreadId
0x180004500  mov     r9d, eax
0x180004503  mov     r8d, eax
0x180004506  shr     r8, 2
0x18000450a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004514  mul     r8
0x180004517  shr     rdx, 3
0x18000451b  lea     rcx, [rdx+rdx*4]
0x18000451f  add     rcx, rcx
0x180004522  sub     r8, rcx
0x180004525  mov     rbx, [rbx+r8*8]
0x180004529  jmp     short loc_180004534
0x18000452b  cmp     [rbx], r9d
0x18000452e  jz      short loc_1800045AB
0x180004530  mov     rbx, [rbx+8]
0x180004534  test    rbx, rbx
0x180004537  jnz     short loc_18000452B
0x180004539  test    rbx, rbx
0x18000453c  jz      short loc_180004590
0x18000453e  cmp     qword ptr [rbx], 0
0x180004542  jz      short loc_180004590
0x180004544  mov     [rsi], bpl
0x180004547  mov     r9, r14; unsigned __int64
0x18000454a  mov     r8, rsi; char *
0x18000454d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004550  mov     rcx, rdi; struct wil::FailureInfo *
0x180004553  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004558  test    al, al
0x18000455a  jz      short loc_180004560
0x18000455c  mov     [rdi+48h], rsi
0x180004560  mov     rbx, [rbx]
0x180004563  mov     al, [rbx+28h]
0x180004566  mov     byte ptr [rbx+28h], 1
0x18000456a  test    al, al
0x18000456c  jnz     short loc_180004587
0x18000456e  mov     rcx, [rbx+8]
0x180004572  mov     rax, [rcx]
0x180004575  mov     rdx, rdi
0x180004578  mov     rax, [rax]
0x18000457b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004580  or      bpl, al
0x180004583  mov     byte ptr [rbx+28h], 0
0x180004587  mov     rbx, [rbx+10h]
0x18000458b  test    rbx, rbx
0x18000458e  jnz     short loc_180004563
0x180004590  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004597  test    rax, rax
0x18000459a  jz      short loc_1800045BC
0x18000459c  test    bpl, bpl
0x18000459f  jnz     short loc_1800045B1
0x1800045a1  test    byte ptr [rdi+4], 2
0x1800045a5  jnz     short loc_1800045B1
0x1800045a7  xor     ecx, ecx
0x1800045a9  jmp     short loc_1800045B3
0x1800045ab  add     rbx, 10h
0x1800045af  jmp     short loc_180004539
0x1800045b1  mov     cl, 1
0x1800045b3  mov     rdx, rdi
0x1800045b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045bb  nop
0x1800045bc  call    cs:__imp_GetCurrentThreadId
0x1800045c2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045c8  cmp     ecx, eax
0x1800045ca  jz      short loc_18000460C
0x1800045cc  mov     ecx, 1
0x1800045d1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800045d9  inc     ecx; this
0x1800045db  cmp     ecx, 4
0x1800045de  jge     short loc_180004605
0x1800045e0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045e6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800045eb  test    rax, rax
0x1800045ee  jz      short loc_1800045FB
0x1800045f0  mov     rdx, rdi; struct wil::FailureInfo *
0x1800045f3  mov     rcx, rax; this
0x1800045f6  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1800045fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004605  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000460c  add     rsp, 20h
0x180004610  pop     r14
0x180004612  pop     rdi
0x180004613  pop     rsi
0x180004614  pop     rbp
0x180004615  pop     rbx
0x180004616  retn
```
