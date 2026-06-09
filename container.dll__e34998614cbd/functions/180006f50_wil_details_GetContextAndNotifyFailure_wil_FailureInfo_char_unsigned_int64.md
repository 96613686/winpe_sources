# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006f50`
- end: `0x1800070a4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006f50`
- `0x180007728`
- `0x18000780c`
- `0x18000a94c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007042`

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
0x180006f50  push    rbx
0x180006f52  push    rbp
0x180006f53  push    rsi
0x180006f54  push    rdi
0x180006f55  push    r14
0x180006f57  sub     rsp, 20h
0x180006f5b  mov     r14, r8
0x180006f5e  mov     rsi, rdx
0x180006f61  mov     rdi, rcx
0x180006f64  mov     byte ptr [rdx], 0
0x180006f67  xor     bpl, bpl
0x180006f6a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006f71  test    rbx, rbx
0x180006f74  jz      loc_180007016
0x180006f7a  call    cs:__imp_GetCurrentThreadId
0x180006f81  nop     dword ptr [rax+rax+00h]
0x180006f86  mov     r9d, eax
0x180006f89  mov     r8d, eax
0x180006f8c  shr     r8, 2
0x180006f90  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006f9a  mul     r8
0x180006f9d  shr     rdx, 3
0x180006fa1  lea     rcx, [rdx+rdx*4]
0x180006fa5  add     rcx, rcx
0x180006fa8  sub     r8, rcx
0x180006fab  mov     rbx, [rbx+r8*8]
0x180006faf  jmp     short loc_180006FBA
0x180006fb1  cmp     [rbx], r9d
0x180006fb4  jz      short loc_180007031
0x180006fb6  mov     rbx, [rbx+8]
0x180006fba  test    rbx, rbx
0x180006fbd  jnz     short loc_180006FB1
0x180006fbf  test    rbx, rbx
0x180006fc2  jz      short loc_180007016
0x180006fc4  cmp     qword ptr [rbx], 0
0x180006fc8  jz      short loc_180007016
0x180006fca  mov     [rsi], bpl
0x180006fcd  mov     r9, r14; unsigned __int64
0x180006fd0  mov     r8, rsi; char *
0x180006fd3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006fd6  mov     rcx, rdi; struct wil::FailureInfo *
0x180006fd9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006fde  test    al, al
0x180006fe0  jz      short loc_180006FE6
0x180006fe2  mov     [rdi+48h], rsi
0x180006fe6  mov     rbx, [rbx]
0x180006fe9  mov     al, [rbx+28h]
0x180006fec  mov     byte ptr [rbx+28h], 1
0x180006ff0  test    al, al
0x180006ff2  jnz     short loc_18000700D
0x180006ff4  mov     rcx, [rbx+8]
0x180006ff8  mov     rax, [rcx]
0x180006ffb  mov     rdx, rdi
0x180006ffe  mov     rax, [rax]
0x180007001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007006  or      bpl, al
0x180007009  mov     byte ptr [rbx+28h], 0
0x18000700d  mov     rbx, [rbx+10h]
0x180007011  test    rbx, rbx
0x180007014  jnz     short loc_180006FE9
0x180007016  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000701d  test    rax, rax
0x180007020  jz      short loc_180007042
0x180007022  test    bpl, bpl
0x180007025  jnz     short loc_180007037
0x180007027  test    byte ptr [rdi+4], 2
0x18000702b  jnz     short loc_180007037
0x18000702d  xor     ecx, ecx
0x18000702f  jmp     short loc_180007039
0x180007031  add     rbx, 10h
0x180007035  jmp     short loc_180006FBF
0x180007037  mov     cl, 1
0x180007039  mov     rdx, rdi
0x18000703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007041  nop
0x180007042  call    cs:__imp_GetCurrentThreadId
0x180007049  nop     dword ptr [rax+rax+00h]
0x18000704e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007054  cmp     ecx, eax
0x180007056  jz      short loc_180007098
0x180007058  mov     ecx, 1
0x18000705d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007065  inc     ecx; this
0x180007067  cmp     ecx, 4
0x18000706a  jge     short loc_180007091
0x18000706c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007072  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007077  test    rax, rax
0x18000707a  jz      short loc_180007087
0x18000707c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000707f  mov     rcx, rax; this
0x180007082  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180007087  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007091  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007098  add     rsp, 20h
0x18000709c  pop     r14
0x18000709e  pop     rdi
0x18000709f  pop     rsi
0x1800070a0  pop     rbp
0x1800070a1  pop     rbx
0x1800070a2  retn
```
