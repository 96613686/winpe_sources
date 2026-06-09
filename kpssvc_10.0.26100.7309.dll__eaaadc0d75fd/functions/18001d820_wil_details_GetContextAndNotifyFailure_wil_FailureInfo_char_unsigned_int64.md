# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001d820`
- end: `0x18001d97e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `350`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001d820`
- `0x18001dea4`
- `0x18001dfa4`
- `0x180025424`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d90c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d90c`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r10
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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
        v11 = (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        v3 |= v11;
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
0x18001d820  mov     rax, rsp
0x18001d823  mov     [rax+8], rbx
0x18001d827  mov     [rax+10h], rbp
0x18001d82b  mov     [rax+18h], rsi
0x18001d82f  mov     [rax+20h], rdi
0x18001d833  push    r14
0x18001d835  sub     rsp, 20h
0x18001d839  mov     byte ptr [rdx], 0
0x18001d83c  xor     bpl, bpl
0x18001d83f  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001d846  mov     r14, r8
0x18001d849  mov     rsi, rdx
0x18001d84c  mov     rdi, rcx
0x18001d84f  test    rbx, rbx
0x18001d852  jz      loc_18001D8E1
0x18001d858  call    cs:__imp_GetCurrentThreadId
0x18001d85f  nop     dword ptr [rax+rax+00h]
0x18001d864  mov     r9d, eax
0x18001d867  mov     r10d, eax
0x18001d86a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001d874  mul     r10
0x18001d877  shr     rdx, 3
0x18001d87b  lea     rcx, [rdx+rdx*4]
0x18001d87f  add     rcx, rcx
0x18001d882  sub     r9, rcx
0x18001d885  mov     rbx, [rbx+r9*8]
0x18001d889  jmp     short loc_18001D894
0x18001d88b  cmp     [rbx], r10d
0x18001d88e  jz      short loc_18001D8FC
0x18001d890  mov     rbx, [rbx+8]
0x18001d894  test    rbx, rbx
0x18001d897  jnz     short loc_18001D88B
0x18001d899  test    rbx, rbx
0x18001d89c  jz      short loc_18001D8E1
0x18001d89e  cmp     qword ptr [rbx], 0
0x18001d8a2  jz      short loc_18001D8E1
0x18001d8a4  mov     [rsi], bpl
0x18001d8a7  mov     r9, r14; unsigned __int64
0x18001d8aa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001d8ad  mov     r8, rsi; char *
0x18001d8b0  mov     rcx, rdi; struct wil::FailureInfo *
0x18001d8b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001d8b8  test    al, al
0x18001d8ba  jz      short loc_18001D8C0
0x18001d8bc  mov     [rdi+48h], rsi
0x18001d8c0  mov     rbx, [rbx]
0x18001d8c3  mov     rcx, [rbx+8]
0x18001d8c7  mov     rdx, rdi
0x18001d8ca  mov     rax, [rcx]
0x18001d8cd  mov     rax, [rax]
0x18001d8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d5  mov     rbx, [rbx+10h]
0x18001d8d9  or      bpl, al
0x18001d8dc  test    rbx, rbx
0x18001d8df  jnz     short loc_18001D8C3
0x18001d8e1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001d8e8  test    rax, rax
0x18001d8eb  jz      short loc_18001D90C
0x18001d8ed  test    bpl, bpl
0x18001d8f0  jnz     short loc_18001D902
0x18001d8f2  test    byte ptr [rdi+4], 2
0x18001d8f6  jnz     short loc_18001D902
0x18001d8f8  xor     ecx, ecx
0x18001d8fa  jmp     short loc_18001D904
0x18001d8fc  add     rbx, 10h
0x18001d900  jmp     short loc_18001D899
0x18001d902  mov     cl, 1
0x18001d904  mov     rdx, rdi
0x18001d907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d90c  call    cs:__imp_GetCurrentThreadId
0x18001d913  nop     dword ptr [rax+rax+00h]
0x18001d918  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001d91e  cmp     ecx, eax
0x18001d920  jz      short loc_18001D962
0x18001d922  mov     ecx, 1
0x18001d927  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001d92f  inc     ecx; this
0x18001d931  cmp     ecx, 4
0x18001d934  jge     short loc_18001D95B
0x18001d936  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001d93c  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18001d941  test    rax, rax
0x18001d944  jz      short loc_18001D951
0x18001d946  mov     rdx, rdi; struct wil::FailureInfo *
0x18001d949  mov     rcx, rax; this
0x18001d94c  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18001d951  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001d95b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001d962  mov     rbx, [rsp+28h+arg_0]
0x18001d967  mov     rbp, [rsp+28h+arg_8]
0x18001d96c  mov     rsi, [rsp+28h+arg_10]
0x18001d971  mov     rdi, [rsp+28h+arg_18]
0x18001d976  add     rsp, 20h
0x18001d97a  pop     r14
0x18001d97c  retn
```
