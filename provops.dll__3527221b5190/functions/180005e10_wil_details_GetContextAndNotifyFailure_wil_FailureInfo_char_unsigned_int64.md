# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005e10`
- end: `0x180005f57`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005e10`
- `0x180006550`
- `0x180006634`
- `0x180007b68`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005efc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005efc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180005e10  push    rbx
0x180005e12  push    rbp
0x180005e13  push    rsi
0x180005e14  push    rdi
0x180005e15  push    r14
0x180005e17  sub     rsp, 20h
0x180005e1b  mov     r14, r8
0x180005e1e  mov     rsi, rdx
0x180005e21  mov     rdi, rcx
0x180005e24  mov     byte ptr [rdx], 0
0x180005e27  xor     bpl, bpl
0x180005e2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005e31  test    rbx, rbx
0x180005e34  jz      loc_180005ED0
0x180005e3a  call    cs:__imp_GetCurrentThreadId
0x180005e40  mov     r9d, eax
0x180005e43  mov     r8d, eax
0x180005e46  shr     r8, 2
0x180005e4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005e54  mul     r8
0x180005e57  shr     rdx, 3
0x180005e5b  lea     rcx, [rdx+rdx*4]
0x180005e5f  add     rcx, rcx
0x180005e62  sub     r8, rcx
0x180005e65  mov     rbx, [rbx+r8*8]
0x180005e69  jmp     short loc_180005E74
0x180005e6b  cmp     [rbx], r9d
0x180005e6e  jz      short loc_180005EEB
0x180005e70  mov     rbx, [rbx+8]
0x180005e74  test    rbx, rbx
0x180005e77  jnz     short loc_180005E6B
0x180005e79  test    rbx, rbx
0x180005e7c  jz      short loc_180005ED0
0x180005e7e  cmp     qword ptr [rbx], 0
0x180005e82  jz      short loc_180005ED0
0x180005e84  mov     [rsi], bpl
0x180005e87  mov     r9, r14; unsigned __int64
0x180005e8a  mov     r8, rsi; char *
0x180005e8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005e90  mov     rcx, rdi; struct wil::FailureInfo *
0x180005e93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005e98  test    al, al
0x180005e9a  jz      short loc_180005EA0
0x180005e9c  mov     [rdi+48h], rsi
0x180005ea0  mov     rbx, [rbx]
0x180005ea3  mov     al, [rbx+28h]
0x180005ea6  mov     byte ptr [rbx+28h], 1
0x180005eaa  test    al, al
0x180005eac  jnz     short loc_180005EC7
0x180005eae  mov     rcx, [rbx+8]
0x180005eb2  mov     rax, [rcx]
0x180005eb5  mov     rdx, rdi
0x180005eb8  mov     rax, [rax]
0x180005ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec0  or      bpl, al
0x180005ec3  mov     byte ptr [rbx+28h], 0
0x180005ec7  mov     rbx, [rbx+10h]
0x180005ecb  test    rbx, rbx
0x180005ece  jnz     short loc_180005EA3
0x180005ed0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005ed7  test    rax, rax
0x180005eda  jz      short loc_180005EFC
0x180005edc  test    bpl, bpl
0x180005edf  jnz     short loc_180005EF1
0x180005ee1  test    byte ptr [rdi+4], 2
0x180005ee5  jnz     short loc_180005EF1
0x180005ee7  xor     ecx, ecx
0x180005ee9  jmp     short loc_180005EF3
0x180005eeb  add     rbx, 10h
0x180005eef  jmp     short loc_180005E79
0x180005ef1  mov     cl, 1
0x180005ef3  mov     rdx, rdi
0x180005ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005efb  nop
0x180005efc  call    cs:__imp_GetCurrentThreadId
0x180005f02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f08  cmp     ecx, eax
0x180005f0a  jz      short loc_180005F4C
0x180005f0c  mov     ecx, 1
0x180005f11  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005f19  inc     ecx; this
0x180005f1b  cmp     ecx, 4
0x180005f1e  jge     short loc_180005F45
0x180005f20  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f26  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005f2b  test    rax, rax
0x180005f2e  jz      short loc_180005F3B
0x180005f30  mov     rdx, rdi; struct wil::FailureInfo *
0x180005f33  mov     rcx, rax; this
0x180005f36  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180005f3b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f45  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005f4c  add     rsp, 20h
0x180005f50  pop     r14
0x180005f52  pop     rdi
0x180005f53  pop     rsi
0x180005f54  pop     rbp
0x180005f55  pop     rbx
0x180005f56  retn
```
