# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005330`
- end: `0x180005537`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005330`
- `0x180005a2c`
- `0x180005b10`
- `0x1800064cc`
- `0x180006c94`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000535a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000541c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000535a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000541c`

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
0x180005330  push    rbx
0x180005332  push    rbp
0x180005333  push    rsi
0x180005334  push    rdi
0x180005335  push    r14
0x180005337  sub     rsp, 20h
0x18000533b  mov     r14, r8
0x18000533e  mov     rsi, rdx
0x180005341  mov     rdi, rcx
0x180005344  mov     byte ptr [rdx], 0
0x180005347  xor     bpl, bpl
0x18000534a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005351  test    rbx, rbx
0x180005354  jz      loc_1800053F0
0x18000535a  call    cs:__imp_GetCurrentThreadId
0x180005360  mov     r9d, eax
0x180005363  mov     r8d, eax
0x180005366  shr     r8, 2
0x18000536a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005374  mul     r8
0x180005377  shr     rdx, 3
0x18000537b  lea     rcx, [rdx+rdx*4]
0x18000537f  add     rcx, rcx
0x180005382  sub     r8, rcx
0x180005385  mov     rbx, [rbx+r8*8]
0x180005389  jmp     short loc_180005394
0x18000538b  cmp     [rbx], r9d
0x18000538e  jz      short loc_18000540B
0x180005390  mov     rbx, [rbx+8]
0x180005394  test    rbx, rbx
0x180005397  jnz     short loc_18000538B
0x180005399  test    rbx, rbx
0x18000539c  jz      short loc_1800053F0
0x18000539e  cmp     qword ptr [rbx], 0
0x1800053a2  jz      short loc_1800053F0
0x1800053a4  mov     [rsi], bpl
0x1800053a7  mov     r9, r14; unsigned __int64
0x1800053aa  mov     r8, rsi; char *
0x1800053ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800053b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800053b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800053b8  test    al, al
0x1800053ba  jz      short loc_1800053C0
0x1800053bc  mov     [rdi+48h], rsi
0x1800053c0  mov     rbx, [rbx]
0x1800053c3  mov     al, [rbx+28h]
0x1800053c6  mov     byte ptr [rbx+28h], 1
0x1800053ca  test    al, al
0x1800053cc  jnz     short loc_1800053E7
0x1800053ce  mov     rcx, [rbx+8]
0x1800053d2  mov     rax, [rcx]
0x1800053d5  mov     rdx, rdi
0x1800053d8  mov     rax, [rax]
0x1800053db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e0  or      bpl, al
0x1800053e3  mov     byte ptr [rbx+28h], 0
0x1800053e7  mov     rbx, [rbx+10h]
0x1800053eb  test    rbx, rbx
0x1800053ee  jnz     short loc_1800053C3
0x1800053f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800053f7  test    rax, rax
0x1800053fa  jz      short loc_18000541C
0x1800053fc  test    bpl, bpl
0x1800053ff  jnz     short loc_180005411
0x180005401  test    byte ptr [rdi+4], 2
0x180005405  jnz     short loc_180005411
0x180005407  xor     ecx, ecx
0x180005409  jmp     short loc_180005413
0x18000540b  add     rbx, 10h
0x18000540f  jmp     short loc_180005399
0x180005411  mov     cl, 1
0x180005413  mov     rdx, rdi
0x180005416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000541b  nop
0x18000541c  call    cs:__imp_GetCurrentThreadId
0x180005422  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005428  cmp     ecx, eax
0x18000542a  jz      loc_18000552C
0x180005430  mov     ecx, 1
0x180005435  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000543d  inc     ecx; this
0x18000543f  cmp     ecx, 4
0x180005442  jge     loc_180005525
0x180005448  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000544e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005453  mov     rbx, rax
0x180005456  test    rax, rax
0x180005459  jz      loc_18000551B
0x18000545f  mov     esi, [rax+10h]
0x180005462  mov     ebp, 50h ; 'P'
0x180005467  cmp     qword ptr [rax+18h], 0
0x18000546c  jnz     short loc_1800054A3
0x18000546e  test    esi, esi
0x180005470  jz      short loc_1800054A3
0x180005472  mov     edx, 190h; dwBytes
0x180005477  lea     ecx, [rbp-48h]; dwFlags
0x18000547a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000547f  mov     [rbx+18h], rax
0x180005483  test    rax, rax
0x180005486  jz      short loc_1800054A3
0x180005488  mov     dword ptr [rbx+20h], 5
0x18000548f  lea     rcx, [rax+190h]
0x180005496  jmp     short loc_18000549E
0x180005498  mov     [rax], bp
0x18000549b  add     rax, rbp
0x18000549e  cmp     rax, rcx
0x1800054a1  jnz     short loc_180005498
0x1800054a3  mov     r9, [rbx+18h]
0x1800054a7  test    r9, r9
0x1800054aa  jz      short loc_18000551B
0x1800054ac  test    esi, esi
0x1800054ae  jz      short loc_1800054E1
0x1800054b0  mov     rcx, r9
0x1800054b3  movzx   eax, word ptr [rbx+20h]
0x1800054b7  lea     rdx, [rax+rax*4]
0x1800054bb  shl     rdx, 4
0x1800054bf  add     rdx, r9
0x1800054c2  cmp     r9, rdx
0x1800054c5  jz      short loc_1800054E1
0x1800054c7  mov     r8d, [rbx+10h]
0x1800054cb  cmp     [rcx+4], r8d
0x1800054cf  jbe     short loc_1800054D9
0x1800054d1  mov     eax, [rdi+8]
0x1800054d4  cmp     [rcx+8], eax
0x1800054d7  jz      short loc_18000551B
0x1800054d9  add     rcx, rbp
0x1800054dc  cmp     rcx, rdx
0x1800054df  jnz     short loc_1800054CB
0x1800054e1  movzx   eax, word ptr [rbx+22h]
0x1800054e5  inc     eax
0x1800054e7  movzx   ecx, word ptr [rbx+20h]
0x1800054eb  xor     edx, edx
0x1800054ed  div     ecx
0x1800054ef  mov     [rbx+22h], dx
0x1800054f3  mov     rax, [rbx+8]
0x1800054f7  mov     r8d, 1
0x1800054fd  lock xadd [rax], r8d
0x180005502  inc     r8d; unsigned int
0x180005505  movzx   eax, dx
0x180005508  lea     rcx, [rax+rax*4]
0x18000550c  shl     rcx, 4
0x180005510  add     rcx, r9; this
0x180005513  mov     rdx, rdi; struct wil::FailureInfo *
0x180005516  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000551b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005525  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000552c  add     rsp, 20h
0x180005530  pop     r14
0x180005532  pop     rdi
0x180005533  pop     rsi
0x180005534  pop     rbp
0x180005535  pop     rbx
0x180005536  retn
```
