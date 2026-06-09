# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x14000fba0`
- end: `0x14000fda7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000fba0`
- `0x14001029c`
- `0x140010380`
- `0x140010df8`
- `0x140012644`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fbca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fc8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fbca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fc8c`

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
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

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
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x14000fba0  push    rbx
0x14000fba2  push    rbp
0x14000fba3  push    rsi
0x14000fba4  push    rdi
0x14000fba5  push    r14
0x14000fba7  sub     rsp, 20h
0x14000fbab  mov     r14, r8
0x14000fbae  mov     rsi, rdx
0x14000fbb1  mov     rdi, rcx
0x14000fbb4  mov     byte ptr [rdx], 0
0x14000fbb7  xor     bpl, bpl
0x14000fbba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000fbc1  test    rbx, rbx
0x14000fbc4  jz      loc_14000FC60
0x14000fbca  call    cs:__imp_GetCurrentThreadId
0x14000fbd0  mov     r9d, eax
0x14000fbd3  mov     r8d, eax
0x14000fbd6  shr     r8, 2
0x14000fbda  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000fbe4  mul     r8
0x14000fbe7  shr     rdx, 3
0x14000fbeb  lea     rcx, [rdx+rdx*4]
0x14000fbef  add     rcx, rcx
0x14000fbf2  sub     r8, rcx
0x14000fbf5  mov     rbx, [rbx+r8*8]
0x14000fbf9  jmp     short loc_14000FC04
0x14000fbfb  cmp     [rbx], r9d
0x14000fbfe  jz      short loc_14000FC7B
0x14000fc00  mov     rbx, [rbx+8]
0x14000fc04  test    rbx, rbx
0x14000fc07  jnz     short loc_14000FBFB
0x14000fc09  test    rbx, rbx
0x14000fc0c  jz      short loc_14000FC60
0x14000fc0e  cmp     qword ptr [rbx], 0
0x14000fc12  jz      short loc_14000FC60
0x14000fc14  mov     [rsi], bpl
0x14000fc17  mov     r9, r14; unsigned __int64
0x14000fc1a  mov     r8, rsi; char *
0x14000fc1d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000fc20  mov     rcx, rdi; struct wil::FailureInfo *
0x14000fc23  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000fc28  test    al, al
0x14000fc2a  jz      short loc_14000FC30
0x14000fc2c  mov     [rdi+48h], rsi
0x14000fc30  mov     rbx, [rbx]
0x14000fc33  mov     al, [rbx+28h]
0x14000fc36  mov     byte ptr [rbx+28h], 1
0x14000fc3a  test    al, al
0x14000fc3c  jnz     short loc_14000FC57
0x14000fc3e  mov     rcx, [rbx+8]
0x14000fc42  mov     rax, [rcx]
0x14000fc45  mov     rdx, rdi
0x14000fc48  mov     rax, [rax]
0x14000fc4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc50  or      bpl, al
0x14000fc53  mov     byte ptr [rbx+28h], 0
0x14000fc57  mov     rbx, [rbx+10h]
0x14000fc5b  test    rbx, rbx
0x14000fc5e  jnz     short loc_14000FC33
0x14000fc60  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000fc67  test    rax, rax
0x14000fc6a  jz      short loc_14000FC8C
0x14000fc6c  test    bpl, bpl
0x14000fc6f  jnz     short loc_14000FC81
0x14000fc71  test    byte ptr [rdi+4], 2
0x14000fc75  jnz     short loc_14000FC81
0x14000fc77  xor     ecx, ecx
0x14000fc79  jmp     short loc_14000FC83
0x14000fc7b  add     rbx, 10h
0x14000fc7f  jmp     short loc_14000FC09
0x14000fc81  mov     cl, 1
0x14000fc83  mov     rdx, rdi
0x14000fc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc8b  nop
0x14000fc8c  call    cs:__imp_GetCurrentThreadId
0x14000fc92  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000fc98  cmp     ecx, eax
0x14000fc9a  jz      loc_14000FD9C
0x14000fca0  mov     ecx, 1
0x14000fca5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000fcad  inc     ecx; this
0x14000fcaf  cmp     ecx, 4
0x14000fcb2  jge     loc_14000FD95
0x14000fcb8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000fcbe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000fcc3  mov     rbx, rax
0x14000fcc6  test    rax, rax
0x14000fcc9  jz      loc_14000FD8B
0x14000fccf  mov     esi, [rax+10h]
0x14000fcd2  mov     ebp, 50h ; 'P'
0x14000fcd7  cmp     qword ptr [rax+18h], 0
0x14000fcdc  jnz     short loc_14000FD13
0x14000fcde  test    esi, esi
0x14000fce0  jz      short loc_14000FD13
0x14000fce2  mov     edx, 190h; dwBytes
0x14000fce7  lea     ecx, [rbp-48h]; dwFlags
0x14000fcea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000fcef  mov     [rbx+18h], rax
0x14000fcf3  test    rax, rax
0x14000fcf6  jz      short loc_14000FD13
0x14000fcf8  mov     dword ptr [rbx+20h], 5
0x14000fcff  lea     rcx, [rax+190h]
0x14000fd06  jmp     short loc_14000FD0E
0x14000fd08  mov     [rax], bp
0x14000fd0b  add     rax, rbp
0x14000fd0e  cmp     rax, rcx
0x14000fd11  jnz     short loc_14000FD08
0x14000fd13  mov     r9, [rbx+18h]
0x14000fd17  test    r9, r9
0x14000fd1a  jz      short loc_14000FD8B
0x14000fd1c  test    esi, esi
0x14000fd1e  jz      short loc_14000FD51
0x14000fd20  mov     rcx, r9
0x14000fd23  movzx   eax, word ptr [rbx+20h]
0x14000fd27  lea     rdx, [rax+rax*4]
0x14000fd2b  shl     rdx, 4
0x14000fd2f  add     rdx, r9
0x14000fd32  cmp     r9, rdx
0x14000fd35  jz      short loc_14000FD51
0x14000fd37  mov     r8d, [rbx+10h]
0x14000fd3b  cmp     [rcx+4], r8d
0x14000fd3f  jbe     short loc_14000FD49
0x14000fd41  mov     eax, [rdi+8]
0x14000fd44  cmp     [rcx+8], eax
0x14000fd47  jz      short loc_14000FD8B
0x14000fd49  add     rcx, rbp
0x14000fd4c  cmp     rcx, rdx
0x14000fd4f  jnz     short loc_14000FD3B
0x14000fd51  movzx   eax, word ptr [rbx+22h]
0x14000fd55  inc     eax
0x14000fd57  movzx   ecx, word ptr [rbx+20h]
0x14000fd5b  xor     edx, edx
0x14000fd5d  div     ecx
0x14000fd5f  mov     [rbx+22h], dx
0x14000fd63  mov     rax, [rbx+8]
0x14000fd67  mov     r8d, 1
0x14000fd6d  lock xadd [rax], r8d
0x14000fd72  inc     r8d; unsigned int
0x14000fd75  movzx   eax, dx
0x14000fd78  lea     rcx, [rax+rax*4]
0x14000fd7c  shl     rcx, 4
0x14000fd80  add     rcx, r9; this
0x14000fd83  mov     rdx, rdi; struct wil::FailureInfo *
0x14000fd86  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000fd8b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000fd95  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000fd9c  add     rsp, 20h
0x14000fda0  pop     r14
0x14000fda2  pop     rdi
0x14000fda3  pop     rsi
0x14000fda4  pop     rbp
0x14000fda5  pop     rbx
0x14000fda6  retn
```
