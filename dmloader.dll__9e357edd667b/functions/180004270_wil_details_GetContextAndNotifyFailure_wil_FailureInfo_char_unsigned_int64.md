# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004270`
- end: `0x180004476`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004270`
- `0x180004968`
- `0x180004a4c`
- `0x1800053f8`
- `0x1800068d8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000429a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000435b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000429a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000435b`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x180004270  push    rbx
0x180004272  push    rbp
0x180004273  push    rsi
0x180004274  push    rdi
0x180004275  push    r14
0x180004277  sub     rsp, 20h
0x18000427b  mov     byte ptr [rdx], 0
0x18000427e  xor     bpl, bpl
0x180004281  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004288  mov     r14, r8
0x18000428b  mov     rsi, rdx
0x18000428e  mov     rdi, rcx
0x180004291  test    rbx, rbx
0x180004294  jz      loc_180004330
0x18000429a  call    cs:__imp_GetCurrentThreadId
0x1800042a0  mov     r8d, eax
0x1800042a3  mov     r9d, eax
0x1800042a6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800042b0  shr     r8, 2
0x1800042b4  mul     r8
0x1800042b7  shr     rdx, 3
0x1800042bb  lea     rcx, [rdx+rdx*4]
0x1800042bf  add     rcx, rcx
0x1800042c2  sub     r8, rcx
0x1800042c5  mov     rbx, [rbx+r8*8]
0x1800042c9  jmp     short loc_1800042D4
0x1800042cb  cmp     [rbx], r9d
0x1800042ce  jz      short loc_18000434B
0x1800042d0  mov     rbx, [rbx+8]
0x1800042d4  test    rbx, rbx
0x1800042d7  jnz     short loc_1800042CB
0x1800042d9  test    rbx, rbx
0x1800042dc  jz      short loc_180004330
0x1800042de  cmp     qword ptr [rbx], 0
0x1800042e2  jz      short loc_180004330
0x1800042e4  mov     [rsi], bpl
0x1800042e7  mov     r9, r14; unsigned __int64
0x1800042ea  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800042ed  mov     r8, rsi; char *
0x1800042f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800042f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800042f8  test    al, al
0x1800042fa  jz      short loc_180004300
0x1800042fc  mov     [rdi+48h], rsi
0x180004300  mov     rbx, [rbx]
0x180004303  mov     al, [rbx+28h]
0x180004306  mov     byte ptr [rbx+28h], 1
0x18000430a  test    al, al
0x18000430c  jnz     short loc_180004327
0x18000430e  mov     rcx, [rbx+8]
0x180004312  mov     rdx, rdi
0x180004315  mov     rax, [rcx]
0x180004318  mov     rax, [rax]
0x18000431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004320  or      bpl, al
0x180004323  mov     byte ptr [rbx+28h], 0
0x180004327  mov     rbx, [rbx+10h]
0x18000432b  test    rbx, rbx
0x18000432e  jnz     short loc_180004303
0x180004330  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004337  test    rax, rax
0x18000433a  jz      short loc_18000435B
0x18000433c  test    bpl, bpl
0x18000433f  jnz     short loc_180004351
0x180004341  test    byte ptr [rdi+4], 2
0x180004345  jnz     short loc_180004351
0x180004347  xor     ecx, ecx
0x180004349  jmp     short loc_180004353
0x18000434b  add     rbx, 10h
0x18000434f  jmp     short loc_1800042D9
0x180004351  mov     cl, 1
0x180004353  mov     rdx, rdi
0x180004356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435b  call    cs:__imp_GetCurrentThreadId
0x180004361  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004367  cmp     ecx, eax
0x180004369  jz      loc_18000446B
0x18000436f  mov     ecx, 1
0x180004374  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000437c  inc     ecx; this
0x18000437e  cmp     ecx, 4
0x180004381  jge     loc_180004464
0x180004387  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000438d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004392  mov     rbx, rax
0x180004395  test    rax, rax
0x180004398  jz      loc_18000445A
0x18000439e  cmp     qword ptr [rax+18h], 0
0x1800043a3  mov     ebp, 50h ; 'P'
0x1800043a8  mov     esi, [rax+10h]
0x1800043ab  jnz     short loc_1800043E2
0x1800043ad  test    esi, esi
0x1800043af  jz      short loc_1800043E2
0x1800043b1  mov     edx, 190h; dwBytes
0x1800043b6  lea     ecx, [rbp-48h]; dwFlags
0x1800043b9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800043be  mov     [rbx+18h], rax
0x1800043c2  test    rax, rax
0x1800043c5  jz      short loc_1800043E2
0x1800043c7  mov     dword ptr [rbx+20h], 5
0x1800043ce  lea     rcx, [rax+190h]
0x1800043d5  jmp     short loc_1800043DD
0x1800043d7  mov     [rax], bp
0x1800043da  add     rax, rbp
0x1800043dd  cmp     rax, rcx
0x1800043e0  jnz     short loc_1800043D7
0x1800043e2  mov     r9, [rbx+18h]
0x1800043e6  test    r9, r9
0x1800043e9  jz      short loc_18000445A
0x1800043eb  test    esi, esi
0x1800043ed  jz      short loc_180004420
0x1800043ef  movzx   eax, word ptr [rbx+20h]
0x1800043f3  mov     rcx, r9
0x1800043f6  lea     rdx, [rax+rax*4]
0x1800043fa  shl     rdx, 4
0x1800043fe  add     rdx, r9
0x180004401  cmp     r9, rdx
0x180004404  jz      short loc_180004420
0x180004406  mov     r8d, [rbx+10h]
0x18000440a  cmp     [rcx+4], r8d
0x18000440e  jbe     short loc_180004418
0x180004410  mov     eax, [rdi+8]
0x180004413  cmp     [rcx+8], eax
0x180004416  jz      short loc_18000445A
0x180004418  add     rcx, rbp
0x18000441b  cmp     rcx, rdx
0x18000441e  jnz     short loc_18000440A
0x180004420  movzx   eax, word ptr [rbx+22h]
0x180004424  xor     edx, edx
0x180004426  movzx   ecx, word ptr [rbx+20h]
0x18000442a  inc     eax
0x18000442c  div     ecx
0x18000442e  mov     rax, [rbx+8]
0x180004432  mov     r8d, 1
0x180004438  mov     [rbx+22h], dx
0x18000443c  lock xadd [rax], r8d
0x180004441  movzx   eax, dx
0x180004444  inc     r8d; unsigned int
0x180004447  mov     rdx, rdi; struct wil::FailureInfo *
0x18000444a  lea     rcx, [rax+rax*4]
0x18000444e  shl     rcx, 4
0x180004452  add     rcx, r9; this
0x180004455  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000445a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004464  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000446b  add     rsp, 20h
0x18000446f  pop     r14
0x180004471  pop     rdi
0x180004472  pop     rsi
0x180004473  pop     rbp
0x180004474  pop     rbx
0x180004475  retn
```
