# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800038e0`
- end: `0x180003a27`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800038e0`
- `0x180003f1c`
- `0x180004000`
- `0x180005234`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000390a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000390a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039cc`

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
0x1800038e0  push    rbx
0x1800038e2  push    rbp
0x1800038e3  push    rsi
0x1800038e4  push    rdi
0x1800038e5  push    r14
0x1800038e7  sub     rsp, 20h
0x1800038eb  mov     r14, r8
0x1800038ee  mov     rsi, rdx
0x1800038f1  mov     rdi, rcx
0x1800038f4  mov     byte ptr [rdx], 0
0x1800038f7  xor     bpl, bpl
0x1800038fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003901  test    rbx, rbx
0x180003904  jz      loc_1800039A0
0x18000390a  call    cs:__imp_GetCurrentThreadId
0x180003910  mov     r9d, eax
0x180003913  mov     r8d, eax
0x180003916  shr     r8, 2
0x18000391a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003924  mul     r8
0x180003927  shr     rdx, 3
0x18000392b  lea     rcx, [rdx+rdx*4]
0x18000392f  add     rcx, rcx
0x180003932  sub     r8, rcx
0x180003935  mov     rbx, [rbx+r8*8]
0x180003939  jmp     short loc_180003944
0x18000393b  cmp     [rbx], r9d
0x18000393e  jz      short loc_1800039BB
0x180003940  mov     rbx, [rbx+8]
0x180003944  test    rbx, rbx
0x180003947  jnz     short loc_18000393B
0x180003949  test    rbx, rbx
0x18000394c  jz      short loc_1800039A0
0x18000394e  cmp     qword ptr [rbx], 0
0x180003952  jz      short loc_1800039A0
0x180003954  mov     [rsi], bpl
0x180003957  mov     r9, r14; unsigned __int64
0x18000395a  mov     r8, rsi; char *
0x18000395d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003960  mov     rcx, rdi; struct wil::FailureInfo *
0x180003963  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003968  test    al, al
0x18000396a  jz      short loc_180003970
0x18000396c  mov     [rdi+48h], rsi
0x180003970  mov     rbx, [rbx]
0x180003973  mov     al, [rbx+28h]
0x180003976  mov     byte ptr [rbx+28h], 1
0x18000397a  test    al, al
0x18000397c  jnz     short loc_180003997
0x18000397e  mov     rcx, [rbx+8]
0x180003982  mov     rax, [rcx]
0x180003985  mov     rdx, rdi
0x180003988  mov     rax, [rax]
0x18000398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003990  or      bpl, al
0x180003993  mov     byte ptr [rbx+28h], 0
0x180003997  mov     rbx, [rbx+10h]
0x18000399b  test    rbx, rbx
0x18000399e  jnz     short loc_180003973
0x1800039a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800039a7  test    rax, rax
0x1800039aa  jz      short loc_1800039CC
0x1800039ac  test    bpl, bpl
0x1800039af  jnz     short loc_1800039C1
0x1800039b1  test    byte ptr [rdi+4], 2
0x1800039b5  jnz     short loc_1800039C1
0x1800039b7  xor     ecx, ecx
0x1800039b9  jmp     short loc_1800039C3
0x1800039bb  add     rbx, 10h
0x1800039bf  jmp     short loc_180003949
0x1800039c1  mov     cl, 1
0x1800039c3  mov     rdx, rdi
0x1800039c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039cb  nop
0x1800039cc  call    cs:__imp_GetCurrentThreadId
0x1800039d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800039d8  cmp     ecx, eax
0x1800039da  jz      short loc_180003A1C
0x1800039dc  mov     ecx, 1
0x1800039e1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800039e9  inc     ecx; this
0x1800039eb  cmp     ecx, 4
0x1800039ee  jge     short loc_180003A15
0x1800039f0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800039f6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800039fb  test    rax, rax
0x1800039fe  jz      short loc_180003A0B
0x180003a00  mov     rdx, rdi; struct wil::FailureInfo *
0x180003a03  mov     rcx, rax; this
0x180003a06  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180003a0b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003a15  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003a1c  add     rsp, 20h
0x180003a20  pop     r14
0x180003a22  pop     rdi
0x180003a23  pop     rsi
0x180003a24  pop     rbp
0x180003a25  pop     rbx
0x180003a26  retn
```
