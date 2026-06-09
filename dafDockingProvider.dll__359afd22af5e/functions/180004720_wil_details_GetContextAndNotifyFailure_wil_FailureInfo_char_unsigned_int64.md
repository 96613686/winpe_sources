# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004720`
- end: `0x180004867`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004720`
- `0x180004d5c`
- `0x180004e40`
- `0x18000709c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000474a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000480c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000474a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000480c`

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
0x180004720  push    rbx
0x180004722  push    rbp
0x180004723  push    rsi
0x180004724  push    rdi
0x180004725  push    r14
0x180004727  sub     rsp, 20h
0x18000472b  mov     r14, r8
0x18000472e  mov     rsi, rdx
0x180004731  mov     rdi, rcx
0x180004734  mov     byte ptr [rdx], 0
0x180004737  xor     bpl, bpl
0x18000473a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004741  test    rbx, rbx
0x180004744  jz      loc_1800047E0
0x18000474a  call    cs:__imp_GetCurrentThreadId
0x180004750  mov     r9d, eax
0x180004753  mov     r8d, eax
0x180004756  shr     r8, 2
0x18000475a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004764  mul     r8
0x180004767  shr     rdx, 3
0x18000476b  lea     rcx, [rdx+rdx*4]
0x18000476f  add     rcx, rcx
0x180004772  sub     r8, rcx
0x180004775  mov     rbx, [rbx+r8*8]
0x180004779  jmp     short loc_180004784
0x18000477b  cmp     [rbx], r9d
0x18000477e  jz      short loc_1800047FB
0x180004780  mov     rbx, [rbx+8]
0x180004784  test    rbx, rbx
0x180004787  jnz     short loc_18000477B
0x180004789  test    rbx, rbx
0x18000478c  jz      short loc_1800047E0
0x18000478e  cmp     qword ptr [rbx], 0
0x180004792  jz      short loc_1800047E0
0x180004794  mov     [rsi], bpl
0x180004797  mov     r9, r14; unsigned __int64
0x18000479a  mov     r8, rsi; char *
0x18000479d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800047a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800047a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800047a8  test    al, al
0x1800047aa  jz      short loc_1800047B0
0x1800047ac  mov     [rdi+48h], rsi
0x1800047b0  mov     rbx, [rbx]
0x1800047b3  mov     al, [rbx+28h]
0x1800047b6  mov     byte ptr [rbx+28h], 1
0x1800047ba  test    al, al
0x1800047bc  jnz     short loc_1800047D7
0x1800047be  mov     rcx, [rbx+8]
0x1800047c2  mov     rax, [rcx]
0x1800047c5  mov     rdx, rdi
0x1800047c8  mov     rax, [rax]
0x1800047cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d0  or      bpl, al
0x1800047d3  mov     byte ptr [rbx+28h], 0
0x1800047d7  mov     rbx, [rbx+10h]
0x1800047db  test    rbx, rbx
0x1800047de  jnz     short loc_1800047B3
0x1800047e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800047e7  test    rax, rax
0x1800047ea  jz      short loc_18000480C
0x1800047ec  test    bpl, bpl
0x1800047ef  jnz     short loc_180004801
0x1800047f1  test    byte ptr [rdi+4], 2
0x1800047f5  jnz     short loc_180004801
0x1800047f7  xor     ecx, ecx
0x1800047f9  jmp     short loc_180004803
0x1800047fb  add     rbx, 10h
0x1800047ff  jmp     short loc_180004789
0x180004801  mov     cl, 1
0x180004803  mov     rdx, rdi
0x180004806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000480b  nop
0x18000480c  call    cs:__imp_GetCurrentThreadId
0x180004812  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004818  cmp     ecx, eax
0x18000481a  jz      short loc_18000485C
0x18000481c  mov     ecx, 1
0x180004821  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004829  inc     ecx; this
0x18000482b  cmp     ecx, 4
0x18000482e  jge     short loc_180004855
0x180004830  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004836  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000483b  test    rax, rax
0x18000483e  jz      short loc_18000484B
0x180004840  mov     rdx, rdi; struct wil::FailureInfo *
0x180004843  mov     rcx, rax; this
0x180004846  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000484b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004855  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000485c  add     rsp, 20h
0x180004860  pop     r14
0x180004862  pop     rdi
0x180004863  pop     rsi
0x180004864  pop     rbp
0x180004865  pop     rbx
0x180004866  retn
```
