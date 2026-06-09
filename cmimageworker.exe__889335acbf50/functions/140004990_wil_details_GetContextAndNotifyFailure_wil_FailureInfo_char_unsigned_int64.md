# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004990`
- end: `0x140004ae4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004990`
- `0x140004f7c`
- `0x140005060`
- `0x140007500`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400049ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400049ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a82`

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
0x140004990  push    rbx
0x140004992  push    rbp
0x140004993  push    rsi
0x140004994  push    rdi
0x140004995  push    r14
0x140004997  sub     rsp, 20h
0x14000499b  mov     r14, r8
0x14000499e  mov     rsi, rdx
0x1400049a1  mov     rdi, rcx
0x1400049a4  mov     byte ptr [rdx], 0
0x1400049a7  xor     bpl, bpl
0x1400049aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400049b1  test    rbx, rbx
0x1400049b4  jz      loc_140004A56
0x1400049ba  call    cs:__imp_GetCurrentThreadId
0x1400049c1  nop     dword ptr [rax+rax+00h]
0x1400049c6  mov     r9d, eax
0x1400049c9  mov     r8d, eax
0x1400049cc  shr     r8, 2
0x1400049d0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400049da  mul     r8
0x1400049dd  shr     rdx, 3
0x1400049e1  lea     rcx, [rdx+rdx*4]
0x1400049e5  add     rcx, rcx
0x1400049e8  sub     r8, rcx
0x1400049eb  mov     rbx, [rbx+r8*8]
0x1400049ef  jmp     short loc_1400049FA
0x1400049f1  cmp     [rbx], r9d
0x1400049f4  jz      short loc_140004A71
0x1400049f6  mov     rbx, [rbx+8]
0x1400049fa  test    rbx, rbx
0x1400049fd  jnz     short loc_1400049F1
0x1400049ff  test    rbx, rbx
0x140004a02  jz      short loc_140004A56
0x140004a04  cmp     qword ptr [rbx], 0
0x140004a08  jz      short loc_140004A56
0x140004a0a  mov     [rsi], bpl
0x140004a0d  mov     r9, r14; unsigned __int64
0x140004a10  mov     r8, rsi; char *
0x140004a13  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004a16  mov     rcx, rdi; struct wil::FailureInfo *
0x140004a19  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004a1e  test    al, al
0x140004a20  jz      short loc_140004A26
0x140004a22  mov     [rdi+48h], rsi
0x140004a26  mov     rbx, [rbx]
0x140004a29  mov     al, [rbx+28h]
0x140004a2c  mov     byte ptr [rbx+28h], 1
0x140004a30  test    al, al
0x140004a32  jnz     short loc_140004A4D
0x140004a34  mov     rcx, [rbx+8]
0x140004a38  mov     rax, [rcx]
0x140004a3b  mov     rdx, rdi
0x140004a3e  mov     rax, [rax]
0x140004a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a46  or      bpl, al
0x140004a49  mov     byte ptr [rbx+28h], 0
0x140004a4d  mov     rbx, [rbx+10h]
0x140004a51  test    rbx, rbx
0x140004a54  jnz     short loc_140004A29
0x140004a56  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004a5d  test    rax, rax
0x140004a60  jz      short loc_140004A82
0x140004a62  test    bpl, bpl
0x140004a65  jnz     short loc_140004A77
0x140004a67  test    byte ptr [rdi+4], 2
0x140004a6b  jnz     short loc_140004A77
0x140004a6d  xor     ecx, ecx
0x140004a6f  jmp     short loc_140004A79
0x140004a71  add     rbx, 10h
0x140004a75  jmp     short loc_1400049FF
0x140004a77  mov     cl, 1
0x140004a79  mov     rdx, rdi
0x140004a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a81  nop
0x140004a82  call    cs:__imp_GetCurrentThreadId
0x140004a89  nop     dword ptr [rax+rax+00h]
0x140004a8e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004a94  cmp     ecx, eax
0x140004a96  jz      short loc_140004AD8
0x140004a98  mov     ecx, 1
0x140004a9d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004aa5  inc     ecx; this
0x140004aa7  cmp     ecx, 4
0x140004aaa  jge     short loc_140004AD1
0x140004aac  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004ab2  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004ab7  test    rax, rax
0x140004aba  jz      short loc_140004AC7
0x140004abc  mov     rdx, rdi; struct wil::FailureInfo *
0x140004abf  mov     rcx, rax; this
0x140004ac2  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x140004ac7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004ad1  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004ad8  add     rsp, 20h
0x140004adc  pop     r14
0x140004ade  pop     rdi
0x140004adf  pop     rsi
0x140004ae0  pop     rbp
0x140004ae1  pop     rbx
0x140004ae2  retn
```
