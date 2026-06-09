# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000d070`
- end: `0x18000d1de`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `366`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000d070`
- `0x18000da04`
- `0x18000dafc`
- `0x180011ecc`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000d0a8`
- `KERNEL32!GetCurrentThreadId` at `0x18000d16c`
- `KERNEL32!GetCurrentThreadId` at `0x18000d0a8`
- `KERNEL32!GetCurrentThreadId` at `0x18000d16c`

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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
0x18000d070  mov     rax, rsp
0x18000d073  mov     [rax+8], rbx
0x18000d077  mov     [rax+10h], rbp
0x18000d07b  mov     [rax+18h], rsi
0x18000d07f  mov     [rax+20h], rdi
0x18000d083  push    r14
0x18000d085  sub     rsp, 20h
0x18000d089  mov     r14, r8
0x18000d08c  mov     rsi, rdx
0x18000d08f  mov     rdi, rcx
0x18000d092  mov     byte ptr [rdx], 0
0x18000d095  xor     bpl, bpl
0x18000d098  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d09f  test    rbx, rbx
0x18000d0a2  jz      loc_18000D140
0x18000d0a8  call    cs:__imp_GetCurrentThreadId
0x18000d0af  nop     dword ptr [rax+rax+00h]
0x18000d0b4  mov     r9d, eax
0x18000d0b7  mov     r8d, eax
0x18000d0ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d0c4  mul     r9
0x18000d0c7  shr     rdx, 3
0x18000d0cb  lea     rcx, [rdx+rdx*4]
0x18000d0cf  add     rcx, rcx
0x18000d0d2  sub     r8, rcx
0x18000d0d5  mov     rbx, [rbx+r8*8]
0x18000d0d9  jmp     short loc_18000D0E4
0x18000d0db  cmp     [rbx], r9d
0x18000d0de  jz      short loc_18000D15B
0x18000d0e0  mov     rbx, [rbx+8]
0x18000d0e4  test    rbx, rbx
0x18000d0e7  jnz     short loc_18000D0DB
0x18000d0e9  test    rbx, rbx
0x18000d0ec  jz      short loc_18000D140
0x18000d0ee  cmp     qword ptr [rbx], 0
0x18000d0f2  jz      short loc_18000D140
0x18000d0f4  mov     [rsi], bpl
0x18000d0f7  mov     r9, r14; unsigned __int64
0x18000d0fa  mov     r8, rsi; char *
0x18000d0fd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d100  mov     rcx, rdi; struct wil::FailureInfo *
0x18000d103  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d108  test    al, al
0x18000d10a  jz      short loc_18000D110
0x18000d10c  mov     [rdi+48h], rsi
0x18000d110  mov     rbx, [rbx]
0x18000d113  mov     al, [rbx+28h]
0x18000d116  mov     byte ptr [rbx+28h], 1
0x18000d11a  test    al, al
0x18000d11c  jnz     short loc_18000D137
0x18000d11e  mov     rcx, [rbx+8]
0x18000d122  mov     rax, [rcx]
0x18000d125  mov     rdx, rdi
0x18000d128  mov     rax, [rax]
0x18000d12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d130  or      bpl, al
0x18000d133  mov     byte ptr [rbx+28h], 0
0x18000d137  mov     rbx, [rbx+10h]
0x18000d13b  test    rbx, rbx
0x18000d13e  jnz     short loc_18000D113
0x18000d140  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d147  test    rax, rax
0x18000d14a  jz      short loc_18000D16C
0x18000d14c  test    bpl, bpl
0x18000d14f  jnz     short loc_18000D161
0x18000d151  test    byte ptr [rdi+4], 2
0x18000d155  jnz     short loc_18000D161
0x18000d157  xor     ecx, ecx
0x18000d159  jmp     short loc_18000D163
0x18000d15b  add     rbx, 10h
0x18000d15f  jmp     short loc_18000D0E9
0x18000d161  mov     cl, 1
0x18000d163  mov     rdx, rdi
0x18000d166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d16b  nop
0x18000d16c  call    cs:__imp_GetCurrentThreadId
0x18000d173  nop     dword ptr [rax+rax+00h]
0x18000d178  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d17e  cmp     ecx, eax
0x18000d180  jz      short loc_18000D1C2
0x18000d182  mov     ecx, 1
0x18000d187  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d18f  inc     ecx; this
0x18000d191  cmp     ecx, 4
0x18000d194  jge     short loc_18000D1BB
0x18000d196  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d19c  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000d1a1  test    rax, rax
0x18000d1a4  jz      short loc_18000D1B1
0x18000d1a6  mov     rdx, rdi; struct wil::FailureInfo *
0x18000d1a9  mov     rcx, rax; this
0x18000d1ac  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000d1b1  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d1bb  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d1c2  mov     rbx, [rsp+28h+arg_0]
0x18000d1c7  mov     rbp, [rsp+28h+arg_8]
0x18000d1cc  mov     rsi, [rsp+28h+arg_10]
0x18000d1d1  mov     rdi, [rsp+28h+arg_18]
0x18000d1d6  add     rsp, 20h
0x18000d1da  pop     r14
0x18000d1dc  retn
```
