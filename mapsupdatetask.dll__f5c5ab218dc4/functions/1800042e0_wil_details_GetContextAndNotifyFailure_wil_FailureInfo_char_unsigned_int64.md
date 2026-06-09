# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800042e0`
- end: `0x1800044e7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800042e0`
- `0x1800049dc`
- `0x180004ac0`
- `0x18000550c`
- `0x180005d60`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000430a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000430a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043cc`

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
0x1800042e0  push    rbx
0x1800042e2  push    rbp
0x1800042e3  push    rsi
0x1800042e4  push    rdi
0x1800042e5  push    r14
0x1800042e7  sub     rsp, 20h
0x1800042eb  mov     r14, r8
0x1800042ee  mov     rsi, rdx
0x1800042f1  mov     rdi, rcx
0x1800042f4  mov     byte ptr [rdx], 0
0x1800042f7  xor     bpl, bpl
0x1800042fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004301  test    rbx, rbx
0x180004304  jz      loc_1800043A0
0x18000430a  call    cs:__imp_GetCurrentThreadId
0x180004310  mov     r9d, eax
0x180004313  mov     r8d, eax
0x180004316  shr     r8, 2
0x18000431a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004324  mul     r8
0x180004327  shr     rdx, 3
0x18000432b  lea     rcx, [rdx+rdx*4]
0x18000432f  add     rcx, rcx
0x180004332  sub     r8, rcx
0x180004335  mov     rbx, [rbx+r8*8]
0x180004339  jmp     short loc_180004344
0x18000433b  cmp     [rbx], r9d
0x18000433e  jz      short loc_1800043BB
0x180004340  mov     rbx, [rbx+8]
0x180004344  test    rbx, rbx
0x180004347  jnz     short loc_18000433B
0x180004349  test    rbx, rbx
0x18000434c  jz      short loc_1800043A0
0x18000434e  cmp     qword ptr [rbx], 0
0x180004352  jz      short loc_1800043A0
0x180004354  mov     [rsi], bpl
0x180004357  mov     r9, r14; unsigned __int64
0x18000435a  mov     r8, rsi; char *
0x18000435d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004360  mov     rcx, rdi; struct wil::FailureInfo *
0x180004363  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004368  test    al, al
0x18000436a  jz      short loc_180004370
0x18000436c  mov     [rdi+48h], rsi
0x180004370  mov     rbx, [rbx]
0x180004373  mov     al, [rbx+28h]
0x180004376  mov     byte ptr [rbx+28h], 1
0x18000437a  test    al, al
0x18000437c  jnz     short loc_180004397
0x18000437e  mov     rcx, [rbx+8]
0x180004382  mov     rax, [rcx]
0x180004385  mov     rdx, rdi
0x180004388  mov     rax, [rax]
0x18000438b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004390  or      bpl, al
0x180004393  mov     byte ptr [rbx+28h], 0
0x180004397  mov     rbx, [rbx+10h]
0x18000439b  test    rbx, rbx
0x18000439e  jnz     short loc_180004373
0x1800043a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800043a7  test    rax, rax
0x1800043aa  jz      short loc_1800043CC
0x1800043ac  test    bpl, bpl
0x1800043af  jnz     short loc_1800043C1
0x1800043b1  test    byte ptr [rdi+4], 2
0x1800043b5  jnz     short loc_1800043C1
0x1800043b7  xor     ecx, ecx
0x1800043b9  jmp     short loc_1800043C3
0x1800043bb  add     rbx, 10h
0x1800043bf  jmp     short loc_180004349
0x1800043c1  mov     cl, 1
0x1800043c3  mov     rdx, rdi
0x1800043c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043cb  nop
0x1800043cc  call    cs:__imp_GetCurrentThreadId
0x1800043d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800043d8  cmp     ecx, eax
0x1800043da  jz      loc_1800044DC
0x1800043e0  mov     ecx, 1
0x1800043e5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800043ed  inc     ecx; this
0x1800043ef  cmp     ecx, 4
0x1800043f2  jge     loc_1800044D5
0x1800043f8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800043fe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004403  mov     rbx, rax
0x180004406  test    rax, rax
0x180004409  jz      loc_1800044CB
0x18000440f  mov     esi, [rax+10h]
0x180004412  mov     ebp, 50h ; 'P'
0x180004417  cmp     qword ptr [rax+18h], 0
0x18000441c  jnz     short loc_180004453
0x18000441e  test    esi, esi
0x180004420  jz      short loc_180004453
0x180004422  mov     edx, 190h; dwBytes
0x180004427  lea     ecx, [rbp-48h]; dwFlags
0x18000442a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000442f  mov     [rbx+18h], rax
0x180004433  test    rax, rax
0x180004436  jz      short loc_180004453
0x180004438  mov     dword ptr [rbx+20h], 5
0x18000443f  lea     rcx, [rax+190h]
0x180004446  jmp     short loc_18000444E
0x180004448  mov     [rax], bp
0x18000444b  add     rax, rbp
0x18000444e  cmp     rax, rcx
0x180004451  jnz     short loc_180004448
0x180004453  mov     r9, [rbx+18h]
0x180004457  test    r9, r9
0x18000445a  jz      short loc_1800044CB
0x18000445c  test    esi, esi
0x18000445e  jz      short loc_180004491
0x180004460  mov     rcx, r9
0x180004463  movzx   eax, word ptr [rbx+20h]
0x180004467  lea     rdx, [rax+rax*4]
0x18000446b  shl     rdx, 4
0x18000446f  add     rdx, r9
0x180004472  cmp     r9, rdx
0x180004475  jz      short loc_180004491
0x180004477  mov     r8d, [rbx+10h]
0x18000447b  cmp     [rcx+4], r8d
0x18000447f  jbe     short loc_180004489
0x180004481  mov     eax, [rdi+8]
0x180004484  cmp     [rcx+8], eax
0x180004487  jz      short loc_1800044CB
0x180004489  add     rcx, rbp
0x18000448c  cmp     rcx, rdx
0x18000448f  jnz     short loc_18000447B
0x180004491  movzx   eax, word ptr [rbx+22h]
0x180004495  inc     eax
0x180004497  movzx   ecx, word ptr [rbx+20h]
0x18000449b  xor     edx, edx
0x18000449d  div     ecx
0x18000449f  mov     [rbx+22h], dx
0x1800044a3  mov     rax, [rbx+8]
0x1800044a7  mov     r8d, 1
0x1800044ad  lock xadd [rax], r8d
0x1800044b2  inc     r8d; unsigned int
0x1800044b5  movzx   eax, dx
0x1800044b8  lea     rcx, [rax+rax*4]
0x1800044bc  shl     rcx, 4
0x1800044c0  add     rcx, r9; this
0x1800044c3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800044c6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800044cb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800044d5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800044dc  add     rsp, 20h
0x1800044e0  pop     r14
0x1800044e2  pop     rdi
0x1800044e3  pop     rsi
0x1800044e4  pop     rbp
0x1800044e5  pop     rbx
0x1800044e6  retn
```
