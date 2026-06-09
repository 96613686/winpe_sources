# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800052e0`
- end: `0x1800054e7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800052e0`
- `0x180005a80`
- `0x180005b64`
- `0x1800063d8`
- `0x1800068b4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000530a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000530a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053cc`

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
0x1800052e0  push    rbx
0x1800052e2  push    rbp
0x1800052e3  push    rsi
0x1800052e4  push    rdi
0x1800052e5  push    r14
0x1800052e7  sub     rsp, 20h
0x1800052eb  mov     r14, r8
0x1800052ee  mov     rsi, rdx
0x1800052f1  mov     rdi, rcx
0x1800052f4  mov     byte ptr [rdx], 0
0x1800052f7  xor     bpl, bpl
0x1800052fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005301  test    rbx, rbx
0x180005304  jz      loc_1800053A0
0x18000530a  call    cs:__imp_GetCurrentThreadId
0x180005310  mov     r9d, eax
0x180005313  mov     r8d, eax
0x180005316  shr     r8, 2
0x18000531a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005324  mul     r8
0x180005327  shr     rdx, 3
0x18000532b  lea     rcx, [rdx+rdx*4]
0x18000532f  add     rcx, rcx
0x180005332  sub     r8, rcx
0x180005335  mov     rbx, [rbx+r8*8]
0x180005339  jmp     short loc_180005344
0x18000533b  cmp     [rbx], r9d
0x18000533e  jz      short loc_1800053BB
0x180005340  mov     rbx, [rbx+8]
0x180005344  test    rbx, rbx
0x180005347  jnz     short loc_18000533B
0x180005349  test    rbx, rbx
0x18000534c  jz      short loc_1800053A0
0x18000534e  cmp     qword ptr [rbx], 0
0x180005352  jz      short loc_1800053A0
0x180005354  mov     [rsi], bpl
0x180005357  mov     r9, r14; unsigned __int64
0x18000535a  mov     r8, rsi; char *
0x18000535d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005360  mov     rcx, rdi; struct wil::FailureInfo *
0x180005363  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005368  test    al, al
0x18000536a  jz      short loc_180005370
0x18000536c  mov     [rdi+48h], rsi
0x180005370  mov     rbx, [rbx]
0x180005373  mov     al, [rbx+28h]
0x180005376  mov     byte ptr [rbx+28h], 1
0x18000537a  test    al, al
0x18000537c  jnz     short loc_180005397
0x18000537e  mov     rcx, [rbx+8]
0x180005382  mov     rax, [rcx]
0x180005385  mov     rdx, rdi
0x180005388  mov     rax, [rax]
0x18000538b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005390  or      bpl, al
0x180005393  mov     byte ptr [rbx+28h], 0
0x180005397  mov     rbx, [rbx+10h]
0x18000539b  test    rbx, rbx
0x18000539e  jnz     short loc_180005373
0x1800053a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800053a7  test    rax, rax
0x1800053aa  jz      short loc_1800053CC
0x1800053ac  test    bpl, bpl
0x1800053af  jnz     short loc_1800053C1
0x1800053b1  test    byte ptr [rdi+4], 2
0x1800053b5  jnz     short loc_1800053C1
0x1800053b7  xor     ecx, ecx
0x1800053b9  jmp     short loc_1800053C3
0x1800053bb  add     rbx, 10h
0x1800053bf  jmp     short loc_180005349
0x1800053c1  mov     cl, 1
0x1800053c3  mov     rdx, rdi
0x1800053c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cb  nop
0x1800053cc  call    cs:__imp_GetCurrentThreadId
0x1800053d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800053d8  cmp     ecx, eax
0x1800053da  jz      loc_1800054DC
0x1800053e0  mov     ecx, 1
0x1800053e5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800053ed  inc     ecx; this
0x1800053ef  cmp     ecx, 4
0x1800053f2  jge     loc_1800054D5
0x1800053f8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800053fe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005403  mov     rbx, rax
0x180005406  test    rax, rax
0x180005409  jz      loc_1800054CB
0x18000540f  mov     esi, [rax+10h]
0x180005412  mov     ebp, 50h ; 'P'
0x180005417  cmp     qword ptr [rax+18h], 0
0x18000541c  jnz     short loc_180005453
0x18000541e  test    esi, esi
0x180005420  jz      short loc_180005453
0x180005422  mov     edx, 190h; dwBytes
0x180005427  lea     ecx, [rbp-48h]; dwFlags
0x18000542a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000542f  mov     [rbx+18h], rax
0x180005433  test    rax, rax
0x180005436  jz      short loc_180005453
0x180005438  mov     dword ptr [rbx+20h], 5
0x18000543f  lea     rcx, [rax+190h]
0x180005446  jmp     short loc_18000544E
0x180005448  mov     [rax], bp
0x18000544b  add     rax, rbp
0x18000544e  cmp     rax, rcx
0x180005451  jnz     short loc_180005448
0x180005453  mov     r9, [rbx+18h]
0x180005457  test    r9, r9
0x18000545a  jz      short loc_1800054CB
0x18000545c  test    esi, esi
0x18000545e  jz      short loc_180005491
0x180005460  mov     rcx, r9
0x180005463  movzx   eax, word ptr [rbx+20h]
0x180005467  lea     rdx, [rax+rax*4]
0x18000546b  shl     rdx, 4
0x18000546f  add     rdx, r9
0x180005472  cmp     r9, rdx
0x180005475  jz      short loc_180005491
0x180005477  mov     r8d, [rbx+10h]
0x18000547b  cmp     [rcx+4], r8d
0x18000547f  jbe     short loc_180005489
0x180005481  mov     eax, [rdi+8]
0x180005484  cmp     [rcx+8], eax
0x180005487  jz      short loc_1800054CB
0x180005489  add     rcx, rbp
0x18000548c  cmp     rcx, rdx
0x18000548f  jnz     short loc_18000547B
0x180005491  movzx   eax, word ptr [rbx+22h]
0x180005495  inc     eax
0x180005497  movzx   ecx, word ptr [rbx+20h]
0x18000549b  xor     edx, edx
0x18000549d  div     ecx
0x18000549f  mov     [rbx+22h], dx
0x1800054a3  mov     rax, [rbx+8]
0x1800054a7  mov     r8d, 1
0x1800054ad  lock xadd [rax], r8d
0x1800054b2  inc     r8d; unsigned int
0x1800054b5  movzx   eax, dx
0x1800054b8  lea     rcx, [rax+rax*4]
0x1800054bc  shl     rcx, 4
0x1800054c0  add     rcx, r9; this
0x1800054c3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800054c6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800054cb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800054d5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800054dc  add     rsp, 20h
0x1800054e0  pop     r14
0x1800054e2  pop     rdi
0x1800054e3  pop     rsi
0x1800054e4  pop     rbp
0x1800054e5  pop     rbx
0x1800054e6  retn
```
